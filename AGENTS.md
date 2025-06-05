# 🤖 Agents Overview – Microsoft Fabric & Power BI Toolbox

This document describes the agents used within the FabricCodex toolbox. Each agent represents an automated process, AI skill, or reusable template that supports analytics, data integration, governance, or visualization tasks.

---

## 🧠 Intelligent Agents (AI, CoPilot, DAX)

### Agent: `agent-dax-insight-generator`
- **Type**: CoPilot Skill / TMDL Snippet
- **Category**: Analytics
- **Description**: Generates DAX measures dynamically based on natural language prompts.
- **Technologies**: Power BI, CoPilot, TMDL
- **Trigger**: Manual (via CoPilot)
- **Output**: DAX Measure
- **Status**: ✅ Active

---

## 🔄 Data Pipeline Agents (ETL, Dataflows, Notebooks)

### Agent: `agent-etl-crm-api-ingestion`
- **Type**: Dataflow Gen2
- **Category**: Data Integration
- **Description**: Connects to a CRM system via REST API (OAuth2) and ingests customer data into a Lakehouse.
- **Technologies**: Power Query (M), Dataflow Gen2
- **Trigger**: Fabric Pipeline (Daily at 06:00)
- **Output**: Delta Table
- **Status**: ✅ Active

---

### Agent: `agent-data-quality-validator`
- **Type**: PySpark Notebook + Power Automate
- **Category**: Data Quality
- **Description**: Validates data based on defined quality rules (e.g., NULLs, duplicates, out-of-range values).
- **Technologies**: Fabric Notebooks, Power Automate
- **Trigger**: Daily (Scheduled)
- **Output**: Validation Report + Teams Notification
- **Status**: 🧪 In Testing

---

## 📤 Reporting & Distribution Agents

### Agent: `agent-report-distributor`
- **Type**: Power Automate Flow
- **Category**: Report Automation
- **Description**: Exports Power BI reports to PDF and sends them to stakeholders via email.
- **Trigger**: After dataset refresh
- **Output**: PDF report
- **Status**: 🛠️ In Development

---

## 🔐 Governance & Compliance Agents

### Agent: `agent-audit-logger`
- **Type**: Power Automate + Dataverse
- **Category**: Governance
- **Description**: Logs all user interactions with sensitive dashboards for audit and compliance purposes.
- **Technologies**: Power Automate, Dataverse
- **Output**: Audit log table
- **Status**: ✅ Active

---

## 💡 Future Ideas / Backlog

| Agent ID                 | Description                                      | Status        |
|--------------------------|--------------------------------------------------|---------------|
| `agent-deneb-generator`  | Generates reusable Deneb visual JSON templates   | 💡 Idea        |
| `agent-kpi-alerting`     | Monitors KPIs and sends alerts on threshold breach | 🧪 Prototype   |
| `agent-metadata-scanner` | Crawls workspaces and extracts metadata          | 💡 Idea        |

---

## 🧩 Contribution Guidelines

- New agents must follow the naming convention: `agent-[domain]-[function]`.
- Each agent should include a minimal README or metadata definition.
- If applicable, link to templates or scripts in the `/templates` or `/scripts` directory.
