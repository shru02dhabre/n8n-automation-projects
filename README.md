# n8n-automation-projects

AI-powered and rule-based automation workflows built using n8n, 
Claude (Anthropic), and Google Sheets.

---

## Project 1: AI-Powered Customer Support Triage Bot

**File:** `AI Support Triage bot (1).json`

### What it does
Automatically receives customer support messages via webhook, 
uses Claude AI to classify intent and urgency, then routes 
tickets — simple queries get an instant AI-generated reply, 
urgent tickets get escalated to a human agent via Gmail.

### Workflow Architecture
Webhook → Claude (classify intent) → Code (parse JSON)
→ IF node → True: Gmail alert to support team
→ False: Auto-reply to customer
### Tools & Technologies
- n8n (workflow automation)
- Anthropic Claude API (LLM classification)
- Webhook (event trigger)
- Gmail (human escalation alerts)
- JavaScript (JSON parsing)

### Key Concepts Demonstrated
- Webhook design and real-time event-driven architecture
- Prompt engineering for structured JSON output from LLMs
- Conditional routing logic (IF node)
- Third-party API integration (Anthropic, Gmail)

---

## Project 2: Customer Segmentation Workflow

**File:** `Customer segmentation.json`

### What it does
Reads customer data from Google Sheets (total spend, order 
count, recency), applies business rule logic to classify each 
customer into a segment, and writes the result back to the sheet.

### Segments
- **VIP** — spend > ₹10,000 AND order count > 5
- **At Risk** — last order more than 90 days ago
- **New Customer** — only 1 order placed
- **Regular** — all others

### Workflow Architecture
Manual/Schedule Trigger → Google Sheets (read)
→ Code node (apply rules) → Google Sheets (write segment)
### Tools & Technologies
- n8n (workflow automation)
- Google Sheets API
- JavaScript (segmentation logic)

### Key Concepts Demonstrated
- Scheduled automation
- Data transformation using Code node
- Google Sheets read/write integration
- Business rule encoding

---

## Project 3: Customer Sentiment Analysis

**File:** `Customer sentiments.json`

### What it does
Reads customer reviews from Google Sheets, loops through each 
one, sends it to Claude AI for sentiment analysis, and writes 
structured results back to the sheet — including sentiment, 
emotion, key issue, and urgency level.

### Workflow Architecture
Manual Trigger → Google Sheets (read reviews)
→ Loop Over Items → Claude (analyze sentiment)
→ Code (parse JSON) → Google Sheets (write results)
### Output Fields
- **Sentiment** — Positive / Negative / Neutral / Mixed
- **Emotion** — e.g. frustrated, delighted, indifferent
- **Key Issue** — short summary of the main complaint or praise
- **Urgency** — High / Medium / Low

### Tools & Technologies
- n8n (workflow automation)
- Anthropic Claude API (sentiment analysis)
- Google Sheets API
- JavaScript (JSON parsing)
- Loop Over Items node (batch processing)

### Key Concepts Demonstrated
- Looping through multiple records with batch processing
- LLM-powered text analysis
- Structured output prompting
- End-to-end data pipeline (read → process → write)

---

## How to Import These Workflows

1. Install n8n locally: `npx n8n`
2. Open `http://localhost:5678`
3. Click **"Import Workflow"**
4. Upload any `.json` file from this repo
5. Add your own credentials (Google Sheets OAuth, Anthropic API key)
6. Run the workflow

---

Built as part of hands-on automation and AI workflow practice.
