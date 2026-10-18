# DataLens AI — Ask. Query. Verify.

**An Explainable AI-Powered Data Intelligence Agent Using Snowflake and Google Gemma**

DataLens AI is an AI-powered data analytics platform that enables users to interact with organizational data using natural language. It transforms everyday questions into real data queries, performs analysis on actual records, and delivers evidence-backed answers with transparent explanations.

Instead of requiring users to understand SQL or manually analyse large datasets, DataLens AI makes data accessible through an intelligent, conversational interface while prioritising accuracy, transparency, and trust.

---

## 📌 Problem Statement

Organizations generate and maintain enormous amounts of data across databases, spreadsheets, reports, documents, and other information systems. Extracting meaningful insights from this data often requires technical expertise, specialised SQL queries, and hours of manual analysis.

As a result, the people who understand business problems and decision-making requirements best are often the ones who face the greatest difficulty accessing the information they need.

Traditional chatbots can generate fluent responses but may produce plausible yet unsupported claims. They often fail to demonstrate whether an answer was calculated from actual data, which records were examined, or how the result was obtained.

**The challenge is to develop an AI-powered data experience that allows users to ask questions in everyday language and receive accurate, explainable, and verifiable answers grounded in actual data.**

The system must retrieve, query, or analyse real information at question time, expose the evidence supporting its answers, handle missing or insufficient data responsibly, and reflect changes in the underlying data.

## 💡 Proposed Solution

DataLens AI addresses this challenge by combining **Snowflake's data processing capabilities with Google Gemma's language understanding and reasoning capabilities** to create an intelligent, evidence-driven data analyst.

Users can connect to authorised Snowflake datasets and ask analytical questions in natural language. The system interprets the question, identifies relevant tables and columns, generates a suitable SQL query, validates it, and executes it against the actual Snowflake environment.

The returned records are then analysed to produce a concise answer, relevant calculations, interactive visualisations, and a plain-language explanation. Users can inspect the executed SQL, source tables, result rows, filters, and assumptions to independently verify the response.

Unlike a conventional chatbot, DataLens AI separates AI-generated reasoning from actual data computation. The language model helps interpret and explain; Snowflake retrieves and processes the data; and the application validates the query and grounds the final response in the resulting evidence.

The platform is designed to be modular and reusable, allowing developers to adapt it to different compatible datasets through configuration changes rather than rewriting the core application.

---

## 🎯 Project Objectives

- Enable natural-language interaction with structured data.
- Eliminate the need for users to write SQL manually.
- Integrate Google Gemma for meaningful AI-powered question interpretation and explanation.
- Use Snowflake for real-time analytical query execution.
- Generate answers grounded in actual database results.
- Provide inspectable SQL, source references, and supporting records.
- Explain calculations, filters, assumptions, and data limitations.
- Detect ambiguous questions, missing values, empty results, and unsupported requests.
- Reflect underlying data changes in subsequent queries.
- Deliver a reusable, documented, open-source implementation.

---

## ⚙️ How It Works

1. **Connect Data:** Connect the application to an authorised Snowflake account containing the relevant datasets.
2. **Discover Schema:** Retrieve the available tables, columns, data types, and configured relationships.
3. **Ask a Question:** The user submits a question in everyday language.
4. **AI Interpretation:** Google Gemma interprets the question and proposes an analytical plan or SQL query using the available schema.
5. **Query Validation:** The backend validates the generated SQL, checks permissions, and enforces read-only execution and resource limits.
6. **Real Data Execution:** The validated query executes against Snowflake and retrieves actual records.
7. **Evidence-Based Analysis:** The application calculates the requested metrics and prepares supporting evidence.
8. **Explainable Response:** The system presents the answer with a plain-language explanation, executed SQL, source information, and relevant data rows.
9. **Visualisation:** Charts, summary cards, and tables help users understand the findings.
10. **Updated Insights:** Subsequent queries retrieve current data, ensuring that answers can reflect changes in the underlying dataset.

---

## ✨ Key Features

### 1. Natural-Language Data Queries
Ask analytical questions in everyday English without needing SQL expertise.

### 2. Google Gemma Integration
Use a compatible Google Gemma model for question understanding, query planning, and evidence-grounded explanations.

### 3. Snowflake Integration
Connect to Snowflake to discover authorised data sources, execute SQL queries, and retrieve actual results.

### 4. Explainable AI Responses
Provide explanations of the tables, filters, calculations, assumptions, and limitations involved in producing an answer.

### 5. SQL Transparency
Display the SQL that was actually executed, together with available query metadata and execution status.

### 6. Evidence-Based Results
Show supporting result rows, source tables, and relevant data references so users can verify the response.

### 7. Interactive Analytics
Present appropriate charts, metrics, and data tables generated from actual query results.

### 8. Data Quality Awareness
Identify missing values, empty results, incomplete records, and insufficient information when these affect an answer.

### 9. Intelligent Error Handling
Handle ambiguous questions, unsupported requests, invalid SQL, connection failures, and model inference errors without inventing results.

### 10. Dynamic Data Analysis
Execute new queries against the current Snowflake data so subsequent answers can reflect updated records.

### 11. Secure Query Execution
Use read-only database permissions, query validation, approved table access, execution limits, and secure credential management.

### 12. Reusable Architecture
Support compatible datasets through configurable schemas, table definitions, and metric descriptions.

---

## 🏗️ System Architecture

The application follows a modular architecture:

```text
                 USER
                   |
                   v
        React + TypeScript UI
                   |
                   v
           FastAPI Backend
                   |
                   v
       Question Interpretation
                   |
                   v
        Google Gemma Inference
                   |
                   v
       Schema-Aware SQL Generation
                   |
                   v
          SQL Validation Layer
                   |
                   v
          Snowflake Execution
                   |
                   v
       Actual Query Result Records
                   |
                   v
      Deterministic Result Analysis
                   |
                   v
       Evidence & Explanation Layer
                   |
                   v
      Answers + SQL + Sources + Charts
```

### Architectural Principle

**Gemma interprets and explains. Snowflake retrieves and computes. The backend validates and verifies.**

This separation helps ensure that the system does not confuse plausible AI-generated text with verified analytical results.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|---|---|---|
| Frontend | React.js, TypeScript | Interactive user interface |
| UI Styling | Tailwind CSS | Responsive application design |
| UI Components | shadcn/ui | Accessible interface components |
| Backend | Python, FastAPI | API development and agent orchestration |
| AI Model | Google Gemma 3n E2B/E4B or another compatible Gemma variant | Question interpretation and explanations |
| Data Platform | Snowflake | Data storage, retrieval, and SQL analysis |
| Database Connector | `snowflake-connector-python` | Snowflake connectivity and query execution |
| Data Processing | SQL, Pandas where appropriate | Analytical processing and data quality checks |
| Visualisation | Recharts | Interactive charts |
| Tables | TanStack Table | Sorting and presentation of query results |
| Validation | Pydantic and SQL parsing tools | Structured data validation and SQL safety |
| Testing | Pytest and frontend testing tools | Unit, integration, and application testing |
| Version Control | Git and GitHub | Source management and collaboration |
| Deployment | Docker and a suitable cloud platform | Reproducible deployment |

The selected Gemma model and inference runtime must be verified for compatibility, hardware requirements, and licensing before deployment.

---

## 📋 Mandatory Challenge Requirements

DataLens AI is designed to address all eight mandatory evaluation criteria.

| ID | Requirement | Proposed implementation |
|---|---|---|
| M1 | Natural-language questions | Conversational question interface |
| M2 | Real data retrieval and analysis | Actual Snowflake query execution |
| M3 | Grounded answers | Responses constrained by returned evidence |
| M4 | Plain-language explanation | Calculation, filter, and assumption explanations |
| M5 | Inspectable evidence | Executed SQL, result rows, and source references |
| M6 | Sensible edge-case handling | Ambiguity, missing data, empty results, and errors |
| M7 | Snowflake and Gemma integration | Actual integration of both required technologies |
| M8 | Open-source implementation | Reusable code, documentation, configuration, and tests |

All criteria must be verified through a functioning implementation. Listing a feature in the documentation does not establish that it has been implemented or tested.

---

## 🔍 Example Use Cases

Users can ask questions such as:

- Which products generated the highest revenue this year?
- Compare sales performance across different regions.
- What percentage of total revenue came from each product category?
- Which departments have expenses above the average?
- Identify records containing missing customer identifiers.
- Show the top five customers by total spending.
- Compare sales between two time periods.
- Which datasets lack sufficient information to answer this question?

The application should generate answers from the connected data rather than using hardcoded responses.

---

## 🔐 Security and Reliability

DataLens AI prioritises safe, controlled, and transparent data access.

- Use authorised Snowflake connections and read-only database roles.
- Validate generated SQL before execution.
- Restrict access to approved databases, schemas, tables, and columns.
- Enforce query timeouts and result-size limits.
- Store credentials securely on the backend.
- Avoid exposing secrets in logs, responses, or frontend code.
- Treat user input and retrieved content as untrusted data.
- Distinguish failed queries from successful queries returning zero rows.
- Report missing information instead of inventing unsupported claims.
- Ensure that displayed evidence corresponds to the query actually executed.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11 or a compatible supported version.
- Node.js and npm.
- Access to a configured Snowflake account.
- An authorised Google Gemma model checkpoint and compatible inference runtime.
- Git.
- Suitable hardware or an inference service capable of running the selected model.


## 🧪 Testing and Evaluation

The application should be evaluated using:

- Natural-language questions not seen during development.
- Queries requiring filtering, grouping, aggregation, and comparisons.
- Questions involving missing or insufficient data.
- Empty-result scenarios.
- Invalid or unsafe SQL generation attempts.
- Snowflake connection and query failures.
- Gemma inference failures.
- Source-data changes followed by new queries.
- Independent verification of answers against actual query results.

Important evaluation measures include answer correctness, query execution success, evidence completeness, unsupported-claim rate, error handling, and response latency.

Only report test results that have actually been measured.

---

## 🌱 Future Scope

Potential extensions include:

- Support for additional authorised data platforms.
- Document retrieval and source-grounded PDF/DOCX analysis.
- Advanced data-quality profiling.
- Scheduled reports and monitoring.
- Role-based dashboards.
- Multi-dataset analytical workflows.
- Natural-language chart generation.
- Query optimisation and performance insights.
- Additional language support.
- Versioned analyses and reproducible reports.

These extensions should preserve the core principle that answers must be based on actual retrieved evidence.

---

## 🤝 Open-Source Contribution

DataLens AI is intended to be a modular, reusable project that developers can adapt to their own datasets and analytical requirements.

Contributions may include:

- Improving SQL generation and validation.
- Adding dataset configurations.
- Improving evidence verification.
- Developing accessible UI components.
- Expanding test coverage.
- Improving documentation and deployment.

Before publishing, include an appropriate `LICENSE` file and verify the licence terms of all dependencies and the selected Gemma model.

---

## 🎯 Project Vision

DataLens AI aims to make data analysis accessible to everyone, regardless of their technical background.

By combining natural-language interaction, Snowflake's analytical capabilities, and Google Gemma's language understanding, the project bridges the gap between asking a question and obtaining a trustworthy, evidence-backed answer.

**The goal is not simply to generate text about data. It is to compute answers from real data, explain how they were obtained, and make every important result independently verifiable.**

**DataLens AI — Ask. Query. Verify.**
