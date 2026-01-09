
# IRI Withdrawals API


# **Systematic Program Setup Attribute Specification**

This repository contains the schema definitions for **Systematic Withdrawal** and **Systematic RMD (Required Minimum Distribution)** program setup transactions. These specifications support the modernization of In-Force Transactions (IFT) by transitioning from legacy XML/SOAP messaging to RESTful APIs. This aligns with the industry’s Digital First goals and prepares stakeholders for scalable, secure, and interoperable retirement policy management.

---

## Business Case
The financial services industry is rapidly evolving toward seamless, real-time, and lightweight digital experiences. Legacy XML/SOAP technology is approaching end-of-life and lacks the scalability, flexibility, and security required by today’s digital ecosystems. RESTful APIs, using JSON payloads and OAuth 2.0 authentication, are now the de facto standard.
### Problem Statement
- End-of-Life Technology: SOAP is no longer supported; REST/JSON is prioritized by vendors and cloud providers.
- Security: Modern protocols (OAuth 2.0) are required.
- Scalability & Flexibility: REST APIs are lightweight, easier to parse, and integrate with microservices.
- Industry Alignment: Supports IRI Digital First goals for secure, interoperable technology.

### Objectives
- Transition all IFT processing from XML to RESTful API architecture.
- Reduce transaction payload size and processing time.
- Improve integration velocity across firms and carriers.
- Strengthen transaction security.
- Ensure long-term vendor and community support.

### Key Features
- Modular RESTful APIs with JSON payloads and OAuth 2.0 authentication.
- OpenAPI/Swagger documentation for easy onboarding.
- Accelerated development using validated payload structures.
- Standardized testing framework for early and consistent validation.
- Open contribution to IRI standards for industry-wide adoption.

---

## Supported Transactions

### 1. Schema Overview
The schema for systematic program setup transactions is defined in the data model and includes the following key components for both Systematic Withdrawal and Systematic RMD:

#### User Stories
- As a Policy Administrator, I want to validate all required fields before submitting a transaction so that I can avoid processing delays.
- As a System Integrator, I want to map the schema to our internal data model so that we can automate the transaction flow.
- As a Financial Advisor, I want to confirm the payee’s bank and address details so that I can ensure accurate disbursement.

#### Personas
**Policy Administrator**  
- Goals: Ensure accurate and timely processing of systematic withdrawals and RMDs.
- Needs: Clear schema definitions, validation rules, and integration guidance.
- Pain Points: Manual data entry errors, inconsistent formats, lack of traceability.

**System Integrator**  
- Goals: Implement schema into backend systems and APIs.
- Needs: JSON schema formats, sample payloads, field-level documentation.
- Pain Points: Ambiguous field definitions, missing required attributes.

**Financial Advisor**  
- Goals: Guide clients through systematic withdrawal and RMD processes.
- Needs: Clear understanding of payment forms, tax implications, and beneficiary details.
- Pain Points: Confusing terminology, paper process.

---
## Schema Overview
The schema for systematic program setup transactions is defined in the data model and includes the following key components for both Systematic Withdrawal and Systematic RMD:

### Root Attributes

- correlationId: Unique transaction ID (string, required)
- effectiveDate: Transaction date (string, required, format: yyyy-mm-dd)
- actionIndicator: Transaction action (enum: N, O, C)
- associatedFirmId: Firm identifier (string, required)
- nsccParticipantId: NSCC participant identifier (string, required)
- externalArrangementId: Arrangement ID from external system (string, required)
- cusip: Security identifier (string, optional)

### Systematic Program

- paymentForm: Type of payment (enum: DTCC, CREDITCARD, ACH, CHECK, WIRE, EXCHANGE)
- arrangementType: WITHDRAWAL or REQUIREDMINIMUMDISTRIBUTION
- amountType: AMOUNT, PERCENTAGE, MAX, FREEWITHDRAWALAMOUNT, WITHDRAWALUNTILBASIS, EARNINGSONLY, PRORATA
- netGrossIndicator: Net or Gross (enum: N, G)
- requestedAmount/requestedPercentage: Amount or percentage, as applicable
- frequency: Transaction frequency (enum: DAILY, EVERYTWOWEEKS, MONTHLY, SEMIANNUAL, QUARTERLY, ANNUAL, SINGLEPAYMENT)
- startDate, endDate, previousTransactionDate, nextTransactionDate: Date fields

### For Systematic RMD Only:

- rmdInfo: RMD-specific details (tax year, age at distribution, spouse DOB, requested amount, calculation method, prior year end value)

### Payee/Beneficiary Details

- partyId, firstName, middleName, lastName, organizationName
- bank: Bank details (account number, routing number, etc.)
- taxWithholdingInstructions: Array of tax withholding instructions

### Parties

- partyRole, partyId, firstName, middleName, lastName, organizationName
- paymentForm, allocationPercentage
- bank, address: Financial and contact details

### Producer

- producerNumber, npn, crdNumber

### Fund Allocation & Distributions

- allocationOption: PRORATA, DOLLAR, SPECIFYPERCENTAGE, SPECIFIEDFUNDS, etc.
- fundDistributions: Array of fund distribution objects

---

## Change Submissions and Reporting Issues

- Issues and bugs can be reported directly within the **Issues** tab of this repository.
- **Security issues** should be reported directly to Katherine Dease at **kdease@irionline.org**.
- Change requests should follow the **standards governance workflow** outlined on the main page.

---

## Code of Conduct

Please review and adhere to the **Code of Conduct** and **Style Guide** provided in the repository to ensure consistency and professionalism.

---

## How to Contribute

- Fork the repo and submit pull requests.
- Report issues via the **Issues** tab.
- Join working groups: **hpikus@irionline.org**.

---

## Business Owners

- **Carrier Business Owner:** digitalfirst@brighthousefinancial.com  
- **Distributor Business Owner:** [contact]  
- **Solution Provider Business Owner:** [contact]

  
