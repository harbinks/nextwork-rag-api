# RAG API with FastAPI

## 📌 Project Overview
This project implements a **Retrieval-Augmented Generation (RAG) API** using **FastAPI**, **ChromaDB**, and **Ollama**.  
The API retrieves relevant context from stored documents and uses a local language model to generate accurate, context-aware responses.

---

## 🚀 Tech Stack
- FastAPI – API framework  
- Ollama – Local LLM runtime (`tinyllama`)  
- ChromaDB – Vector database for embeddings  
- Python – Core language  

---

## 🧠 How the RAG API Works
1. A user sends a query to the API.
2. The query is searched against embeddings stored in ChromaDB.
3. Relevant context is retrieved from the vector database.
4. The context and query are sent to the language model.
5. The model generates a clean and concise answer.
6. The API returns the response in JSON format.

---

## 📁 Project Structure
rag-fastapi/
│── app.py
│── ingest.py
│── requirements.txt
│── db/
│── data/
│ └── context.txt


---

## ⚙️ Setup Instructions
```bash
1️⃣ Create and activate a virtual environment
python -m venv venv
# Windows
.\venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

2️⃣ Install dependencies
pip install -r requirements.txt

3️⃣ Set up Ollama

Ensure Ollama is running and pull the required model:

ollama pull tinyllama

📥 Ingest Documents

Add context data into ChromaDB:

python ingest.py

▶️ Run the API
uvicorn app:app --reload


The API will be available at:

http://127.0.0.1:8000

🧪 Testing the API
Using Swagger UI

Open in browser:

http://127.0.0.1:8000/docs


Use the /query endpoint to send a question and view the response.

Using PowerShell
Invoke-RestMethod -Uri "http://127.0.0.1:8000/query?q=What is Kubernetes?" -Method Post

✅ Sample Response
{
  "answer": "Kubernetes is an open-source container orchestration platform used to manage and scale containerized applications."
}

🎯 Key Learnings

Understanding Retrieval-Augmented Generation (RAG)

Creating and using embeddings for semantic search

Integrating a vector database with a language model

Building APIs with FastAPI

Controlling and cleaning LLM outputs for production-ready responses

🏁 Conclusion

This project demonstrates a complete RAG pipeline, from document ingestion to context-based answer generation, and provides practical experience in building and testing AI-powered APIs.