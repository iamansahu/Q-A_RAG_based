# RAG Q&A App

A **Retrieval-Augmented Generation (RAG)** application that allows users to upload documents or provide web links/text, then ask questions interactively. The app combines document ingestion, semantic search with **FAISS**, and large language model reasoning via **Hugging Face** to generate context-aware answers.

---

## Features

- **Multiple Input Types**: Supports PDFs, DOCX, TXT, and web links.  
- **Automated Preprocessing**: Extracts text, splits it into ~1000-character chunks, and converts to embeddings using `sentence-transformers/all-mpnet-base-v2`.  
- **Vector Search**: Uses **FAISS** for fast similarity search over document embeddings.  
- **In-Memory Storage**: Stores documents and vectors using LangChain’s `InMemoryDocstore`.  
- **LLM Integration**: Uses Hugging Face endpoint (`Meta-Llama-3-8B-Instruct`) for answering questions based on retrieved content.  
- **Interactive UI**: Built with **Streamlit** for easy uploading, indexing, and querying.

---

## Workflow

1. **User Input**  
   - Choose input type and provide content (file or link).  

2. **Processing**  
   - Extract text from uploaded files or links.  
   - Split text into chunks for embeddings.  
   - Generate embeddings using Hugging Face sentence-transformers.  
   - Store embeddings in FAISS for semantic retrieval.  

3. **Querying**  
   - User enters a natural-language question.  
   - Relevant chunks are retrieved from FAISS.  
   - LLM generates an answer using the retrieved context.  

4. **Output**  
   - Answer is displayed in the Streamlit interface.

---

## Technologies Used

- **Python Libraries**: Streamlit, FAISS, NumPy, PyPDF2, python-docx  
- **LangChain**: Document loaders, text splitting, embeddings, RetrievalQA, FAISS wrapper  
- **Hugging Face**: Sentence Transformers for embeddings, Meta-Llama models via Inference Endpoint  
- **Streamlit Session State**: Maintains vectorstore across interactions  

---

## Use Cases

- Explore and query knowledge bases, reports, or research papers quickly.  
- Prototype document-aware chatbots or assistants.  
- Experiment with RAG workflows combining open-source embeddings and LLMs.

---
