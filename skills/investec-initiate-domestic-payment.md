---
name: Initiate a domestic payment (PIS)
description: Create a domestic-payment consent, confirm funds availability, and submit the payment via the Investec / OBIE Payment Initiation API using an idempotency key.
api: openapi/obie-payment-initiation-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a domestic payment

UK Open Banking Payment Initiation (PISP) under OBIE Read/Write v4.0, FAPI-secured over mTLS with PSD2 SCA.

## Steps
1. **Create the payment consent.** `CreateDomesticPaymentConsents` with `Initiation` (debtor/creditor accounts, `InstructedAmount`). Set a unique `x-idempotency-key` header.
2. **PSU authorisation + SCA.** Send the customer through `PSUOAuth2Security` (authorization_code + SCA) to authorise the `ConsentId`.
3. **Confirm status.** `GetDomesticPaymentConsentsConsentId` — proceed when `Status` is `Authorised`.
4. **Check funds (optional).** `GetDomesticPaymentConsentsConsentIdFundsConfirmation`.
5. **Submit the payment.** `CreateDomesticPayments` referencing the authorised `ConsentId`, with a fresh `x-idempotency-key`. The `Initiation` block must match the consent exactly.
6. **Poll status.** `GetDomesticPaymentsDomesticPaymentId` until `Status` reaches `AcceptedSettlementCompleted` (or a terminal reject).

## Rules
- **Idempotency is mandatory** on payment creation: `x-idempotency-key` (≤40 chars). Replaying a key with the same payload must not double-pay — see `conventions/investec-conventions.yml`.
- The `Initiation`/`InstructedAmount` on `CreateDomesticPayments` must be identical to the consent.
- Errors use `OBErrorResponse1` — see `errors/investec-problem-types.yml`.
