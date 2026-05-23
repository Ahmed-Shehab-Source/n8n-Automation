# 🤖 Exology: Autonomous AI Finance Recorder & Accounting Dashboard

Exology is an autonomous, multi-modal financial tracking and AI-CFO pipeline designed for small and medium business owners. It completely eliminates traditional manual bookkeeping friction by allowing users to log financial data securely via a single Telegram conversation interface.

---

## 📊 System Overview & Architecture

The ecosystem relies on a 4-layer decoupled architecture to ingest, process, structure, and visualize corporate accounts safely:

1. **Presentation Layer:** Telegram Bot API (Receives unstructured Text, Native Voice `.ogg` files, and Receipt Images).
2. **Application Layer:** n8n Workflow Automation Engine Core pipeline orchestration.
3. **Intelligence Layer:** Gemini 2.5 Flash API (Advanced data extraction, zero-shot structured JSON formatting, voice transcription, and financial health profiling).
4. **Data Layer:** Structured Google Sheets ledger workspace acting as the transactional, forecasting, and analytical database.

---

## 📂 The Three Modular Production Workflows

The engine is engineered cleanly across three isolated n8n workflows:

### 1. 🔹 Core Transaction Recorder (`Exology_Main_Workflow.json`)
* **Trigger:** Real-time incoming Telegram webhook trigger events.
* **Logic:** Implements a strict input router switch to manage 3 distinct media paths:
  * **Text Path:** Directly streams short notes into Gemini 2.5 Flash for attribute modeling.
  * **Voice Path:** Intercepts incoming audio metadata, downloads binary `.ogg` payloads from the Telegram storage grid, streams files onto the Gemini Upload File API, and executes joint transcriptions/accounting Extractions.
  * **Photo Path:** Executes automated OCR extraction on structured physical invoices or loose point-of-sale thermal receipts utilizing advanced multi-modal vision prompts.
* **Output:** Validates confidence parameters, compiles standard transactional schema references, saves tracking data to Google Sheets, and pushes rich markup push notification receipts to the user's mobile device.

### 2. 🔹 Financial Forecaster (`Exology_Forecasting_Workflow.json`)
* **Trigger:** Automated cron daemon scheduler executing daily at 11:00 PM.
* **Logic:** Scrapes the past 90 days of operational records, runs moving average calculations to calculate daily run-rates, and maps out a cumulative 30-day corporate trajectory.
* **Output:** Updates the `Forecasts` ledger. If a projected net balance drops below 0 EGP, an explicit **Cash Drought Warning Alert** is generated and broadcasted immediately via Telegram.

### 3. 🔹 Automated AI-CFO (`Exology_Health_Score_Workflow.json`)
* **Trigger:** Automated cron daemon scheduler executing every Monday morning at 9:00 AM.
* **Logic:** Aggregates a full monthly rolling business transaction matrix, calculates net operating metrics, transaction frequencies, and expenditure ratios. Streams this financial summary to Gemini with a dedicated executive corporate finance analysis context.
* **Output:** Appends tracking logs to Google Sheets and sends a beautifully formatted summary outlining an official operational health score (`Healthy` / `Warning` / `Critical`) accompanied by exactly 3 concrete, strategic business recommendations directly to the user.

---

## 📋 Database Structure (Google Sheets Schema)

The processing system requires target sheet tab arrays to map ledger parameters natively:

* **`Transactions` Sheet:** Logs critical execution records including unique `transaction_id`, timestamp, type (income/expense), asset values, local currencies, payment categorization mappings, vendor names, and extraction confidence metrics.
* **`Forecasts` Sheet:** Tracks forward-looking fields: `forecast_date`, `projected_income`, `predicted_expenses`, `predicted_balance`, and `cash_drought` status flags.
* **`Health_Scores` Sheet:** Captures analytics logs over time: `health_score`, explicit qualitative narrative summaries, and detailed operational recommendations.

---

## 🛠️ Step-by-Step Canvas Initialization

1. Download all JSON workflow configurations hosted in this repository directory.
2. Log into your target **n8n browser instance**.
3. Create a blank canvas workspace, access the upper-right configuration panel (`...`), select **Import from File**, and upload the respective JSON blueprints.
4. Provision explicit integration credential hooks within n8n:
   * **Telegram API:** Configure Bot tokens provisioned through the official `@BotFather` platform. Name it `Exology Bot`.
   * **Google Sheets API:** Set up your Workspace Client OAuth2 parameters. Name it `Exology Sheets`.
5. Update individual node environment variables:
   * Replace the target template Google Spreadsheet Document IDs inside all active Spreadsheet steps with your local operational document string.
   * Pass your private API key credentials safely inside the respective endpoint configurations.
6. Toggle all workflows to **Active** to initialize live listening hooks.

---

## 🔒 Security Posture

* All secret tokens, session keys, and live developer API tokens have been fully sanitized and scrubbed from the exposed JSON configuration files.
* Production paths leverage secure n8n placeholder variables to abstract environment keys from canvas logic files.
