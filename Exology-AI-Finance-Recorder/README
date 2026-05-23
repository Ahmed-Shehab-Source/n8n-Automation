# 🤖 Exology: Autonomous AI Finance Recorder & Accounting Dashboard

[cite_start]Exology is an autonomous, multi-modal financial tracking and AI-CFO pipeline designed for small and medium business owners[cite: 22]. [cite_start]It completely eliminates traditional manual bookkeeping friction by allowing users to log financial data securely via a single Telegram conversation interface[cite: 23].

---

## 📊 System Overview & Architecture

[cite_start]The ecosystem relies on a 4-layer decoupled architecture to ingest, process, structure, and visualize corporate accounts safely[cite: 38, 39]:

1. [cite_start]**Presentation Layer:** Telegram Bot API (Receives unstructured Text, Native Voice `.ogg` files, and Receipt Images)[cite: 40, 104, 105, 106].
2. [cite_start]**Application Layer:** n8n Workflow Automation Engine Core pipeline orchestration[cite: 40].
3. [cite_start]**Intelligence Layer:** Gemini 2.5 Flash API (Advanced data extraction, zero-shot structured JSON formatting, voice transcription, and financial health profiling)[cite: 40, 110, 131, 148, 202].
4. [cite_start]**Data Layer:** Structured Google Sheets ledger workspace acting as the transactional, forecasting, and analytical database[cite: 40, 70].

---

## 📂 The Three Modular Production Workflows

[cite_start]The engine is engineered cleanly across three isolated n8n workflows[cite: 42]:

### 1. 🔹 Core Transaction Recorder (`Exology_Main_Workflow.json`)
* [cite_start]**Trigger:** Real-time incoming Telegram webhook trigger events[cite: 43, 96].
* [cite_start]**Logic:** Implements a strict input router switch to manage 3 distinct media paths[cite: 101, 103]:
  * [cite_start]**Text Path:** Directly streams short notes into Gemini 2.5 Flash for attribute modeling[cite: 107, 109].
  * [cite_start]**Voice Path:** Intercepts incoming audio metadata, downloads binary `.ogg` payloads from the Telegram storage grid, streams files onto the Gemini Upload File API, and executes joint transcriptions/accounting Extractions[cite: 114, 118, 121, 124, 130, 131].
  * [cite_start]**Photo Path:** Executes automated OCR extraction on structured physical invoices or loose point-of-sale thermal receipts utilizing advanced multi-modal vision prompts[cite: 135, 147, 148, 262].
* [cite_start]**Output:** Validates confidence parameters, compiles standard transactional schema references, saves tracking data to Google Sheets, and pushes rich markup push notification receipts to the user's mobile device[cite: 33, 156, 158, 159, 254].

### 2. 🔹 Financial Forecaster (`Exology_Forecasting_Workflow.json`)
* [cite_start]**Trigger:** Automated cron daemon scheduler executing daily at 11:00 PM[cite: 43, 161].
* [cite_start]**Logic:** Scrapes the past 90 days of operational records, runs moving average calculations to calculate daily run-rates, and maps out a cumulative 30-day corporate trajectory[cite: 176, 177].
* [cite_start]**Output:** Updates the `Forecasts` ledger[cite: 179]. [cite_start]If a projected net balance drops below 0 EGP, an explicit **Cash Drought Warning Alert** is generated and broadcasted immediately via Telegram[cite: 33, 180, 181, 187].

### 3. 🔹 Automated AI-CFO (`Exology_Health_Score_Workflow.json`)
* [cite_start]**Trigger:** Automated cron daemon scheduler executing every Monday morning at 9:00 AM[cite: 43, 189].
* [cite_start]**Logic:** Aggregates a full monthly rolling business transaction matrix, calculates net operating metrics, transaction frequencies, and expenditure ratios[cite: 198, 199]. [cite_start]Streams this financial summary to Gemini with a dedicated executive corporate finance analysis context[cite: 200, 201].
* [cite_start]**Output:** Appends tracking logs to Google Sheets and sends a beautifully formatted summary outlining an official operational health score (`Healthy` / `Warning` / `Critical`) accompanied by exactly 3 concrete, strategic business recommendations directly to the user[cite: 202, 213, 216].

---

## 📋 Database Structure (Google Sheets Schema)

[cite_start]The processing system requires target sheet tab arrays to map ledger parameters natively[cite: 69]:

* [cite_start]**`Transactions` Sheet:** Logs critical execution records including unique `transaction_id`, timestamp, type (income/expense), asset values, local currencies, payment categorization mappings, vendor names, and extraction confidence metrics[cite: 70].
* [cite_start]**`Forecasts` Sheet:** Tracks forward-looking fields: `forecast_date`, `projected_income`, `predicted_expenses`, `predicted_balance`, and `cash_drought` status flags[cite: 70].
* [cite_start]**`Health_Scores` Sheet:** Captures analytics logs over time: `health_score`, explicit qualitative narrative summaries, and detailed operational recommendations[cite: 70].

---

## 🛠️ Step-by-Step Canvas Initialization

1. Download all JSON workflow configurations hosted in this repository directory.
2. Log into your target **n8n browser instance**.
3. [cite_start]Create a blank canvas workspace, access the upper-right configuration panel (`...`), select **Import from File**, and upload the respective JSON blueprints[cite: 83].
4. [cite_start]Provision explicit integration credential hooks within n8n[cite: 85]:
   * [cite_start]**Telegram API:** Configure Bot tokens provisioned through the official `@BotFather` platform[cite: 58]. [cite_start]Name it `Exology Bot`[cite: 59].
   * [cite_start]**Google Sheets API:** Set up your Workspace Client OAuth2 parameters[cite: 63]. [cite_start]Name it `Exology Sheets`[cite: 64].
5. [cite_start]Update individual node environment variables[cite: 67, 87]:
   * Replace the target template Google Spreadsheet Document IDs inside all active Spreadsheet steps with your local operational document string[cite: 87].
   * [cite_start]Pass your private API key credentials safely inside the respective endpoint configurations[cite: 67].
6. [cite_start]Toggle all workflows to **Active** to initialize live listening hooks[cite: 89].

---

## 🔒 Security Posture

* All secret tokens, session keys, and live developer API tokens have been fully sanitized and scrubbed from the exposed JSON configuration files.
* Production paths leverage secure n8n placeholder variables to abstract environment keys from canvas logic files.
