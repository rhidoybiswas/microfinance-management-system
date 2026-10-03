# Microfinance Management System

A full-stack financial application designed to simulate the core operations of a microfinance institution, covering customer management, security accounts, loan applications, loan approval, loan disbursement, installment collection, payment processing, financial journal transactions, and MIS-to-FIS financial processing.

The project is developed and tested as a complete software lifecycle by covering both **Software Development** and **Software Quality Assurance (SQA)** activities.

**Technology Stack:** Python, FastAPI, PostgreSQL, SQLAlchemy, React, REST API, HTTPX, Pytest, Postman, and Git.

The project focuses on:

- Backend engineering and financial business logic.
- React frontend development and UI workflows.
- REST API development and integration.
- Relational database design and validation.
- Financial transaction processing.
- External API integration.
- Developer-level testing.
- Functional and integration testing.
- API and database testing.
- End-to-end system testing.
- Regression testing.
- Automated testing.
- Financial business-rule validation.
- Data integrity and transaction consistency.

---

# 1. Project Overview

The Microfinance Loan Management System is designed to simulate the core operations of a microfinance institution, covering the complete loan lifecycle and associated financial transaction processing.

The application combines operational activities managed through the Management Information System (MIS) with financial transaction processing through the Financial Information System (FIS).

The system will support:

- Customer management.
- Security account management.
- Security transactions.
- Loan application and approval.
- Loan disbursement.
- Installment generation.
- Payment processing.
- Payment gateway integration.
- MIS-to-FIS transaction processing.
- Process Programs Journal.
- General Journal.
- Manual General Journal posting.
- Financial transaction history.
- Operational and financial reporting.

The Python backend will enforce business rules, validate financial operations, manage database transactions, and coordinate communication between application components.

The React frontend will provide the user interface for operational activities, financial processing, transaction monitoring, validation messages, and workflow demonstration.

The application will be tested from both **developer and QA perspectives** to validate functionality, integration, data consistency, business rules, error handling, and complete user workflows.

## Primary Objectives

### Development Objectives

- Develop RESTful APIs using Python and FastAPI.
- Design and manage a relational database using PostgreSQL.
- Implement financial business rules and validation.
- Build a complete loan management workflow.
- Develop a React-based frontend.
- Integrate frontend and backend through REST APIs.
- Integrate a simulated external payment gateway.
- Implement MIS-to-FIS transaction processing.
- Support General Journal transaction viewing and manual journal posting.
- Maintain financial data consistency and transaction history.
- Implement database migrations using Alembic.
- Write automated backend tests using Pytest.

### Quality Assurance Objectives

- Validate functional requirements.
- Design test scenarios and test cases.
- Perform positive and negative testing.
- Validate API requests and responses.
- Validate HTTP status codes and error responses.
- Validate financial business rules.
- Validate database records and transaction consistency.
- Test frontend forms and user workflows.
- Perform API integration testing.
- Perform payment gateway integration testing.
- Test MIS-to-FIS processing.
- Test General Journal balancing and posting rules.
- Test duplicate transaction prevention.
- Test exception and failure scenarios.
- Perform regression testing after defect fixes.
- Perform end-to-end workflow testing.
- Perform UAT-style validation of major business processes.
- Automate repeatable backend/API test scenarios.
- Verify that defects are correctly fixed without introducing regressions.

---

# 2. Technology Stack

| Technology | Purpose |
| ---------- | ------- |
| Python | Backend programming |
| FastAPI | REST API development |
| Pydantic | Request and response validation |
| PostgreSQL | Relational database |
| SQLAlchemy | ORM and database operations |
| Alembic | Database schema migrations |
| HTTPX | External API communication |
| React | Frontend development |
| JavaScript | Frontend application logic |
| Vite | Frontend development tooling |
| Pytest | Automated testing |
| Postman | API testing |
| Git | Version control |
| GitHub | Source code hosting |

---

# 3. System Architecture

```text
                         User
                          |
                          v
                  React Frontend / UI
                          |
                     REST API Calls
                          |
                          v
                  FastAPI Backend
                          |
              +-----------+-----------+
              |           |           |
              v           v           v
        Business      SQLAlchemy    HTTPX
          Logic            |           |
              |            v           v
              |        PostgreSQL   Mock Payment
              |        Database      Gateway
              |
              +-----------------------------+
              |                             |
              v                             v
       MIS Transaction                General Journal
         Processing                  Manual Posting
              |                             |
              v                             |
    Process Programs Journal                |
              |                             |
              +--------------+--------------+
                             |
                             v
                    Financial Processing
                             |
                             v
                            FIS


             QA / Testing Layer
                     |
        +------------+-------------+
        |            |             |
        v            v             v
    UI Testing   API Testing   Database Testing
        |            |             |
        +------------+-------------+
                     |
                     v
             Integration Testing
                     |
                     v
             End-to-End Testing
                     |
                     v
             Regression Testing
                     |
                     v
              Final Validation
```

The application is designed with clear separation between the frontend, backend, database, external integration, and financial processing components.

Business rules and financial validations will be enforced in the backend rather than relying exclusively on frontend validation.

Testing will be performed at multiple levels to validate individual components as well as complete business workflows.

---

# 4. Development & Quality Assurance Lifecycle

The project will follow a development lifecycle in which development and testing are performed together.

```text
Requirement Analysis
        |
        v
Business Rule Identification
        |
        v
System / Database Design
        |
        v
Backend Development
        |
        v
Frontend Development
        |
        v
Developer Testing
        |
        v
API / Integration Testing
        |
        v
Database Validation
        |
        v
System / End-to-End Testing
        |
        v
Defect Identification
        |
        v
Bug Fix / Code Change
        |
        v
Regression Testing
        |
        v
UAT-Style Validation
        |
        v
Final Verification
```

The same person develops and tests the system, but development testing and QA testing are treated as separate activities.

### Developer Perspective

Developer-level testing will focus on verifying that the implemented code works correctly before considering a feature ready for broader testing.

Examples include:

- Unit testing.
- Function-level testing.
- Service-level testing.
- API endpoint testing.
- Request validation testing.
- Response validation.
- Exception handling.
- Database operation testing.
- Business-rule testing.
- Integration checks.

### QA Perspective

QA activities will focus on validating whether the implemented system behaves according to the intended requirements and business workflows.

Examples include:

- Functional testing.
- Positive testing.
- Negative testing.
- Boundary testing.
- API testing.
- UI testing.
- Database validation.
- Integration testing.
- System testing.
- End-to-end testing.
- Regression testing.
- Exploratory testing.
- UAT-style validation.
- Error-message validation.
- Data consistency verification.

---

# 5. Core Application Modules

## 5.1 Dashboard

The dashboard will provide an overview of operational and financial activities.

Potential indicators include:

- Total customers.
- Active security accounts.
- Active and closed loans.
- Pending loan applications.
- Outstanding installments.
- Payments collected.
- Pending financial processing.
- General Journal transaction summaries.

### Development Scope

- Implement dashboard APIs.
- Retrieve relevant aggregated information.
- Display data through React components.
- Handle loading and error states.

### QA Scope

- Verify dashboard figures against database records.
- Verify correct filtering and aggregation.
- Validate empty-data scenarios.
- Validate loading and error states.
- Verify that displayed totals update after relevant transactions.
- Verify that unauthorized or invalid requests are handled appropriately.

---

# 6. Customer Management

Features:

- Create customer.
- View customer details.
- View all customers.
- Update customer information.
- Search customers.
- Validate customer information.
- Link customers to security and loan accounts.

### Development Testing

- Validate request schemas.
- Test successful customer creation.
- Test database insertion.
- Test retrieval and update operations.
- Test validation errors.
- Test duplicate or invalid data handling.

### QA Testing

- Positive customer creation.
- Missing required fields.
- Invalid field formats.
- Boundary-value testing.
- Duplicate customer scenarios.
- Search functionality.
- Update validation.
- UI form validation.
- API response validation.
- Database record verification.

---

# 7. Security Account Management

Features:

- Create security account.
- View security account details.
- Check account status.
- View available security balance.
- Validate account eligibility before loan disbursement.

An active security account will be required before loan disbursement.

### QA Scenarios

- Create valid security account.
- Attempt creation with invalid customer.
- Verify account status.
- Verify available balance.
- Verify inactive account behavior.
- Verify customer-account relationship.
- Verify database balance.
- Verify UI and API validation consistency.

---

# 8. Security Transaction Management

Features:

- Record security deposits.
- Record permitted withdrawals.
- View transaction history.
- Calculate available security balance.
- Validate transaction amounts.
- Prevent withdrawals that violate applicable balance rules.

### Testing Scope

The system will be tested for:

- Valid deposits.
- Invalid deposits.
- Valid withdrawals.
- Excessive withdrawals.
- Zero or negative transaction amounts.
- Balance calculation.
- Multiple sequential transactions.
- Database transaction consistency.
- Failed transaction rollback.
- Transaction history accuracy.
- Duplicate transaction scenarios.

---

# 9. Loan Application Management

Features:

- Create loan applications.
- View application details.
- Update permitted application information.
- Validate loan principal and required fields.
- View pending applications.
- Track application status.

Proposed statuses:

- Pending
- Approved
- Rejected

### QA Scenarios

- Valid loan application.
- Missing customer.
- Invalid loan amount.
- Invalid status transition.
- Updating restricted information.
- Duplicate application scenarios.
- UI validation.
- API validation.
- Database state verification.

---

# 10. Loan Approval and Rejection

Features:

- Review loan applications.
- Approve eligible applications.
- Reject applications.
- Record approval decisions.
- Validate status transitions.
- Prevent disbursement of unapproved loans.

### Testing

The approval workflow will be tested for:

- Valid approval.
- Valid rejection.
- Approval of nonexistent application.
- Repeated approval.
- Rejection of already processed application.
- Invalid status transitions.
- Attempted disbursement before approval.
- Database status validation.
- UI status consistency.

---

# 11. Loan Account Management

Features:

- Manage eligible loan accounts.
- View loan account details.
- View active and closed loans.
- Track disbursement status.
- View principal and outstanding amounts.
- Close eligible loan accounts.

Financial transaction history will be preserved according to the application's data integrity rules.

---

# 12. Loan Disbursement

The backend will validate the customer's eligibility before disbursing an approved loan.

Required validations:

1. The customer exists.
2. The loan application has been approved.
3. The customer has an active security account.
4. The available security balance satisfies the minimum requirement.
5. The loan has not already been disbursed.
6. The loan amount and related values are valid.

## Minimum Security Balance Rule

The available security balance must be at least **10% of the loan principal**.

```text
Required Security Balance = Loan Principal × 10%
```

Example:

| Item | Amount |
| ---- | ------ |
| Loan Principal | ৳100,000 |
| Required Security Percentage | 10% |
| Minimum Required Security | ৳10,000 |
| Available Security Balance | ৳7,000 |
| Security Shortfall | ৳3,000 |

In this example, the backend must reject the disbursement request.

If the customer does not have an active security account, the backend must return a meaningful validation error.

These validations must be enforced in FastAPI even when a request is submitted directly through an API client.

## Developer Testing

- Test valid disbursement.
- Test service/business-rule logic.
- Test database transaction behavior.
- Test rollback on failure.
- Test duplicate disbursement prevention.
- Test exception handling.

## QA Testing

### Positive Scenarios

- Approved loan with valid security account.
- Security balance exactly equal to required 10%.
- Security balance greater than required amount.

### Negative Scenarios

- Customer does not exist.
- Loan does not exist.
- Loan is not approved.
- No active security account.
- Security balance below 10%.
- Loan already disbursed.
- Invalid loan amount.
- Duplicate disbursement request.

### Boundary Testing

The following boundary conditions will be tested:

- Security balance just below 10%.
- Security balance exactly 10%.
- Security balance just above 10%.
- Minimum and maximum applicable loan amounts.

### Database Validation

After a successful disbursement:

- Loan status will be verified.
- Disbursement record will be verified.
- Relevant financial transaction will be verified.
- Security account data will be verified where applicable.
- Related records will be checked for consistency.

---

# 13. Installment Management

Features:

- Generate installment schedules.
- Calculate installment amounts according to selected repayment rules.
- Assign installment numbers and due dates.
- Track paid and outstanding amounts.
- Identify overdue installments.
- Update installment status following confirmed payments.

The interest calculation, rounding rules, and repayment schedule will be defined during implementation.

### Testing Scope

- Correct installment count.
- Correct due dates.
- Correct installment amounts.
- Rounding validation.
- Invalid loan scenarios.
- Duplicate schedule generation.
- Paid installment behavior.
- Overdue installment behavior.
- Outstanding balance calculation.
- Database record validation.

---

# 14. Loan Transaction Management

Features:

- View loan transactions.
- Maintain repayment history.
- Link payments to relevant loans and installments.
- Track transaction amounts and statuses.
- Validate financial operations.
- Preserve transaction history.

Testing will verify:

- Correct transaction creation.
- Correct transaction amounts.
- Correct loan linkage.
- Correct installment linkage.
- Transaction status.
- Historical data preservation.
- Database consistency.

---

# 15. Financial Accounting Modules

Financial accounting is a core part of this project.

Two dedicated pages will support financial transaction processing and General Journal management.

---

# 16. Process Programs Journal

## Purpose

The **Process Programs Journal** page will initiate and monitor the processing of eligible MIS transactions into FIS.

It represents the operational processing step that transfers applicable transaction information from the Management Information System (MIS) to the Financial Information System (FIS).

## Intended Workflow

```text
MIS Transaction Created
          |
          v
Process Programs Journal
          |
          v
Backend Validation
          |
          v
Financial Posting Processing
          |
          v
FIS Transaction Recorded
          |
          v
Processing Result Displayed
```

## Development Scope

- Implement processing endpoint.
- Identify eligible transactions.
- Validate source transaction.
- Generate appropriate financial posting.
- Record processing result.
- Maintain source-to-FIS traceability.
- Prevent duplicate posting.

## QA Scope

Testing will include:

- Valid MIS transaction processing.
- Invalid MIS transaction.
- Already processed transaction.
- Duplicate processing request.
- Missing source transaction.
- Invalid financial data.
- Processing failure.
- Database rollback.
- Successful FIS posting.
- Source-to-FIS traceability.
- Processing status validation.
- UI result validation.

### Duplicate Processing Test

The same MIS transaction will be submitted more than once.

Expected behavior:

```text
First Request
     |
     v
Successful Processing
     |
     v
FIS Posting Created

Second Request
     |
     v
Duplicate Detection
     |
     v
No Duplicate Financial Posting
```

---

# 17. General Journal

The **General Journal** page will display General Journal transactions recorded in the financial system.

It will also provide access to the manual journal-entry workflow.

## General Journal Page

The page will provide:

- View General Journal transactions.
- Refresh transaction information.
- Display journal references.
- Display transaction dates.
- Display transaction descriptions.
- Display posting status.
- View relevant debit and credit information.
- Open transaction details.
- Access the New General Journal page through the Add button.

## QA Testing

- Verify transaction listing.
- Verify transaction details.
- Verify debit and credit values.
- Verify posting status.
- Verify transaction reference.
- Verify filtering and search where implemented.
- Verify newly posted journals appear correctly.
- Verify database records against UI.

---

# 18. New General Journal — Manual Posting

The New General Journal page will allow a user to create a General Journal entry through manual financial posting.

This is distinct from automated MIS-to-FIS processing.

## Intended Workflow

```text
General Journal Page
          |
          v
       Add Button
          |
          v
 New General Journal Page
          |
          v
 Enter Journal Information
          |
          v
 Validate Journal Entries
          |
          v
       Save / Post
          |
          v
 General Journal Transaction
```

## Essential Financial Validation

### Required Fields

The journal must contain all required transaction information.

### Valid Accounts

Journal entries must reference valid accounts from the configured account structure.

### Positive Amounts

Invalid or non-positive posting amounts must be rejected where they are not permitted.

### Balanced Journal

For a balanced double-entry journal:

```text
Total Debit = Total Credit
```

Example:

| Account | Debit | Credit |
| ------- | ----- | ------ |
| Cash Account | ৳10,000 | — |
| Loan Repayment Account | — | ৳10,000 |
| **Total** | **৳10,000** | **৳10,000** |

## QA Scenarios

### Positive

- Valid single-line journal where supported.
- Valid multi-line journal.
- Balanced debit and credit.
- Valid account references.
- Successful posting.

### Negative

- Missing required field.
- Invalid account.
- Zero amount.
- Negative amount.
- Unbalanced journal.
- Duplicate submission.
- Invalid status transition.
- Attempt to modify posted transaction.

### Boundary Testing

- Minimum permitted amount.
- Maximum permitted amount where applicable.
- Debit equal to credit.
- Debit differing from credit by the smallest permitted unit.

### Database Validation

After posting:

- Journal header will be verified.
- Journal lines will be verified.
- Debit total will be verified.
- Credit total will be verified.
- Posting status will be verified.
- Transaction reference will be verified.
- Database transaction consistency will be checked.

---

# 19. Payment Management and External API Integration

The payment module will process installment payments through a separate mock payment gateway.

## Intended Workflow

```text
User Selects Installment
          |
          v
React Frontend
          |
          v
FastAPI Payment Endpoint
          |
          v
Payment Validation
          |
          v
Payment Record
          |
          v
HTTPX
          |
          v
Mock Payment Gateway
          |
          v
Gateway Response
          |
          v
Backend Response Processing
          |
          v
Payment Status Update
          |
          v
Installment / Loan Balance Update
          |
          v
Frontend Result
```

## Expected Capabilities

- JSON request and response handling.
- HTTP status-code validation.
- Successful payment scenarios.
- Failed payment scenarios.
- Timeout handling.
- Connection error handling.
- External transaction reference storage.
- Duplicate payment protection.
- Appropriate database transaction management.

## Developer Testing

- Test payment service logic.
- Mock external gateway responses.
- Test successful response handling.
- Test failed response handling.
- Test timeout exceptions.
- Test connection exceptions.
- Test database commit and rollback.

## QA Testing

### Positive Testing

- Valid installment payment.
- Successful gateway response.
- Correct payment status.
- Correct installment update.
- Correct outstanding balance.

### Negative Testing

- Invalid installment.
- Already-paid installment.
- Invalid payment amount.
- Gateway rejection.
- Gateway timeout.
- Gateway connection failure.
- Invalid gateway response.
- Duplicate payment request.

### Integration Testing

Verify:

```text
Frontend
   ↓
FastAPI
   ↓
Payment Service
   ↓
HTTPX
   ↓
Mock Gateway
   ↓
Response
   ↓
Database Update
   ↓
Frontend Status
```

### Important Failure Scenario

A timeout does not necessarily mean that an external service failed to process a payment.

The application will therefore test uncertain payment outcomes and avoid incorrectly marking a payment as failed solely because a timeout occurred.

The mock gateway is for development and demonstration, not real financial transactions.

---

# 20. Frontend Development and UI Testing

The React frontend will provide the user interface for the complete application.

## Frontend Development Scope

- Page development.
- Form development.
- API integration.
- Data tables.
- Search and filtering.
- Validation messages.
- Loading states.
- Error states.
- Transaction status display.
- Navigation between workflows.
- Financial journal interfaces.

## UI Testing Scope

Each major frontend workflow will be tested for:

### Functional Behavior

- Correct page loading.
- Correct navigation.
- Correct form submission.
- Correct API communication.
- Correct success response display.
- Correct error response display.

### Form Validation

- Required fields.
- Invalid input.
- Boundary values.
- Incorrect formats.
- Invalid financial amounts.
- Duplicate submission behavior.

### UI/API Consistency

The UI will be compared against the actual API response to verify that:

- Correct values are displayed.
- Correct status is displayed.
- Error messages correspond to backend validation.
- Updated records appear correctly.

### UI/Database Verification

Where appropriate, frontend results will be cross-checked with database records.

---

# 21. API Testing

API testing will be performed using **Postman** and automated test cases using **Pytest**.

## API Testing Coverage

- Request validation.
- Response validation.
- HTTP status codes.
- JSON structure.
- Required fields.
- Invalid inputs.
- Boundary values.
- Business-rule validation.
- Authentication/authorization where implemented.
- Error handling.
- Duplicate request handling.
- Database state after API operations.

## HTTP Status Validation

Examples include:

| Scenario | Expected Response |
| -------- | ----------------- |
| Successful creation | 201 |
| Successful retrieval | 200 |
| Successful update | 200 |
| Successful deletion where supported | 200 / 204 |
| Invalid request | 400 / 422 |
| Resource not found | 404 |
| Duplicate/conflicting operation | 409 where applicable |
| Server-side failure | 500 |

The exact status code will depend on the implemented API contract.

---

# 22. Database Testing and Validation

PostgreSQL will be used not only as the application database but also as an important validation point during testing.

## Database QA Scope

Testing will verify:

- Record creation.
- Record updates.
- Record deletion where permitted.
- Primary-key relationships.
- Foreign-key relationships.
- Referential integrity.
- Financial transaction consistency.
- Balance calculations.
- Loan outstanding amounts.
- Payment records.
- Journal records.
- MIS-to-FIS references.
- Duplicate transaction prevention.

## Database Verification Examples

After an API operation:

```text
API Request
    |
    v
Backend Processing
    |
    v
Database Update
    |
    v
SQL Query Verification
    |
    v
Expected vs Actual Data
```

Database validation may be performed using SQL queries and PostgreSQL tools.

---

# 23. Testing Strategy

The project will use a layered testing strategy.

## 23.1 Unit Testing

Focus:

- Individual functions.
- Business rules.
- Calculations.
- Validation logic.
- Utility functions.
- Service-level logic.

Examples:

- Security requirement calculation.
- Installment calculation.
- Journal balancing.
- Payment validation.

---

## 23.2 Developer Testing

Developer testing will be performed before considering functionality ready for broader QA validation.

Coverage includes:

- Unit tests.
- API endpoint checks.
- Database operation checks.
- Service-level tests.
- Exception handling.
- Integration checks.
- Business-rule verification.

The objective is to identify implementation defects early.

---

## 23.3 API Testing

Using Postman and automated Pytest tests:

- Endpoint functionality.
- Request validation.
- Response validation.
- HTTP status codes.
- Error responses.
- Business rules.
- Database side effects.

---

## 23.4 Functional Testing

Functional testing will verify that each implemented feature behaves according to its intended requirements.

Examples:

- Customer creation.
- Security account creation.
- Loan application.
- Loan approval.
- Loan disbursement.
- Installment generation.
- Payment.
- General Journal creation.
- MIS-to-FIS processing.

---

## 23.5 Integration Testing

Integration testing will verify interactions between components.

Examples:

```text
React → FastAPI
FastAPI → PostgreSQL
FastAPI → Payment Gateway
MIS → Process Programs Journal → FIS
General Journal → PostgreSQL
Payment → Installment → Loan Balance
```

---

## 23.6 System Testing

System testing will validate the complete application as an integrated system.

The test will cover complete business workflows rather than isolated endpoints.

---

## 23.7 End-to-End Testing

A complete loan lifecycle will be tested from beginning to end.

```text
Customer
   ↓
Security Account
   ↓
Security Deposit
   ↓
Loan Application
   ↓
Loan Approval
   ↓
Security Validation
   ↓
Loan Disbursement
   ↓
Installment Generation
   ↓
Payment
   ↓
Payment Gateway
   ↓
Payment Confirmation
   ↓
MIS Transaction
   ↓
Process Programs Journal
   ↓
FIS Processing
   ↓
General Journal
```

The objective is to verify that the complete workflow operates correctly across the frontend, backend, database, and integration layers.

---

# 24. Negative Testing

Negative testing will be an important part of the QA process.

Examples include:

- Missing required fields.
- Invalid data types.
- Invalid formats.
- Nonexistent customer.
- Nonexistent loan.
- Nonexistent installment.
- Inactive security account.
- Insufficient security balance.
- Unapproved loan disbursement.
- Duplicate disbursement.
- Duplicate payment.
- Invalid payment amount.
- Failed payment gateway.
- Gateway timeout.
- Invalid gateway response.
- Unbalanced journal.
- Invalid account.
- Duplicate financial posting.
- Invalid transaction status.
- Invalid state transition.

The objective is to verify that invalid operations are rejected safely and produce meaningful responses.

---

# 25. Boundary and Edge-Case Testing

Boundary testing will be applied to important financial and business values.

Examples:

- Security balance just below 10%.
- Security balance exactly 10%.
- Security balance just above 10%.
- Minimum loan amount.
- Maximum permitted loan amount.
- Minimum payment amount.
- Payment equal to outstanding amount.
- Payment exceeding outstanding amount.
- Zero amount.
- Negative amount.
- Empty input.
- Maximum supported input length.

Edge cases will also include:

- Repeated requests.
- Concurrent-like duplicate requests where applicable.
- Failed database operations.
- External API timeout.
- Partial workflow failure.
- Unexpected external API responses.

---

# 26. Regression Testing

Regression testing will be performed after defect fixes or changes to important business logic.

Examples:

```text
Bug Found
   ↓
Root Cause Investigation
   ↓
Code Fix
   ↓
Retest Failed Scenario
   ↓
Regression Test Related Features
   ↓
Regression Test Complete Workflow
```

Regression coverage will focus particularly on financial workflows because changes to one transaction process may affect related balances, journal entries, and transaction history.

---

# 27. Exploratory Testing

Exploratory testing may be performed in addition to predefined test cases.

The purpose is to identify unexpected behavior that may not be covered by formal scenarios.

Areas may include:

- Unexpected navigation.
- Repeated button clicks.
- Rapid duplicate submission.
- Unexpected input combinations.
- Browser refresh during workflows.
- Invalid workflow sequences.
- Unexpected API responses.
- Data consistency after failed operations.

Findings will be documented and converted into repeatable test cases where appropriate.

---

# 28. UAT-Style Validation

Major business workflows will be validated from an end-user perspective.

Examples:

### Loan Workflow

```text
Create Customer
      ↓
Create Security Account
      ↓
Deposit Security
      ↓
Apply for Loan
      ↓
Approve Loan
      ↓
Disburse Loan
      ↓
Generate Installments
      ↓
Collect Payment
```

### Financial Workflow

```text
Operational Transaction
      ↓
Process Programs Journal
      ↓
MIS Validation
      ↓
FIS Processing
      ↓
Financial Journal
      ↓
Transaction Verification
```

### Manual Journal Workflow

```text
General Journal
      ↓
Add
      ↓
New General Journal
      ↓
Enter Debit/Credit
      ↓
Validate
      ↓
Post
      ↓
Verify General Journal
```

The purpose is to verify that the application supports the intended user workflows rather than only individual technical functions.

---

# 29. Defect Management

Defects identified during development or QA testing will be investigated and tracked.

A defect record may contain:

- Defect ID.
- Summary.
- Module.
- Environment.
- Preconditions.
- Steps to reproduce.
- Test data.
- Expected result.
- Actual result.
- Severity.
- Priority.
- Status.
- Root cause where identified.
- Fix details.
- Retest result.

Example defect lifecycle:

```text
New
 ↓
Analysis
 ↓
Fixed
 ↓
Retest
 ↓
Passed
```

If the defect remains unresolved:

```text
Retest
   ↓
Failed
   ↓
Reopened
   ↓
Fix
   ↓
Retest
```

---

# 30. Test Data and Environment Validation

Testing will use controlled test data representing different business conditions.

Examples:

- Customer with active security account.
- Customer without security account.
- Customer with insufficient security balance.
- Customer with sufficient security balance.
- Approved loan.
- Pending loan.
- Rejected loan.
- Already-disbursed loan.
- Outstanding installment.
- Paid installment.
- Failed payment.
- Successful payment.
- Unprocessed MIS transaction.
- Already-processed MIS transaction.
- Balanced journal.
- Unbalanced journal.

Testing will verify that different data states produce the expected application behavior.

---

# 31. Financial Data Integrity

Because this is a financial application, data integrity will be treated as a major quality requirement.

The system will aim to ensure:

- No partial financial posting.
- No duplicate financial posting.
- No invalid balance updates.
- No unauthorized modification of posted financial history.
- Consistent transaction relationships.
- Proper commit and rollback behavior.
- Traceability between operational and financial transactions.

Important financial operations will use appropriate database transaction handling.

---

# 32. Test Automation

Pytest will be used to automate repeatable backend and API tests.

Potential automated coverage includes:

- Customer API.
- Security account API.
- Security transaction API.
- Loan application API.
- Loan approval API.
- Loan disbursement API.
- Installment API.
- Payment API.
- General Journal API.
- MIS-to-FIS processing API.

Automated tests will include both positive and negative scenarios.

Examples:

```text
Valid Request
      ↓
Expected Success
```

and:

```text
Invalid Request
      ↓
Expected Validation Error
```

Automated tests will also verify important business rules and database outcomes.

---

# 33. Test Coverage Areas

| Area | Development | QA |
| ---- | ----------- | --- |
| Python Backend | ✓ | ✓ |
| FastAPI APIs | ✓ | ✓ |
| React UI | ✓ | ✓ |
| PostgreSQL | ✓ | ✓ |
| Business Logic | ✓ | ✓ |
| API Validation | ✓ | ✓ |
| Database Validation | ✓ | ✓ |
| External API Integration | ✓ | ✓ |
| Financial Rules | ✓ | ✓ |
| Positive Testing | ✓ | ✓ |
| Negative Testing | ✓ | ✓ |
| Boundary Testing | ✓ | ✓ |
| Integration Testing | ✓ | ✓ |
| End-to-End Testing | ✓ | ✓ |
| Regression Testing | — | ✓ |
| Exploratory Testing | — | ✓ |
| UAT-Style Testing | — | ✓ |
| Automated Testing | ✓ | ✓ |
| Defect Investigation | ✓ | ✓ |
| Retesting | — | ✓ |

This separation represents the testing perspective rather than separate team members. The project is developed and tested by the same developer.

---

# 34. Frontend Pages

The React frontend will include the following pages:

| Page | Main Purpose |
| ---- | ------------ |
| Dashboard | Operational and financial summary |
| Customer Management | Customer records |
| Security Account | Security account management |
| Security Transactions | Deposits, withdrawals, and balances |
| Loan Applications | Application management |
| Loan Approval | Approval and rejection |
| Loan Accounts | Loan account management |
| Loan Disbursement | Disbursement and eligibility validation |
| Installments | Due, paid, and overdue installments |
| Loan Transactions | Loan transaction history |
| Payments | Payment initiation and status |
| Process Programs Journal | MIS-to-FIS transaction processing |
| General Journal | View General Journal transactions |
| New General Journal | Manual journal entry and posting |
| Reports | Operational and financial summaries |

The UI will remain simple and functional, with priority given to workflow correctness, business-rule enforcement, data consistency, and testability.

---

# 35. Database Design

The application will use PostgreSQL to maintain operational and financial records.

## Core Operational Entities

- Customer
- Security Account
- Security Transaction
- Loan Application
- Loan Account
- Loan Disbursement
- Installment
- Payment Transaction

## Financial Accounting Entities

The accounting implementation is expected to require entities such as:

- Financial Account / Chart of Accounts.
- General Journal Header.
- General Journal Lines.
- MIS Transaction Processing Record.
- Financial Posting Reference.

The final entity names and relationships will be established during implementation.

## General Journal Structure

A General Journal will typically require a journal header and associated journal lines.

### Journal Header

Contains information shared by the journal, such as:

- Reference.
- Date.
- Description.
- Status.

### Journal Lines

Contain:

- Account.
- Debit.
- Credit.
- Supporting information.

This structure supports multiple journal lines while preserving the overall journal transaction.

## MIS-to-FIS Traceability

The financial processing workflow should retain the relationship between the originating MIS transaction and the resulting financial posting.

The system should record sufficient information to identify:

- Source transaction.
- Processing attempt.
- Processing result.
- Resulting journal or financial reference.
- Processing status.

This supports error investigation and duplicate-posting prevention.

---

# 36. Backend Engineering Scope

The project emphasizes practical Python backend engineering.

## API Development

- RESTful endpoint design.
- Request and response validation.
- Appropriate HTTP status codes.
- Error handling.
- Pagination and filtering where useful.

## Database Engineering

- PostgreSQL schema design.
- SQLAlchemy models and relationships.
- Primary and foreign keys.
- Constraints and indexes where appropriate.
- Database sessions.
- Alembic migrations.

## Financial Business Logic

- Loan eligibility validation.
- Security balance calculation.
- Loan disbursement rules.
- Installment generation.
- Payment processing.
- MIS-to-FIS processing.
- General Journal validation.
- Balanced debit and credit validation.
- Controlled financial posting.

## Data Integrity

- Database transactions.
- Commit and rollback.
- Duplicate processing protection.
- Financial history preservation.
- Consistent updates across related records.

## External API Integration

- HTTPX requests.
- JSON response handling.
- HTTP status validation.
- Timeout and connection error handling.
- External transaction reference management.
- Idempotency and safe retry considerations.

---

# 37. Software Quality Assurance Scope

This project also emphasizes practical Software Quality Assurance activities across the complete application.

## Requirement-Based Testing

Requirements and business rules will be converted into:

- Test scenarios.
- Test cases.
- Expected results.
- Positive cases.
- Negative cases.
- Boundary cases.

## Functional Testing

Each feature will be validated against its intended functional behavior.

## API Testing

- REST API requests.
- JSON validation.
- Response validation.
- HTTP status codes.
- Error handling.
- Business-rule validation.

## Database Testing

- Data persistence.
- Data retrieval.
- Relationships.
- Constraints.
- Financial calculations.
- Transaction consistency.

## Integration Testing

Testing interactions between:

- React and FastAPI.
- FastAPI and PostgreSQL.
- FastAPI and payment gateway.
- MIS and FIS processing.
- Payment and installment modules.
- Financial journal and source transactions.

## System Testing

Complete application functionality will be validated after integrating major components.

## End-to-End Testing

Complete business workflows will be tested from UI action through backend processing and database results.

## Regression Testing

Previously validated functionality will be re-tested after relevant code changes.

## Exploratory Testing

The application will be explored beyond predefined test cases to identify unexpected behavior.

## UAT-Style Testing

Business workflows will be validated from the perspective of an end user.

## Automated Testing

Repeatable backend and API scenarios will be automated using Pytest.

---

# 38. Testing Artifacts

The project may maintain testing artifacts such as:

- Test scenarios.
- Test cases.
- Test data.
- API collections.
- Automated test scripts.
- Defect reports.
- Retest results.
- Regression test cases.
- UAT-style scenarios.
- Expected vs actual results.

These artifacts will be maintained as the project evolves.

---

# 39. Proposed Project Structure

```text
microfinance-loan-management-system/
│
├── backend/
│   ├── app/
│   │   ├── core/
│   │   ├── db/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── routers/
│   │   ├── services/
│   │   ├── repositories/
│   │   ├── integrations/
│   │   └── main.py
│   │
│   ├── tests/
│   │   ├── unit/
│   │   ├── api/
│   │   ├── integration/
│   │   └── business_rules/
│   │
│   ├── alembic/
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── App.jsx
│   └── package.json
│
├── mock-payment-gateway/
│   └── app/
│
├── tests/
│   ├── test-cases/
│   ├── test-data/
│   └── test-documentation/
│
├── .gitignore
└── README.md
```

The structure will evolve as the project develops. Only modules required for the actual implementation will be created.

---

# 40. Setup and Installation

## Prerequisites

- Python.
- Node.js and npm.
- PostgreSQL.
- Git.

## Clone the Repository

```bash
git clone https://github.com/rhidoybiswas/microfinance-loan-management-system.git
cd microfinance-loan-management-system
```

## Backend Setup

```bash
cd backend
python -m venv venv
```

Activate the virtual environment.

### Windows PowerShell

```powershell
.\venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Environment Configuration

Create a `.env` file in the backend directory.

Example:

```text
DATABASE_URL=postgresql+psycopg2://username:password@localhost:5432/microfinance_db
PAYMENT_GATEWAY_URL=http://127.0.0.1:8001
```

Use the database credentials configured on your own machine.

Never commit real credentials or secrets to the public repository.

## Run the Backend

From the backend directory:

```bash
uvicorn app.main:app --reload
```

Interactive API documentation:

```text
http://127.0.0.1:8000/docs
```

## Run the Frontend

From the frontend directory:

```bash
npm install
npm run dev
```

Vite will display the local development URL.

The mock payment gateway will run as a separate service.

**Note:** The commands and environment variables above describe the intended setup and must be verified against the final implementation before the repository is considered fully runnable.

---

# 41. Development Roadmap

## Phase 1 — Project Setup

- Configure Python environment.
- Configure PostgreSQL.
- Establish FastAPI application.
- Configure SQLAlchemy.
- Configure Alembic.
- Establish React frontend.
- Establish Git repository.

## Phase 2 — Core Operational Backend

- Customer management.
- Security account management.
- Security transactions.
- Loan applications.
- Loan approval.
- Loan disbursement.
- Installment generation.

## Phase 3 — Financial Accounting

- Define financial account structure.
- Design General Journal Header and Lines.
- Implement General Journal viewing.
- Implement New General Journal.
- Implement debit-credit balancing.
- Implement Process Programs Journal.
- Implement MIS-to-FIS processing.
- Add duplicate posting protection.
- Add processing history.

## Phase 4 — Payment Integration

- Create mock payment gateway.
- Implement HTTPX communication.
- Handle successful responses.
- Handle failed responses.
- Handle timeout and connection errors.
- Implement duplicate payment protection.

## Phase 5 — React Frontend

- Create application pages.
- Connect frontend to FastAPI.
- Implement forms.
- Implement tables.
- Implement validation messages.
- Build journal interfaces.
- Implement complete user workflows.

## Phase 6 — Developer Testing

- Unit tests.
- Business-rule tests.
- API tests.
- Database operation tests.
- Service-level tests.
- Integration checks.

## Phase 7 — QA Testing

- Test scenario preparation.
- Functional testing.
- API testing.
- Database validation.
- Positive testing.
- Negative testing.
- Boundary testing.
- Integration testing.
- System testing.
- End-to-end testing.
- Exploratory testing.
- UAT-style testing.
- Regression testing.

## Phase 8 — Defect Fixing and Retesting

- Defect identification.
- Root-cause investigation.
- Code fixes.
- Retesting.
- Regression testing.
- Final verification.

## Phase 9 — Final Validation and Documentation

- Validate complete loan lifecycle.
- Validate financial processing.
- Validate database consistency.
- Verify automated tests.
- Verify API collection.
- Finalize documentation.
- Verify README instructions.
- Prepare GitHub repository.

---

# 42. Future Enhancements

Potential future improvements include:

- Authentication.
- Role-based authorization.
- Approval workflows for manual journal posting.
- Reversal and adjustment journal workflows.
- Advanced financial reporting.
- Payment reconciliation.
- Audit logging.
- Docker-based development.
- CI/CD pipeline.
- Cloud deployment.
- Automated regression pipeline.
- Test reporting.
- Performance testing.
- Security testing.

---

# 43. Project Development & QA Principles

The project follows these principles:

1. Requirements should be translated into testable behavior.
2. Business rules must be enforced in the backend.
3. Frontend validation must not replace backend validation.
4. Database consistency must be maintained during financial operations.
5. Financial transaction history must be preserved.
6. Duplicate financial processing must be prevented.
7. External API failures must be handled carefully.
8. Positive and negative scenarios must both be tested.
9. Boundary and edge cases should be considered for important business rules.
10. Changes should be followed by appropriate regression testing.
11. Automated tests should cover important and repeatable business rules.
12. UI behavior should be validated against backend responses.
13. Database records should be verified for important financial operations.
14. Defects should be reproduced, fixed, retested, and regression-tested.
15. Documentation should reflect the actual implementation.

---

# 44. Author

**Rhidoy Biswas**

GitHub: https://github.com/rhidoybiswas

---

# 45. Project Objective

The objective of this project is to build and validate a realistic financial application that demonstrates both **software engineering and software quality assurance capabilities**.

From the development perspective, the project demonstrates:

- Python backend engineering.
- FastAPI REST API development.
- PostgreSQL database management.
- SQLAlchemy ORM.
- React frontend development.
- REST API integration.
- External API integration.
- Financial business logic.
- Database transaction management.

From the QA perspective, the project demonstrates:

- Requirement-based testing.
- Test scenario and test case design.
- Functional testing.
- API testing.
- Postman testing.
- Database validation.
- Positive and negative testing.
- Boundary and edge-case testing.
- Integration testing.
- System testing.
- End-to-end testing.
- Regression testing.
- Exploratory testing.
- UAT-style validation.
- Automated testing with Pytest.
- Defect investigation and retesting.
- Financial data integrity validation.

The project is intended to demonstrate the ability to **build, test, investigate, validate, and continuously improve a complete software system**, rather than focusing exclusively on either development or testing.