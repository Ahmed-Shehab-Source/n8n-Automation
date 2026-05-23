# 🚀 n8n Production Automations Portfolio

Welcome to my production-ready automation repository. This repository serves as a centralized hub for enterprise-grade workflow pipelines, low-code system integrations, and AI-driven automation agents built using **n8n**. 

Each project inside this repository is fully documented, isolated within its own directory, and packaged with native workflow blueprint JSON configurations ready for deployment.

---

## 📂 Active Automation Projects

### 1. 🤖 Exology: Autonomous AI Finance Recorder & Accounting Dashboard
* **Directory:** [`/Exology-AI-Finance-Recorder`](./Exology-AI-Finance-Recorder/)
* **Stack:** n8n Cloud, Gemini 2.5 Flash API, Telegram Bot API, Google Sheets API.
* **Core Functionality:** A multi-modal, bilingual financial tracking pipeline built for small and medium businesses. It processes unstructured data—text, native voice notes (.ogg), and receipt photos (.jpeg)—sent via a secure Telegram bot interface, structures the metadata using an AI extraction engine, executes rigorous data validation rules, logs records instantly into a Google Sheets ledger database, and fires back an automated confirmation breakdown or financial forecasting alert.

---

## 🛠️ Global Requirements & System Deployment

To deploy or replicate any workflow found within this repository, ensure your environment fulfills the following baseline requirements:

1. **n8n Instance:** Access to a self-hosted Docker instance or an active n8n Cloud environment.
2. **Global Integration Credentials:**
   * Custom Telegram Bot tokens provisioned via official Telegram `@BotFather` configuration.
   * Google Workspace Service Accounts or OAuth2 client credentials with `Google Sheets API` scopes enabled.
   * Authorized developer API keys for Large Language Model processing (e.g., Google AI Studio).

### 📥 Standard Import Blueprint Protocol

All projects include an export configuration file containing the visual architecture layouts of the automation nodes. To spin up a project:

1. Clone or download this repository locally.
2. Navigate into your target project directory and select the primary workflow `.json` configuration file.
3. Open your target **n8n workspace dashboard** canvas.
4. Open the context menu in the upper-right corner (`...`) and click **Import from File**.
5. Upload the JSON blueprint to instantly generate the full production node workspace.
6. Open your local node configuration layouts to attach your specific private environment credentials and update template Spreadsheet Document IDs.

---

## 🔒 Security and Credentials Statement

> ⚠️ **Production Security Notice:** In adherence to strict security standards, all sensitive production metadata, live authentication records, secret application tokens, and private infrastructure environment keys have been programmatically scrubbed and stripped from the codebase using automated pre-commit parsing scripts. 
> 
> Environment variables and configurations are replaced with explicit placeholder strings (e.g., `YOUR_GEMINI_API_KEY`, `YOUR_TELEGRAM_CHAT_ID`) to ensure zero structural risk or information leakage. Users must explicitly attach their own secure infrastructure secrets upon canvas initialization.

---

## 💼 Developer Profile

* **Specialization:** Business Analysis & Business Intelligence Engineering
* **Core Competencies:** Business Technology Automation, Data Analysis Pipeline Architecture, Predictive Analytics Modeling, Dashboard Design.
