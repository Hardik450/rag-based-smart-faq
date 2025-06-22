

## 📚 RAG-Based Smart FAQ using Vertex AI & Hugging Face

This repository contains three progressive implementations of a **Retrieval-Augmented Generation (RAG)** based Smart FAQ system. The project extracts information from a PDF (such as a syllabus or guide), creates semantic embeddings, stores them in a vector database, and answers user queries using a Language Model (LLM).

---

### 📁 Project Structure

| Folder / File    | Description                                           |
| ---------------- | ----------------------------------------------------- |
| `rag-based-smart-faq.ipynb`  | RAG system using **Vertex AI** embeddings + LangChain |
| `rag-based-smart-faq-1.1.ipynb` | RAG using **HuggingFace** embeddings, saved vector DB |
| `rag-based-smart-faq-1.2.ipynb` | Directly loads the saved vector DB for fast querying  |

---

### 🚀 Versions Breakdown

#### ✅ 1. `rag-based-smart-faq.ipynb` – Vertex AI Embedding Based

* Embeds each page of a PDF using **`gemini-embedding-001`** from **Vertex AI**.
* Stores vectors in memory (`FAISS`).
* Handles **quota limitations** (e.g., 5 req/min) via delay logic.
* Enables semantic search-based question answering via `RetrievalQA`.

**Used for:** Demonstrating RAG pipeline with enterprise-grade embedding API.

---

#### ✅ 2. `rag-based-smart-faq-1.1.ipynb` – HuggingFace Embedding + Vector DB Save

* Replaces Vertex AI with **HuggingFace Transformers** (e.g., `sentence-transformers/all-MiniLM-L6-v2`).
* Stores embeddings in **FAISS vector database**.
* Saves vector index to a local file (`faiss_index.pkl`).

**Used for:** Lightweight, offline-friendly smart FAQ systems.

---

#### ✅ 3. `rag-based-smart-faq-1.2.ipynb` – Load Pre-Saved Vector DB

* Loads the saved FAISS vector DB.
* Skips re-embedding and directly enables question-answering.
* Ideal for deployment, faster startup time.

**Used for:** Reusable, efficient production or demo environments.

---

### ⚙️ Tech Stack

* **LangChain** for managing documents, chains, retrievers
* **Vertex AI / HuggingFace** for generating text embeddings
* **FAISS** for vector similarity search
* **ChatGoogleGenerativeAI** for final response generation
* **Python** for entire backend logic

---

---

### 🧠 Future Plans

* ✅ Streamlit / Flask-based front-end
* ✅ Convert to chatbot interface
* 🔜 Store user questions and answers for analytics
* 🔜 Upload multiple files support
* 🔒 Secure API integration

---

