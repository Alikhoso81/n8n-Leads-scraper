# 🚀 Automated Google Maps Lead Scraper (n8n Workflow)

[![n8n](https://img.shields.io/badge/n8n-Workflow-FF6C37?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![SerpAPI](https://img.shields.io/badge/SerpAPI-Integration-blue?style=for-the-badge)](https://serpapi.com/)
[![Google Sheets](https://img.shields.io/badge/Google_Sheets-Automated-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)](#)

A fully automated, zero-maintenance **n8n workflow** that scrapes high-quality B2B leads from Google Maps and pipelines them directly into Google Sheets. Perfect for automation engineers, marketing agencies, and sales teams looking to build an intelligent, hands-free lead generation engine.

## ✨ Features
* **Scheduled Automation:** Runs automatically via Cron (default: Every Monday at 9 AM).
* **Smart Filtering:** Automatically drops leads missing crucial contact info (Phone or Website).
* **Built-in Deduplication:** Ensures your database stays clean by checking names and phone numbers before appending.
* **Data Transformation:** Parses raw JSON into clean, actionable columns (Name, Phone, Website, Address, Rating, Reviews, Maps URL).
* **Scalable:** Easily swap or add new search keywords and locations.

## 🔑 Prerequisites & Requirements

Since this is a low-code workflow, you do not need a `requirements.txt` or `package.json`. You only need the following:

1. **n8n Instance:** Self-hosted or n8n Cloud (Ensure the Code node is enabled).
2. **SerpAPI Key:** Get a free or paid API key from [SerpAPI](https://serpapi.com/).
3. **Google Cloud Console App:** For Google Sheets API authentication.
4. **Google Sheet:** A blank sheet named "Leads" to receive the incoming data.

## 🛠️ Installation & Usage

1. **Clone or Download:** Grab the `n8n_final_workflow.json` file from this repository.
2. **Import into n8n:**
   * Open your n8n workspace.
   * Click **Add Workflow** -> **Import from File**.
   * Select the JSON file.
3. **Configure the Settings Node:**
   * Double-click the `⚙️ SETTINGS — Edit Keywords Here` node.
   * Paste your `SERPAPI_KEY`.
   * Update the `SEARCHES` array with your target keywords and locations.
4. **Connect Google Sheets:**
   * Authenticate your Google Account in the `Add to Google Sheets` node.
   * Paste your Google Sheet URL into the node settings.
5. **Activate:** Toggle the workflow to **Active** and let it run!

## 🤖 How It Works

1. **Trigger:** Fires on a schedule.
2. **Settings:** Injects your keywords and API keys.
3. **HTTP Request:** Calls the SerpAPI Google Maps engine.
4. **Transform & Clean:** Extracts only the necessary data points.
5. **Deduplicate:** Removes any previously seen leads in the current batch.
6. **Filter:** Keeps only actionable leads (must have website/phone).
7. **Export:** Pushes to Google Sheets.
8. **Log:** Outputs a success message with the total lead count.

## 🤝 Contributing
Feel free to fork this project, submit pull requests, or open an issue if you have ideas for adding new integrations (like pushing to a CRM or verifying emails via Hunter.io).



