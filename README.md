# 🚀 End-to-End Autonomous Invoice Agent

### Multi-Modal Document AI with LangGraph, Docling, Groq & Gemini

---

## 🎯 Problem Statement

Processing invoices manually is slow, error-prone, and difficult to scale.

This project demonstrates how to build an **autonomous AI agent** capable of:

* Extracting structured data from complex PDF invoices
* Understanding both **text and layout (vision)**
* Making **business decisions automatically**
* Interacting with external tools like databases

---

## 📖 Project Journey (From 1 to 5)

This project is structured into 5 progressive stages, each adding a new layer of intelligence:

### 1️⃣ Document Representation

Convert complex PDFs into structured Markdown and high-quality images using **IBM Docling**.

### 2️⃣ Hybrid Extraction

Use a dual-engine strategy:

* ⚡ **Groq (Llama 3.1)** → Fast text extraction
* 👁️ **Gemini 1.5 Flash** → Accurate visual understanding

### 3️⃣ Structured Outputs

Enforce strict schemas using **Pydantic** to transform LLM outputs into validated Python objects.

### 4️⃣ Conditional Logic

Build a stateful workflow using **LangGraph** to route invoices:

* High-value → Manual review
* Low-value → Automated processing

### 5️⃣ Agentic Tool Use

Extend the system with a **SQLite database**:

* Query customer tiers
* Detect VIP clients
* Apply priority business rules

---

## 🏗️ System Architecture

The system operates as a **stateful DAG (Directed Acyclic Graph)**:

```
PDF → Extract (Groq + Gemini) → Decision → DB Agent → Final Action
```

### Flow:

1. **Input:** PDF Invoice
2. **Extract Node:** Multi-modal data extraction
3. **Decision Node:** Conditional logic (amount threshold)
4. **Agent Node:** Database query (customer tier)
5. **Output:** Automated / Manual / VIP Processing

📌 *(You can add an architecture diagram here for better visualization)*

---

## 📸 Example Output

```json
{
  "invoice_number": "INV-2024-001",
  "balance_due": 7200,
  "invoice_date": "2024-02-15",
  "high_value": true,
  "action": "Manual Review"
}
```

---

## 🛠️ Tech Stack

* **Orchestration:** LangGraph
* **Document Parsing:** Docling (IBM)
* **LLMs:** Groq (Llama 3.1 8B / 70B)
* **Vision Models:** Google Gemini 1.5 Flash
* **Validation:** Pydantic
* **Database:** SQLite

---

## 🚀 Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install dependencies

```bash
pip install -U docling langgraph langchain-groq langchain-google-genai pydantic
```

### 3. API Configuration

```python
import os

os.environ["GROQ_API_KEY"] = "your_key"
os.environ["GOOGLE_API_KEY"] = "your_key"
```

---

## 🎥 Demo

👉 *(Add a GIF or short demo video here — highly recommended)*

---

## 📊 Key Results

* ⚡ **Cost-Efficient Inference** using Groq & Gemini free tiers
* 🎯 **High Accuracy** via hybrid text + vision extraction
* 🔍 **Full Observability** with LangGraph workflow tracing
* 🤖 **Autonomous Decision-Making** via conditional routing

---

## ⚙️ Future Improvements

* Add retry & fallback mechanisms (Groq ↔ Gemini)
* Support multi-page invoices
* Build a human-in-the-loop validation UI
* Deploy as an API (FastAPI)
* Add monitoring & logging system

---

## 🧠 Key Concepts

* Multi-Modal AI
* Agentic Workflows
* Retrieval & Tool Usage
* Structured LLM Outputs
* Decision Automation

---

## 📝 Author

**Hajar Boutayeb**
Master’s Student in Data Science & Big Data

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and feel free to contribute!
