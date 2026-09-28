# 🤖 Customer Support RAG Assistant

> A simple Retrieval-Augmented Generation (RAG) system that answers customer-support questions using information retrieved from a company policy document.

<p align="center">
  <b>📄 PDF → ✂️ Chunking → 🧠 Embeddings → 🔎 FAISS → 🤖 LLM → 💬 Answer</b>
</p>

---

## 📌 Project Overview

This project demonstrates a **Retrieval-Augmented Generation (RAG)** pipeline for a customer-support use case.

Instead of asking an LLM to answer questions purely from its pretrained knowledge, the system first retrieves relevant information from a company policy document and then provides that information as context to the LLM.

### 🎯 Example

**User Question**

> How many days do I have to return a product?

**Retrieved Context**

> Customers can return products within 7 days of delivery.

**Generated Answer**

> Customers can return products within 7 days of delivery.

---

## 🏗️ RAG Architecture

```text
                    📄 Company Policy PDF
                              │
                              ▼
                     📥 Document Loading
                         PyPDFLoader
                              │
                              ▼
                       ✂️ Text Chunking
               RecursiveCharacterTextSplitter
                              │
                              ▼
                      🧠 Text Embeddings
                   Sentence Transformers
                              │
                              ▼
                       🗄️ Vector Store
                            FAISS
                              │
                              │
                    🔎 Similarity Search
                              ▲
                              │
                     👤 User Question
                              │
                              ▼
                    📚 Relevant Chunks
                              │
                              ▼
                    📝 Context + Question
                              │
                              ▼
                         🤖 Llama
                         via Ollama
                              │
                              ▼
                       💬 Final Answer
