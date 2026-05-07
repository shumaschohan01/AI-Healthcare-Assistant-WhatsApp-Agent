# 🏥 AI Healthcare WhatsApp Agent (n8n + Meta API)

An automated AI-powered healthcare assistant designed to manage patient appointments, provide symptom-based guidance, and synchronize data across Google Sheets, Gmail, and Google Calendar.

## 🚀 Features
- **Intelligent Appointment Booking:** Automated scheduling using AI to parse patient intent.
- **Multi-Platform Integration:** Synchronizes with Google Calendar for doctors and Google Sheets for CRM.
- **WhatsApp Cloud API:** Direct communication with patients via WhatsApp.
- **Error Handling & Alerts:** Automated admin email alerts for workflow failures.
- **Real-time Patient Logging:** Maintains detailed records in Google Sheets.

## 🛠️ Tech Stack
- **Automation:** n8n (Self-hosted/Desktop)
- **AI Model:** Google Gemma 3 (via OpenRouter)
- **Messaging:** Meta WhatsApp Cloud API
- **Database/CRM:** Google Sheets
- **Scheduling:** Google Calendar
- **Tunneling:** Ngrok (for local testing)

## 📋 Prerequisites
- n8n installed (Desktop or Docker)
- Meta Developer Account (WhatsApp Cloud API access)
- OpenRouter API Key
- Google Cloud Console Project (with Gmail & Calendar APIs enabled)

## ⚙️ Setup Instructions

### 1. n8n Workflow
- Download the `healthcare-agent.json` from the `workflows/` folder.
- Import it into your n8n instance.

### 2. Configuration
Instead of environment variables, update the following nodes directly with your credentials:
- **WhatsApp Node:** Insert your `Phone Number ID` and `System Access Token`.
- **OpenRouter Node:** Insert your `API Key` in the Authorization header.
- **Google Sheets Nodes:** Use your Spreadsheet URL and define sheet names (`Doctors`, `Appointments`, `CRM_Patients`).

### 3. Tunneling (Local Environment)
To allow Meta to communicate with your local n8n, use Ngrok:
```bash
ngrok http 5678
