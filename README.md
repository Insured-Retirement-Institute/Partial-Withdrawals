# Partial Withdrawals Attribute Specification

This repository contains the schema definition for Partial Withdrawals, supporting the modernization of In-Force Transactions (IFT) by transitioning from legacy XML/SOAP messaging to RESTful APIs. This aligns with the industry’s Digital First goals and prepares stakeholders for scalable, secure, and interoperable retirement policy management.

## Get started
To begin using this specification:

1. Clone the repository:
Shellgit clone https://github.com/Insured-Retirement-Institute/Partial-Withdrawals.git

2. Navigate to the project directory:
Shellcd Partial-WithdrawalsShow more lines

3. Review the schema documentation:

- Understand the structure and required fields.
- Integrate the schema into your transaction processing systems.


4. Validate your data:

- Ensure all required fields are populated.
- Follow the data types and length constraints.

## Business Case
The financial services industry is rapidly evolving toward seamless, real-time, and lightweight digital experiences. Legacy XML/SOAP technology is approaching end-of-life and lacks the scalability, flexibility, and security required by today’s digital ecosystems. RESTful APIs, using JSON payloads and OAuth 2.0 authentication, are now the de facto standard.
Key Drivers:

- End-of-Life Technology: SOAP is no longer supported; REST/JSON is prioritized by vendors and cloud providers.
- Security: Modern protocols (OAuth 2.0) are required.
- Scalability & Flexibility: REST APIs are lightweight, easier to parse, and integrate with microservices.
- Industry Alignment: Supports IRI Digital First goals for secure, interoperable technology.

Objectives & Key Results:

- Transition all IFT processing from XML to RESTful API architecture.
- Reduce transaction payload size and processing time.
- Improve integration velocity across firms and carriers.
- Strengthen transaction security.
- Ensure long-term vendor and community support.

## User Stories, personna - supporting documents for the business case
- As a Policy Administrator, I want to validate all required fields before submitting a transaction so that I can avoid processing delays.
- As a System Integrator, I want to map the schema to our internal data model so that we can automate the transaction flow.
- As a Compliance Analyst, I want to extract tax jurisdiction and exemption data so that I can verify regulatory compliance.
- As a Financial Advisor, I want to confirm the payee’s bank and address details so that I can ensure accurate disbursement.

1. Policy Administrator

- Goals: Ensure accurate and timely processing of partial withdrawals.
- Needs: Clear schema definitions, validation rules, and integration guidance.
- Pain Points: Manual data entry errors, inconsistent formats, lack of traceability.

2. System Integrator

- Goals: Implement schema into backend systems and APIs.
- Needs: JSON/XML schema formats, sample payloads, field-level documentation.
- Pain Points: Ambiguous field definitions, missing required attributes.

3. Compliance Analyst

- Goals: Ensure transactions meet regulatory standards.
- Needs: Audit trails, jurisdictional tax details, exemption tracking.
- Pain Points: Incomplete data, lack of standardization.

4. Financial Advisor

- Goals: Guide clients through partial withdrawal processes.
- Needs: Clear understanding of payment forms, tax implications, and beneficiary details.
- Pain Points: Confusing terminology, paper process.

## Schema Overview
The schema for partial withdrawal transactions is defined in the data model and includes the following key components:
## Root Attributes

- correlationId: Unique transaction ID (string, required)
- effectiveDate: Transaction date (string, required, format: yyyy-mm-dd)
- reverseInitiator: Indicates reversal source (boolean, optional)
- override: Rule override flag (boolean, optional)
- caseId: Live Case ID (string, optional)
- associatedFirmId: Firm identifier (string, required)
- NSCCparticipantID: NSCC participant identifier (string, required)

## Tax Withholding Instructions

- party: Payee/beneficiary details (ID, name, organization)
- taxWithholdingType: Type of tax withholding (string, required)
- taxRateToUse: Payment mode for tax withholding (string, required)
- filingStatus: Tax filing status (string, optional)
- dollar/percentage/exemptions: Requested values (optional)
- taxJurisdiction: Jurisdiction for tax purposes (optional)

## Payee/Beneficiary Details

- partyId, firstName, middleName, lastName, organizationName: Identification fields
- paymentForm: Type of payment (string, optional)
- allocationPercent: Allocation percentage (number, optional)
- bank: Bank details (account number, routing number, etc.)
- address: Physical/mailing address details

## Parties

- partyRole, partyId, firstName, middleName, lastName, organizationName
- paymentForm, allocationPercentage
- forBenefitOfOrForFurtherCredit: FBO/FFC notation (string, optional)
- bank, address: Financial and contact details

## Charges

- chargeType, chargeWaiverIndicator, chargeWaiverReason

## Producer

- producerNumber, npn, crdNumber, associatedFirmId, NSCCparticipantID

## Transaction Amounts

- amountType, disbursementType, disbursementPaymentForm

## Business Owners 
- Carrier Business Owner: digitalfirst@brighthousefinancial.com
- Distributor Business Owner: contact
- Solution Provider Business Owner: contact

## How to engage, contribute, and give feedback
- These working groups are occuring on ....
- Please contact the business owners or IRI (hpikus@irionline.org) to get added to the working group discussions. 

## Change subsmissions and reporting issues and bugs

Security issues and bugs should be reported directly to Katherine Dease kdease@irionline.org. Issues and bugs can be reported directly within the issues tab of a repository. Change requests should follow the standards governance workflow outlined on the [main page](https://github.com/Insured-Retirement-Institute).

## Code of conduct

See [style guide](https://github.com/Insured-Retirement-Institute/Style-Guide)
