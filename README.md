# 🚀 AI Sales Automation System (n8n)

An end-to-end **AI-powered outbound sales automation system** built with n8n, designed to source leads, enrich data, generate personalized outreach, and send emails after manual approval.

---

## 🧠 Overview

This system automates the full outbound pipeline:

1. **Lead Sourcing** via Apollo
2. **Data Enrichment** (Apollo + LinkedIn scraping via PhantomBuster)
3. **AI Personalization** (LLM-generated cold emails)
4. **Human Approval Layer** (Google Sheets)
5. **Automated Email Sending** (LeadConnector / GoHighLevel)

---

## ⚙️ Workflows Included

### 1. 🧩 AI Sales Agent

Core pipeline responsible for:

* Fetching leads from Apollo 
* Enriching contact + company data
* Scraping LinkedIn profiles & company pages
* Structuring and merging data
* Generating personalized cold emails using AI
* Storing results in Google Sheets for approval

#### Key Features

* 🔍 Targeted ICP filtering (specified firms, revenue range, employee size)
* 🔗 LinkedIn profile + company scraping
* 🤖 AI-generated outreach (HTML formatted emails)
* 🔄 Batch processing with retry logic
* 📊 Google Sheets integration for tracking & approval

---

### 2. ✅ Post Approval Agent

Handles sending emails after manual review.

#### Flow:

* Watches Google Sheets for updates
* Filters rows where `Approval = Approved`
* Loops through approved contacts
* Sends emails via LeadConnector API

#### Key Features

* 👀 Sheet-based approval system
* 📤 Automated email dispatch
* 🔁 Batch processing loop
* ⚡ Lightweight & trigger-based execution

---

## 🛠 Tech Stack

* **Automation:** n8n
* **Lead Source:** Apollo API
* **Scraping:** PhantomBuster
* **AI:** OpenAI (via n8n LangChain node)
* **Database / UI:** Google Sheets
* **Email Sending:** LeadConnector (GoHighLevel API)

---

## 🔄 System Architecture

```
Apollo → Enrichment → LinkedIn Scraping → AI Generation → Google Sheets → Approval → Email भेजना
```

---

## 🔐 Security

* ⚠️ Before deploying, you must configure your own:

  * Apollo API Key
  * PhantomBuster session cookie
  * OpenAI API Key
  * Google Sheets OAuth
  * LeadConnector API token

---

## 🚀 Setup Instructions

1. Import workflows into n8n
2. Configure credentials:

   * Apollo
   * PhantomBuster
   * OpenAI
   * Google Sheets
   * LeadConnector
3. Update:

   * Sheet IDs
   * Location IDs
   * API headers (Authorization tokens)
4. Activate workflows
5. Run initial test

---

## 📌 Notes

* Designed for **small CPA firms outreach (US market)**
* Easily adaptable to other niches by modifying Apollo filters
* Includes built-in retry logic for external API reliability
* AI output is structured for direct email delivery (HTML)

---

## ⚡ Future Improvements

* Rate limiting & queue system
* Email warmup + deliverability tracking
* Multi-channel outreach (LinkedIn + SMS)
* CRM sync enhancements
* Advanced personalization (RAG / firm-specific insights)

---

## 👨‍💻 Author

Built by an AI automation-focused developer specializing in:

* AI workflows
* AI Agents
* Business process automation

---

## 📄 License

MIT License 

