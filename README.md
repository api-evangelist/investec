# Investec (investec)

Investec is an international specialist bank and wealth manager, dual-listed on the London Stock Exchange and Johannesburg Stock Exchange and operating through Investec plc (UK) and Investec Limited (South Africa). In the United Kingdom, Investec Bank plc is authorised by the PRA and regulated by the FCA and PRA and is an FCA-registered Account Servicing Payment Service Provider (ASPSP) under UK Open Banking. It exposes Account and Transaction Information (AIS), Payment Initiation (PIS), and Confirmation of Funds (CBPII) interfaces built to the Open Banking Implementation Entity (OBIE) Read/Write API Standard (v3.1), secured with FAPI-grade OAuth2/OIDC, PSD2 strong customer authentication, and mutual-TLS. As a specialist private bank and wealth manager rather than a mass-market retail bank, Investec is not one of the CMA9 and operates no branch or ATM network. Alongside Open Banking, Investec runs a first-party Programmable Banking / Open API developer platform at `openapi.investec.com`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/investec/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/investec/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- United Kingdom
- Payments
- Account Information
- Specialist Bank
- Wealth Management
- FAPI
- Programmable Banking

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Investec Private Bank API

First-party Programmable Banking API to retrieve data and perform actions on your own or your business's Investec Private Banking account, including accounts, balances, transactions, transfers, and payments.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com`

### Investec Business & Commercial Banking API

First-party Programmable Banking API to retrieve data and perform actions on Investec business and commercial banking accounts.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com`

### Investec Intermediaries API

First-party Programmable Banking API to retrieve data and perform actions on behalf of your clients, including forex quoting and trading.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com`

### Investec Intermediaries Forex API

First-party Programmable Banking API for Balance of Payments (BOP) reporting and foreign-exchange information retrieval on behalf of your clients.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com`

### Investec Card API

First-party Programmable Banking Card API to retrieve card data and programmatically attach rules that run before and after transactions on Investec programmable cards.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com`

### Investec Authorisation API (OAuth)

First-party OAuth2 authorisation endpoint that generates and refreshes the access tokens authorising calls to the Investec Programmable Banking APIs.

- **Human URL:** [https://developer.investec.com/api-reference](https://developer.investec.com/api-reference)
- **Base URL:** `https://openapi.investec.com/identity/v2/oauth2/token`

### Investec Account and Transaction Information API (AIS)

UK Open Banking Account Information Service (AISP) interface for accessing account, balance, transaction, and product data. Investec Bank plc conforms to the OBIE Read/Write API Standard (v3.1); the harvested OpenAPI is the shared OBIE standard specification, not an Investec-proprietary contract, and is FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://developer.investec.com/api-products](https://developer.investec.com/api-products)
- **Base URL:** `/open-banking/v3.1/aisp` (OBIE-standard path; Investec production host issued at onboarding)

#### Properties

- [OpenAPI](openapi/obie-account-info-openapi.yaml) — shared OBIE Read/Write standard

### Investec Payment Initiation API (PIS)

UK Open Banking Payment Initiation Service (PISP) interface for initiating domestic and other payments. Investec Bank plc conforms to the OBIE Read/Write API Standard (v3.1); the harvested OpenAPI is the shared OBIE standard specification, not an Investec-proprietary contract, and is FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://developer.investec.com/api-products](https://developer.investec.com/api-products)
- **Base URL:** `/open-banking/v3.1/pisp` (OBIE-standard path; Investec production host issued at onboarding)

#### Properties

- [OpenAPI](openapi/obie-payment-initiation-openapi.yaml) — shared OBIE Read/Write standard

### Investec Confirmation of Funds API (CBPII)

UK Open Banking Confirmation of Funds (CBPII) interface for checking whether funds are available on an account. Investec Bank plc conforms to the OBIE Read/Write API Standard (v3.1); the harvested OpenAPI is the shared OBIE standard specification, not an Investec-proprietary contract, and is FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://developer.investec.com/api-products](https://developer.investec.com/api-products)
- **Base URL:** `/open-banking/v3.1/cbpii` (OBIE-standard path; Investec production host issued at onboarding)

#### Properties

- [OpenAPI](openapi/obie-confirmation-funds-openapi.yaml) — shared OBIE Read/Write standard

## Common Properties

- [Website](https://www.investec.com/)
- [Developer Portal](https://developer.investec.com/)
- [Documentation](https://developer.investec.com/api-reference)
- [API Reference](https://developer.investec.com/api-products)
- [Blog / Community Wiki](https://investec.gitbook.io/programmable-banking-community-wiki)
- [GitHub Organization](https://github.com/investec)
- [LinkedIn](https://www.linkedin.com/company/investec)
- [Support](https://developer.investec.com/support)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
