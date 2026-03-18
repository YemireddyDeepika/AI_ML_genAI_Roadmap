# 🤗 Week 8 — Hugging Face & RAG Architecture

> **90-Day Generative AI Roadmap** | Week 8 of 14  
> **GitHub:** [YemireddyDeepika](https://github.com/YemireddyDeepika) | **LinkedIn:** [yemireddy-deepika](https://linkedin.com/in/yemireddy-deepika)

---

## 📌 Overview

This week covers the **Hugging Face ecosystem** — from basic pipelines to building a full **RAG (Retrieval-Augmented Generation)** system from scratch. The final project is a deployed Document Q&A application powered by Sentence-BERT, FAISS vector search, and Gradio.

---

## 🗓️ Day-by-Day Breakdown

| Day | Topic | Key Concepts |
|-----|-------|-------------|
| Day 1 | HuggingFace Pipelines | Sentiment, NER, QA, Summarization, Zero-shot |
| Day 2 | Tokenizers & Models | BERT tokenization, input IDs, attention masks |
| Day 3 | Datasets Library | `load_dataset`, filtering, mapping, splits |
| Day 4 | Sentence Transformers | Semantic embeddings, `all-MiniLM-L6-v2` |
| Day 5 | FAISS Vector Search | `IndexFlatL2`, similarity search, vector indexing |
| Day 6 | Gradio UI | `gr.Interface`, `gr.Textbox`, `share=True` |
| Day 7 | **RAG Final Project 🏆** | Full pipeline: Doc → Chunks → Embed → FAISS → QA → Answer |

---

## 🏆 Final Project — RAG Document Q&A System

### What It Does
Paste any document → Ask a question → Get an accurate answer with confidence score.

### Architecture
```
User Question
      │
      ▼
[Sentence-BERT Embedder]
      │
      ▼
[FAISS Vector Search] ──→ Top 3 Relevant Chunks
      │
      ▼
[RoBERTa QA Model] ──→ deepset/roberta-base-squad2
      │
      ▼
[Answer + Confidence Score]
```

### Tech Stack
| Component | Tool |
|-----------|------|
| Embedding Model | `sentence-transformers/all-MiniLM-L6-v2` |
| Vector Store | `FAISS` (Facebook AI Similarity Search) |
| QA Model | `deepset/roberta-base-squad2` |
| UI Framework | `Gradio` |
| Deep Learning | `PyTorch` |

---

## 🚀 How to Run

### Option 1 — Google Colab (Recommended)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

1. Open `RAG_Document_QA.ipynb` in Google Colab
2. Run all cells
3. Click the Gradio link generated at the bottom

### Option 2 — Local
```bash
# Clone the repo
git clone https://github.com/YemireddyDeepika/90-day-genai-roadmap.git
cd week8-huggingface

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

---

## 📦 Requirements

```
transformers
sentence-transformers
faiss-cpu
gradio
torch
numpy
```

Install all at once:
```bash
pip install transformers sentence-transformers faiss-cpu gradio torch numpy
```

---

## 💡 Sample Usage

**Document:**
```
Hyderabad is the capital of Telangana state in India. It is known as the 
City of Pearls and is a major IT hub with companies like Microsoft, Google, 
and Amazon. The city was founded in 1591 by Muhammad Quli Qutb Shah.
```

**Question:** `Who founded Hyderabad?`

**Answer:** `Muhammad Quli Qutb Shah` ✅ (Confidence: 94.2%)

---

## 📁 Folder Structure

```
week8-huggingface/
│
├── RAG_Document_QA.ipynb   ← Main Colab notebook
├── app.py                  ← Standalone Python script
├── requirements.txt        ← Dependencies
└── README.md               ← You are here
```

---

## 🧠 Key Concepts Learned

**RAG (Retrieval-Augmented Generation)**
> Instead of relying only on a model's training data, RAG retrieves relevant information from a document at runtime and uses it to generate accurate answers.

**Why RAG matters:**
- ✅ Works on documents the model has never seen
- ✅ Reduces hallucinations
- ✅ Used in production at most AI companies
- ✅ Foundation of modern AI assistants

**Sentence-BERT**
> Converts text into dense vector embeddings that capture semantic meaning. Similar sentences have similar vectors.

**FAISS**
> Facebook AI Similarity Search — lightning-fast vector database for finding the most similar embeddings.

---

## 🔗 Connection to Roadmap

```
Week 5 — Neural Networks
Week 6 — CNN
Week 7 — Transfer Learning  ←  pretrained models concept
Week 8 — Hugging Face 🤗   ←  YOU ARE HERE
Week 9 — RNN & NLP
Week 10 — LLM APIs          ←  builds on this week
Week 11 — LangChain         ←  advanced RAG
Week 12 — Agentic AI        ←  end goal 🎯
```

---

## 👩‍💻 About

**Deepika Yemireddy** — CSE Graduate (2022), CBIT Proddatur  
Currently on a **90-Day Generative AI Learning Roadmap**  
Target Role: **AI/ML Engineer / Agentic AI Developer**

- 🐙 GitHub: [github.com/YemireddyDeepika](https://github.com/YemireddyDeepika)
- 💼 LinkedIn: [linkedin.com/in/yemireddy-deepika](https://linkedin.com/in/yemireddy-deepika)

---

⭐ **If this project helped you, please star the repository!**
