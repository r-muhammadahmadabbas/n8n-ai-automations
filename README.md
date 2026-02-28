# n8n AI Automations Portfolio

## Overview
This repository contains a collection of backend workflows and AI-powered automations built using [n8n](https://n8n.io/). These projects demonstrate practical applications of integrating Large Language Models (LLMs) with APIs, databases, and enterprise tools to build autonomous agents and streamline operations.

## Workflows Included

### 1. Automated Invoice Processor
An automated ERP data extraction pipeline.
* **Trigger:** Monitors a specific Google Drive folder for newly created files.
* **Process:** Downloads the file and uses Google Gemini 2.5 Flash to extract the Vendor Name, Total Amount, and Date into a strict JSON format.
* **Logic:** Evaluates the invoice amount; standard invoices (<= 500) are appended as new rows in a Google Sheet, while high-value invoices trigger a warning email via Gmail.

### 2. AI Productivity Agent
An AI-powered personal assistant designed to retrieve real-time data.
* **Trigger:** Initiated by a chat message interface.
* **Process:** Employs a Google Gemini Chat Model (Flash Lite) with memory buffers to act as a conversational agent.
* **Integration:** Dynamically determines when to call specific tools to fetch recent emails via Gmail or upcoming events via Google Calendar.

### 3. Q&A Tagging Automation
A data ingestion pipeline for classifying user feedback.
* **Trigger:** Activates upon a form submission containing a user's name, email, question, and answer.
* **Process:** Checks if the submitter's email contains "n8n.io" to assign a trusted status. It then utilizes an LLM to analyze the text and generate highly relevant metadata tags.
* **Storage:** Inserts the fully formatted row, including the AI-generated tags, directly into a data table.

### 4. Q&A Retrieval AI Agent
A conversational interface for querying the historical feedback database.
* **Trigger:** Initiated by a chat message.
* **Process:** An AI agent powered by Google Gemini uses a dedicated data table tool to search the database based on the user's inquiry.
* **Output:** Synthesizes the retrieved data from the 'question' and 'tags' columns to provide a contextual answer, or politely declines if the data is unavailable.

## Core Technologies
* **Automation Engine:** n8n
* **AI & LLMs:** Google Gemini (2.5 Flash, Flash Lite), LangChain components
* **Integrations:** Google Workspace (Drive, Sheets, Gmail, Calendar)

## How to Import
To review or run these workflows locally:
1. Clone this repository.
2. Open your n8n workspace.
3. Navigate to **Workflows** > **Add Workflow**.
4. Click the options menu (three dots in the top right) and select **Import from File**.
5. Select the desired `.json` file.
6. **Note:** You will need to authenticate the nodes with your own Google API credentials.
