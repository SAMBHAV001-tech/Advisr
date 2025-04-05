
# 🧠 Advisr: AI-powered Customer 360 & Financial Planning Assistant

**Advisr** is a lightweight, offline-first AI app that helps **banks** create tailored financial plans for customers, and assists **individuals** in managing their finances, spending, and investments. Powered by local LLMs via **Ollama**, it uses **multi-agent collaboration**, a **SQLite database**, and a **Java + Python backend**.

---

## 🚀 Features

- Customer 360 profiling (for banks)
- Financial planning assistant (for users)
- Smart product recommendations
- Risk & goal-based validation
- Local-first, privacy-focused AI
- Simple multi-agent design using Ollama

---

## 🛠️ Tech Stack

- **Java** – Backend services & API exposure
- **Python (FastAPI)** – AI service layer
- **SQLite** – Embedded local database
- **Ollama** – Lightweight LLM execution (e.g. Mistral, LLaMA2)
- **LangChain (optional)** – Agent orchestration
- **REST API** – Java ↔ Python communication

---

## 📁 Project Structure

```
advisr/
│
├── backend-java/              # Java backend project
│   └── CustomerController.java
│
├── ai-service/                # Python + FastAPI AI microservice
│   ├── ai_service.py
│   └── agents.py
│
├── db/                        # SQLite DB and table setup
│   └── database.py
│
├── multi-agent/               # Agent orchestration logic
│   └── multi_agent_core.py
│
└── README.md
```

---

## 🔧 Setup Instructions

### Prerequisites
- Java (JDK 17+)
- Python 3.10+
- SQLite3
- [Ollama](https://ollama.com/) (Install & pull `mistral`, `llama2`, etc.)

### 1. Clone the Repo
```bash
git clone https://github.com/your-username/advisr.git
cd advisr
```

### 2. Set Up SQLite DB
```bash
cd db
python database.py
```

### 3. Run Python AI Service
```bash
cd ai-service
uvicorn ai_service:app --reload --port 8000
```

### 4. Start Java Backend
Run via IntelliJ or:
```bash
cd backend-java
mvn spring-boot:run
```

---

## 🔁 Sample Flow

1. Bank staff or user triggers analysis via Java API (`/analyze/{id}`)
2. Java backend fetches customer from SQLite
3. Sends data to Python AI service via HTTP POST
4. AI agents analyze & respond with a financial plan
5. Java returns result to frontend/user

---

## 🤖 Example API Call

```bash
curl -X GET http://localhost:8080/analyze/1
```

---

## 📌 Note

- This is an offline-capable tool for prototyping financial assistants.
- No sensitive data is stored online.
- You can extend it with a web dashboard or add LLM fine-tuning support.

---

## 📫 Contributors

- Dev Team – Backend (Java), AI (Python), UX
- Special thanks to Open Source Ollama & LangChain communities

---

## 📄 License

MIT License
