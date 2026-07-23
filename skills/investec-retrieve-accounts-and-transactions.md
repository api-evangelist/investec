---
name: Retrieve accounts, balances and transactions (AIS)
description: Set up an Account Access Consent, then read the customer's accounts, balances and transactions via the Investec / OBIE Account & Transaction Information API.
api: openapi/obie-account-info-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountId, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Retrieve accounts, balances and transactions

Investec Bank plc exposes UK Open Banking Account Information (AISP) under the OBIE Read/Write Standard v4.0. Access is FAPI-secured: OAuth2/OIDC over mutual-TLS with OBIE/eIDAS certificates and PSD2 strong customer authentication.

## Steps
1. **Create the consent.** `CreateAccountAccessConsents` with the `Permissions` you need (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`). Use a TPP client-credentials token (`TPPOAuth2Security`, scope `accounts`).
2. **PSU authorisation.** Redirect the customer through the bank's authorisation endpoint (`PSUOAuth2Security`, authorization_code + SCA) to authorise the `ConsentId`.
3. **Confirm consent status.** `GetAccountAccessConsentsConsentId` — proceed only when `Status` is `Authorised`.
4. **List accounts.** `GetAccounts`, then `GetAccountsAccountId` for detail.
5. **Read balances.** `GetAccountsAccountIdBalances`.
6. **Read transactions.** `GetAccountsAccountIdTransactions`; page with `Links.Next` / `Meta.TotalPages`.

## Rules
- Send `x-fapi-interaction-id` on every call for traceability (echo it back from responses in logs).
- Errors return the `OBErrorResponse1` envelope (`Code`/`Message`/`Errors[]`) — see `errors/investec-problem-types.yml`.
- Conventions (auth, pagination, tracing): `conventions/investec-conventions.yml`.
