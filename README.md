# HR Resume Screening AI Agent

An agentic AI app that screens resumes against a job description using OpenAI embeddings, FAISS vector search, and LangChain — served via a Streamlit UI.

---

## How It Works

1. Upload one or more resume PDFs
2. Paste a job description
3. The app embeds all resumes into a FAISS vector store
4. It retrieves the top 5 most relevant resumes via similarity search
5. An LLM (GPT) evaluates each candidate and returns a score, strengths, gaps, and a final recommendation (Shortlist / Maybe / Reject)

---

## Prerequisites

- Python 3.10 or higher
- An [OpenAI API key](https://platform.openai.com/api-keys)

---

## Setup

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd hr-agent
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your OpenAI API key

Create a `.env` file in the project root:

```bash
# .env
OPENAI_API_KEY=sk-...your-key-here...
```

---

## Run the App

```bash
streamlit run hr_agent_ui_cloud.py
```

The app will open in your browser at `http://localhost:8501`.

---

## Project Structure

```
hr-agent/
├── hr_agent_ui_cloud.py   # Main Streamlit app
├── requirements.txt        # Python dependencies
├── .env                    # OpenAI API key (not committed)
└── README.md
```

---

## Dependencies

| Package | Purpose |
|---|---|
| `streamlit` | Web UI |
| `langchain-openai` | OpenAI LLM + embeddings via LangChain |
| `langchain-community` | PDF loader, FAISS vector store integration |
| `faiss-cpu` | Local vector similarity search |
| `pypdf` | PDF parsing |
| `openai` | OpenAI API client |
| `python-dotenv` | Load `.env` file |
