# Automation Q&A Logger With Gemini API 🧠⚙️

An automation workflow using [n8n](https://n8n.io) to receive questions, send them to Google’s Gemini API, and log the answers into Google Sheets.

## ✨ Features

- 📨 Accept questions via webhook
- 🤖 Send questions to Gemini API (Google AI)
- 📄 Log question, answer, and timestamp into Google Sheets
- 🔌 Easily integrate with Telegram bots, WhatsApp, Discord, etc.

## Tech Stack

- [n8n](https://n8n.io) – Automation platform
- Gemini API – Google Generative AI
- Google Sheets – For storing Q&A logs

## How to Use

1. Import `Q&A Gemini Automation.json` into your n8n workspace
2. Set your **Gemini API key** from [Google AI Studio](https://makersuite.google.com/app)
3. Create a Google Sheet with the columns: `Pertanyaan`, `Jawaban`, `TimeStamp`
4. Replace:
   - `[YOUR API KEY]` in the HTTP Request node
   - `[YOUR_SPREADSHEET_ID]` and `[YOUR_SPREADSHEET_URL]` in the Google Sheets node
5. Activate the workflow, send a POST request to the webhook, and you're done!

## Sample Request

```http
POST /webhook/<your-endpoint-id>
Content-Type: application/json

{
  "question": "What is an LLM?"
}
