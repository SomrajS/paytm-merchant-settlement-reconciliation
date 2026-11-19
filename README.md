# Paytm Merchant Settlement and Reconciliation Control System

<p align="center">
  <strong>SQL Developer Project | FinTech | Database Engineering | Financial Reconciliation</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/SQL-SQLite-blue?style=for-the-badge&logo=sqlite" alt="SQL">
  <img src="https://img.shields.io/badge/Python-3.x-yellow?style=for-the-badge&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Google%20Colab-orange?style=for-the-badge&logo=googlecolab" alt="Google Colab">
  <img src="https://img.shields.io/badge/Domain-FinTech-green?style=for-the-badge" alt="FinTech">
</p>

## 1. Project Overview

The **Paytm Merchant Settlement and Reconciliation Control System** is an independent SQL Developer project built around a simulated FinTech payment-processing environment.

The project demonstrates how merchant transactions, refunds, settlement batches, and bank credits can be managed, analyzed, and reconciled using SQL and relational database concepts.

It combines database design, REST API consumption, SQL analytics, transaction management, reconciliation exception detection, and workflow automation concepts in a structured Jupyter Notebook environment.

The project uses synthetic financial data and a locally simulated REST API to demonstrate practical database development and financial operations workflows.

## 2. Business Problem

Digital payment platforms process large volumes of merchant transactions across multiple payment methods.

After processing payments, the corresponding settlement amounts must be calculated and credited to merchant bank accounts. Differences between expected settlement amounts and actual bank credits can create reconciliation problems.

Common operational issues include:

- Missing bank credits.
- Settlement amount mismatches.
- Duplicate bank references.
- Delayed settlements.
- Incorrect transaction fees.
- Overdue unsettled transactions.
- Unresolved reconciliation exceptions.

This project demonstrates a database-driven approach to identifying, analyzing, and reporting such discrepancies.

## 3. Project Objectives

- Design a relational database for merchant payment operations.
- Extract and validate operational data through REST API requests.
- Develop SQL queries for financial and merchant analysis.
- Reconcile settlement records against bank credit information.
- Identify missing, mismatched, and delayed settlements.
- Maintain merchant ledger records.
- Demonstrate SQL transaction control using COMMIT and ROLLBACK.
- Generate reconciliation exception reports.
- Design automated data processing and reporting workflows.
- Understand Git collaboration and safe database change practices.

## 4. Technology Stack

| Technology | Purpose |
|---|---|
| SQL | Database querying and financial reconciliation |
| SQLite | Relational database management |
| Python 3 | Data generation and API integration |
| Pandas | Data processing and validation |
| Requests | REST API consumption |
| Jupyter Notebook | Project development environment |
| Google Colab | Cloud-based notebook execution |
| Graphviz | ER diagrams and workflow visualization |
| Git & GitHub | Version control and project hosting |

## 5. Database Architecture

The project implements a relational database consisting of **10 SQLite tables**.

| Table | Purpose |
|---|---|
| `merchants` | Merchant details and settlement configuration |
| `fee_rules` | Payment method fees and tax rules |
| `transactions` | Merchant payment transaction records |
| `refunds` | Refund records and their statuses |
| `settlement_batches` | Merchant settlement batch information |
| `settlement_items` | Transactions associated with settlement batches |
| `bank_credits` | Bank credit and settlement confirmation records |
| `merchant_ledger` | Merchant financial ledger entries |
| `reconciliation_exceptions` | Detected financial discrepancies and their status |
| `api_ingestion_runs` | API extraction and ingestion execution logs |

### Database Relationships

- One merchant can have multiple transactions.
- One merchant can have multiple settlement batches.
- Fee rules are associated with payment methods.
- One transaction can have multiple refund attempts.
- Settlement batches contain settlement items.
- Bank credit records reference settlement batches and merchants.
- Merchant ledger entries reference merchants and may reference transactions or settlements.
- Reconciliation exceptions can reference merchants.
- API ingestion records track data extraction and loading activities.

The notebook creates an Entity Relationship diagram to visualize the database structure.

## 6. Project Modules

### Module 1: Synthetic Data Generation

Created a simulated FinTech dataset containing:

- 50 merchants.
- 1,200 payment transactions.
- Refund records.
- Settlement batches.
- Settlement items.
- Bank credit records.
- Merchant fee rules.

Supported payment methods:

- UPI
- CARD
- WALLET
- NET_BANKING

The dataset includes deliberately introduced discrepancies to support reconciliation and exception-detection exercises.

### Module 2: REST API Integration

Developed a temporary internal REST API simulator using Python's built-in HTTP server.

Implemented API data extraction with:

- HTTP GET requests.
- Paginated data retrieval.
- Response validation.
- JSON data storage.
- Ingestion metadata tracking.

The simulated API provides merchant, transaction, refund, settlement, settlement-item, and bank-credit resources.

### Module 3: Database Design and Management

- Designed 10 relational database tables.
- Implemented primary and foreign key constraints.
- Applied data validation and integrity rules.
- Created database indexes.
- Established relationships between merchant, transaction, refund, and settlement records.
- Generated an ER diagram using Graphviz.

### Module 4: REST API Operations

Practiced the five major HTTP methods:

| HTTP Method | Operation |
|---|---|
| GET | Retrieve transaction records |
| POST | Create a new transaction |
| PUT | Replace an existing transaction |
| PATCH | Update selected transaction fields |
| DELETE | Delete a transaction and verify removal |

### Module 5: SQL Development and Analysis

Completed 13 SQL business challenges covering:

**SQL Fundamentals**
- SELECT, WHERE, and ORDER BY.
- INNER JOIN and LEFT JOIN.
- GROUP BY and HAVING.
- Aggregate functions.
- UNION and INTERSECT.

**Intermediate and Advanced SQL**
- Subqueries.
- Common Table Expressions (CTEs).
- CASE statements.
- NULL handling.
- String and date functions.

**SQL Window Functions**
- ROW_NUMBER().
- RANK().
- DENSE_RANK().
- PARTITION BY.
- LAG().
- Running totals.
- Seven-day moving averages.

The exercises focus on merchant performance, transaction analysis, settlement discrepancies, and exception monitoring.

### Module 6: Merchant Settlement and Reconciliation

Developed SQL-based reconciliation analysis to compare expected settlement amounts against actual bank credits.

The exercises cover:

- Settlement amount verification.
- Expected versus credited amount comparison.
- Missing bank credit identification.
- Settlement variance analysis.
- Reconciliation status classification.
- Duplicate bank reference investigation.
- Delayed and overdue settlement identification.

A ₹0.02 tolerance is used for settlement amount comparisons.

### Module 7: Transaction Management

Demonstrated SQL transaction control using:

- BEGIN.
- INSERT.
- COMMIT.
- ROLLBACK.

Two practical exercises demonstrate:

1. Committing an approved manual merchant ledger adjustment.
2. Rolling back an unapproved temporary ledger adjustment.

The notebook validates both the transaction sequence and final database persistence state.

### Module 8: Workflow Automation

Designed a daily merchant reconciliation workflow covering seven stages:

1. Scheduled execution.
2. API data extraction.
3. Response validation.
4. Raw JSON storage.
5. Validated data loading into SQLite.
6. Reconciliation exception recalculation and reporting.
7. Execution logging and monitoring.

Additional exercises include:

- Automated SQL exception reporting.
- Cron expression validation.
- Workflow architecture visualization.

**Note:** These are workflow design and validation exercises. A live production scheduler is not deployed by the notebook.

### Module 9: Engineering Practices

Demonstrated professional software and database engineering workflows.

**Git Collaboration**
- Requirement analysis.
- Feature branch creation.
- SQL development.
- Testing and validation.
- Git commits and pushes.
- Pull requests and peer reviews.
- Merging approved changes.

**Safe Database Change Management**
- Requirement analysis.
- Backup preparation.
- Rollback planning.
- SQL migration scripting.
- Development environment testing.
- Peer review.
- Deployment monitoring.
- Rollback procedures.

## 7. How to Run the Project

The project is designed to run using Google Colab.

**Step 1: Open the Notebook**

Open the `.ipynb` file in Google Colab.

**Step 2: Execute Setup**

Select:

`Runtime → Run all`

**Step 3: Verify Setup**

Wait until the green `SETUP COMPLETE` message appears.

The notebook automatically prepares:

- Synthetic datasets.
- Temporary internal REST API.
- Raw and processed data directories.
- SQLite database.
- Reconciliation exception engine.
- SQL validation helpers.
- ER and workflow diagram helpers.

**Step 4: Navigate to Developer Exercises**

Scroll to:

`SQL DEVELOPER WORK STARTS HERE`

**Step 5: Complete the Exercises**

Work through the following sections:

1. Database Design and ER Visualization.
2. API Operations.
3. SQL Developer Questions (Q1–Q13).
4. Transaction Management (T1–T2).
5. Workflow Automation.
6. Engineering Practices.

**Step 6: Validate Your Work**

Run the progress-check cell to review completed and pending exercises.

The validation framework displays whether individual exercises have passed.

## 8. Project Structure

The notebook generates the following project directories during execution:

```text
paytm_sql_project_developer/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── database/
│   └── paytm_reconciliation.db
│
├── logs/
│
└── reports/
```

The main GitHub repository contains the Jupyter Notebook and project documentation.

## 9. Key Learning Outcomes

- Relational database design and data modeling.
- Writing complex SQL queries.
- SQL joins, CTEs, and window functions.
- Merchant payment and settlement analysis.
- Financial reconciliation and exception detection.
- REST API integration and pagination.
- Data validation and database integrity.
- SQL transaction management.
- Workflow automation design.
- Cron scheduling concepts.
- Git collaboration and database change management.

## 10. Future Enhancements

Potential future improvements include:

- Interactive financial reconciliation dashboards.
- Integration with a production-grade relational database.
- Live API integration.
- Scheduled execution using a workflow orchestrator.
- Automated exception notifications.
- Advanced transaction monitoring.
- Role-based access control.
- Production-grade logging and audit trails.

## 11. Disclaimer

This is an independent educational project developed using synthetic financial data and a locally simulated internal REST API.

It is not an official Paytm product, does not connect to Paytm's production systems, and is not affiliated with or endorsed by Paytm.

## 12. Author

**Somraj Sarkar**

B.Tech in Information Technology  
VIT Vellore

GitHub: [SomrajS](https://github.com/SomrajS)

---

<p align="center">
  <strong>Developed as a practical SQL Developer and FinTech database engineering project.</strong>
</p>
