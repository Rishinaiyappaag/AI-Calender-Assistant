# AI-Calender-Assistant
# 🧠 Tailor Talk: AI Calendar Booking Assistant

This project is a conversational AI assistant built using **FastAPI**, **Gemini (Google Generative AI)**, and the **Google Calendar API**. It understands natural language to schedule events, appointments, meetings, or calls at accurate dates and times.

---

## ✨ Features

- 🗣️ Conversational AI with memory using LangChain + Gemini Pro<br>
- 📅 Books events directly into **Google Calendar**<br>
- 🕓 Understands phrases like:<br>
  - `book an appointment for tomorrow at 11am`<br>
  - `schedule meeting next Friday at 2pm`<br>
  - `call with Rishin at 4pm tomorrow`<br>
- ✅ Handles fuzzy dates like `"next Saturday"`, `"Friday 12pm"`, `"2025-07-12 at 10am"`<br>
- 🔁 Persistent session memory using `ConversationBufferMemory`<br>

---

## 🚀 Tech Stack

| Component            | Tech                         |
|---------------------|------------------------------|
| API Framework       | FastAPI                      |
| LLM                 | Gemini (via `langchain_google_genai`) |
| Natural Language Date Parsing | `dateparser` + Regex          |
| Calendar API        | Google Calendar v3           |
| Memory Management   | LangChain Memory             |

---

## 🛠️ Setup Instructions

### 1. 📁 Clone the Repo
bash
git clone https://github.com/yourusername/AI-Calender-Assistant.git
cd ai-calendar-agent<br>

### 2. 📦 Install Dependencies
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt

### 3. 🔐 Setup Environment Variables
Create a .env file (or backend/ai.env) with your Gemini API Key:
GOOGLE_API_KEY=your-gemini-api-key

### 4. 🔑 Setup Google Calendar API
Go to Google Cloud Console.
Create a new project & enable Google Calendar API.
Create a Service Account and download the credentials.json file.
Share access to your calendar with the service account email (e.g., xyz@project.iam.gserviceaccount.com).
Place the credentials.json file inside the backend/ folder.
Update your calendar ID in backend/calendar_utils.py:

### 5. 🚀 Run the Server
uvicorn backend.main:app --reload
API will be available at:
📍 http://localhost:8000/chat/
