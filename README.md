# RAG

An **end-to-end Retrieval-Augmented Generation (RAG) system** that allows users to ask natural-language questions and receive **accurate, grounded answers directly from PDF documents**.

This project focuses on **retrieval accuracy, reduced hallucinations, and real-world AI system design**.

---

## Project Overview

Traditional LLMs often hallucinate and lack awareness of private documents.
This project solves that by combining:

* **Semantic search (embeddings + vector DB)**
* **Context-aware retrieval**
* **LLM-based answer generation grounded in retrieved content**
---

## Key Features

*  PDF ingestion & cleaning
*  Intelligent text chunking with overlap
*  Embedding generation for semantic similarity
*  Vector storage using ChromaDB
*  Metadata-based filtering (query only relevant documents)
*  Context-grounded answer generation
*  Modular & extensible RAG pipeline
---

## Architecture Flow

```
PDF Document
     ↓
Text Cleaning
     ↓
Chunking (RecursiveCharacterTextSplitter)
     ↓
Embeddings (MiniLM)
     ↓
Vector Database (ChromaDB)
     ↓
Retriever (Top-K + Metadata Filter)
     ↓
LLM (FLAN-T5)
     ↓
Final Answer
```

---

## Tech Stack

| Component       | Tool                           |
| --------------- | ------------------------------ |
| Orchestration   | LangChain                      |
| Document Loader | PyPDFLoader                    |
| Chunking        | RecursiveCharacterTextSplitter |
| Embeddings      | all-MiniLM-L6-v2               |
| Vector Database | ChromaDB                       |
| LLM             | FLAN-T5 (HuggingFace)          |
| Runtime         | CPU (GPU optional)             |

---


##  Engineering Decisions

* Optimized **chunk size & overlap** for retrieval accuracy
* Used **metadata filtering** to prevent cross-document noise
* Prioritized **retriever quality over model size**
* Designed prompts to **minimize hallucinations**

This mirrors how **production-grade RAG systems** are built.

---

## Use Cases

* Internal document search
* Knowledge-base chatbots
* Compliance & policy Q&A
* Enterprise AI assistants
* AI search over private data

---

## Future Improvements

* Multi-PDF querying
* Retriever reranking
* Streaming responses
* API deployment (FastAPI)
* UI integration (Streamlit / Web app)

---

