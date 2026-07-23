---
name: Confirm funds availability (CBPII)
description: Establish a funds-confirmation consent and check whether funds are available on an account via the Investec / OBIE Confirmation of Funds API.
api: openapi/obie-confirmation-funds-openapi.yaml
operations: [CreateFundsConfirmationConsents, GetFundsConfirmationConsentsConsentId, CreateFundsConfirmations]
---

# Confirm funds availability

UK Open Banking Confirmation of Funds (CBPII) under OBIE Read/Write v4.0, FAPI-secured over mTLS with PSD2 SCA.

## Steps
1. **Create the funds-confirmation consent.** `CreateFundsConfirmationConsents` (scope `fundsconfirmations`).
2. **PSU authorisation.** Authorise the `ConsentId` via `PSUOAuth2Security` (SCA).
3. **Confirm status.** `GetFundsConfirmationConsentsConsentId` — proceed when `Status` is `Authorised`.
4. **Check funds.** `CreateFundsConfirmations` with the `ConsentId` and an `InstructedAmount`; the response `FundsAvailable` boolean answers the query (no balance is disclosed).

## Rules
- CBPII returns only a yes/no funds decision — never a balance.
- Errors use the `OBErrorResponse1` envelope — see `errors/investec-problem-types.yml`.
- Auth/tracing conventions: `conventions/investec-conventions.yml`.
