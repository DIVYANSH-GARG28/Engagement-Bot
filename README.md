#  Automated Instagram Prospecting & Engagement Engine

An advanced **n8n automation system** designed to identify, score, and engage with high-value Instagram leads using AI. This workflow streamlines the entire prospecting pipeline—from initial discovery to daily performance reporting—making it ideal for agency-level outreach.

## Key Features

* **Automated Lead Discovery**: Periodically scrapes Instagram profiles using Apify (Profile Scraper API) to find and categorise new prospects.
* **Intelligent Lead Scoring**: Custom JavaScript logic evaluates leads based on follower counts and bio data to prioritise high-value targets for engagement.
* **AI-Powered Personalization**: Integrates **Groq AI** to generate context-aware, personalized direct messages and follow-ups.
* **Anti-Detection Logic**: Implements randomised delays (45-90 seconds) between actions to mimic human behaviour and protect account health.
* **Live Performance Dashboard**: A dedicated webhook-triggered HTML dashboard providing real-time visualisation of pipeline metrics.
* **Automated Reporting**: Conducts daily audits of activity (DMs sent, replies received, conversion rates) and syncs data to Google Sheets and Gmail.

## Technical Stack

* **Automation Platform**: n8n
* **Intelligence**: Groq AI (Llama-3/Mixtral)
* **Data Scraping**: Apify
* **Database/CRM**: Google Sheets
* **Communication**: Instagram Graph API & Gmail
* **Languages**: JavaScript (Custom scoring logic & dashboard rendering), HTML/CSS

## Workflow Architecture

1.  **Lead Capture**: Triggers every 6 hours to find and score new prospects via Apify.
2.  **Engagement Loop**: Fetches "pending" leads every 30 minutes, generates AI-driven messages, and sends DMs via HTTP request.
3.  **Follow-Up System**: Checks for no-reply leads every 24 hours and sends secondary engagement prompts if 3+ days have passed.
4.  **Reporting Engine**: Conducts a daily audit to calculate conversion rates and sends a "Daily Prospecting Report" via Gmail.
5.  **Dashboard**: A live `/dashboard` endpoint that renders a professional UI for monitoring system health and lead status.

## Setup & Configuration

1.  **Import Workflow**: Import the `ENGAGEMENT-BOT-TASK.json` file into your n8n instance.
2.  **Credentials**: Configure Apify, Groq, Google Sheets (OAuth2), and Instagram Access Tokens within the n8n credentials manager.
3.  **Sheet Setup**: Ensure your Google Sheet includes columns for `username`, `bio`, `leadScore`, `status`, `dateAdded`, and `dmSent`.

---

### The Approach
As a **B.Tech student** focused on AI and Software Engineering, I built this project to solve the scalability issues inherent in manual prospecting. By combining **asynchronous batch processing** with **advanced prompt engineering**, the system ensures high-quality, human-like outreach while maintaining a low manual workload. The real-time HTML dashboard was added to provide stakeholders with immediate transparency into the automation's ROI.

