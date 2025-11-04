# Langchain-Chat-With-Your-Data

Part of the learning I had from the Deeplearning.AI course: *LangChain — Chat With Your Data* by Harrison Chase.

This project demonstrates how to build a Retrieval-Augmented Generation (**RAG**) pipeline using LangChain to enable an LLM to answer questions based on private documents.

---

## 🎯 Objective
Build a system that can:

- Ingest external documents
- Split them into semantically meaningful chunks
- Generate embeddings
- Store vectors in a vector database
- Retrieve relevant text for a query
- Use an LLM to answer questions grounded in retrieved context

---

## 📚 Key Learnings

### ✅ Retrieval-Augmented Generation (RAG)
LLMs augmented with external knowledge for factual, grounded answers.

### ✅ Document Loading
Import documents (PDF, text, web, etc.) into a structured format.

### ✅ Chunking Strategy
Semantic chunking > fixed-size splitting.  
Good segmentation improves embedding quality and retrieval accuracy.

### ✅ Embeddings & Vector Store
Convert text → embeddings → store in FAISS/Chroma for similarity search.

### ✅ Retrieval + QA Chain
Retrieve relevant chunks and feed them to the model to generate answers.

---

## 🧠 High-Level Architecture

```mermaid
flowchart LR
    UserQuery --> EmbedQuery --> VectorSearch --> RetrieveChunks --> LLM --> Answer

    Documents --> Load --> Chunk --> EmbedDocs --> VectorDB
    VectorDB --> VectorSearch
