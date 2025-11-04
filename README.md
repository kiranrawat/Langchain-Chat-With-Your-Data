# Langchain-Chat-With-Your-Data

Part of the learning I had from the Deeplearning.AI course: *LangChain — Chat With Your Data* by Harrison Chase.

This project demonstrates how to build a Retrieval-Augmented Generation (**RAG**) pipeline using LangChain to enable an LLM to answer questions based on private documents.

---

## Objective
Build a system that can:

- Ingest external documents
- Split them into semantically meaningful chunks
- Generate embeddings
- Store vectors in a vector database
- Retrieve relevant text for a query
- Use an LLM to answer questions grounded in retrieved context

---

## Key Learnings

### Retrieval-Augmented Generation (RAG)
LLMs augmented with external knowledge for factual, grounded answers.

### Document Loading
Import documents (PDF, text, web, etc.) into a structured format.

### Chunking Strategy
Semantic chunking > fixed-size splitting.  
Good segmentation improves embedding quality and retrieval accuracy.

### Embeddings & Vector Store
Convert text → embeddings → store in FAISS/Chroma for similarity search.

### Retrieval + QA Chain
Retrieve relevant chunks and feed them to the model to generate answers.

---

## High-Level Architecture

```mermaid
flowchart LR
    UserQuery --> EmbedQuery --> VectorSearch --> RetrieveChunks --> LLM --> Answer

    Documents --> Load --> Chunk --> EmbedDocs --> VectorDB
    VectorDB --> VectorSearch

## 📓 Notebooks Overview

This repository contains Jupyter notebooks following the structure of the *LangChain — Chat With Your Data* course, each focused on a core component of the RAG workflow.

| Notebook | Topic | Description |
|---|---|---|
`01_document_loading.ipynb` | Document Loading | Load and parse documents into a structured text format for processing |
`02_document_splitting.ipynb` | Document Splitting (Chunking) | Split documents into semantically meaningful chunks to preserve context |
`03_vectorstores_and_embeddings.ipynb` | Embeddings & Vector Stores | Convert text chunks into embeddings and store them in a vector DB |
`04_retrieval.ipynb` | Retrieval | Perform similarity search to retrieve relevant chunks based on a user query |
`05_question_answering.ipynb` | QA Chain | Combine retrieved text with an LLM to answer questions grounded in docs |
`06_chat_bot.ipynb` | Chatbot Integration | Build an interactive chat interface that queries data using the RAG pipeline |
