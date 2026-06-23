# AI-Powered Multi-Channel Support Ticket Router (n8n)

A robust, enterprise-grade backend automation pipeline built using **n8n** that intercepts unstructured user data via webhooks, processes and classifies the intent using a **Groq Large Language Model (LLM)**, and dynamically routes the tickets across multiple production channels based on the classification.

## 🚀 Key Architectural Features

* **Event-Driven Ingestion:** Uses an active n8n Webhook node to capture incoming `POST` requests and raw JSON payloads dynamically.
* **Intelligent Intent Parsing:** Chains a `Basic LLM Chain` paired with a `Groq Chat Model` to perform semantic text classification on user feedback.
* **Deterministic Conditional Routing:** Implements an advanced structural `Switch` node to intelligently split incoming tickets down distinct tracks:
  * **Critical Bugs:** Dispatched instantly to high-priority **Gmail** alerts.
  * **Feature Requests:** Structured and logged seamlessly into product **Google Sheets** for backlog analysis.
  * **General Feedback:** Pushed to corporate internal workspaces via a live **Slack** notification bot interface.

## 🛠️ Tech Stack & Integrations

* **Workflow Orchestration:** n8n (Community Edition)
* **AI & NLP Processing:** Groq API Cloud Models
* **Endpoints & Connectors:** Slack Webhooks/OAuth API, Google Workspace (Sheets, Gmail API)
* **Interface Simulation:** PowerShell REST API methods (`Invoke-RestMethod`)

## 📦 How to Import and Run This Workflow

1. Download the `Ai_Ticket_Router.json` blueprint file from this repository.
2. Open your local n8n dashboard (`localhost:5678`).
3. Create a new workflow, click the top right menu (`...`), and select **Import from File**.
4. Configure your credentials for Groq, Gmail, Google Sheets, and Slack.
5. Toggle the workflow to **Published** to keep the endpoint actively listening 24/7.
