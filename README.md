# flask_RAG_chatbot

A lightweight RAG (Retrieval-Augmented Generation) powered chatbot built with Flask and LangChain, using a local Qwen model via HuggingFace Transformers for context-aware question answering.

## Features

- RAG pipeline using LangChain
- Local Qwen model via HuggingFace Transformers
- Flask REST API with /RAG endpoint
- Context-aware answers from your own documents
- CORS enabled for cross-origin requests

## Project Structure

flask_RAG_chatbot/
├── RAG_Chatbot.ipynb       # Main notebook with all the code
├── langchain_intro.txt     # Knowledge base / source document
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation

## Requirements

- Python 3.9+
- CUDA (optional but recommended for faster inference)

Install all dependencies:

pip install -r requirements.txt

requirements.txt includes:
- flask - REST API server
- flask-cors - Cross-origin support
- langchain - RAG pipeline
- langchain-community - Document loaders, vectorstores
- transformers - Qwen model via HuggingFace
- torch - Deep learning backend
- sentence-transformers - Embeddings
- faiss-cpu - Vector similarity search
- requests - HTTP client for testing

## How to Run

1. Clone the repository:

git clone https://github.com/devAffaan/flask_RAG_chatbot.git
cd flask_RAG_chatbot

2. Install dependencies:

pip install -r requirements.txt

3. Open the notebook:

jupyter notebook RAG_Chatbot.ipynb

4. Run all cells in order, the Flask server will start automatically on:

http://127.0.0.1:5001

## API Usage

Endpoint: POST /RAG

Request:
{
  "question": "What is Text Loader?"
}

Response:
{
  "answer": "A Text Loader is used to load plain text files...",
  "sources": [
    "Text Loader is a document loader in LangChain..."
  ]
}

## How It Works

1. Document Loading - Loads langchain_intro.txt using LangChain's TextLoader
2. Chunking - Splits the document into smaller chunks
3. Embeddings - Converts chunks into vectors using sentence-transformers
4. Vector Store - Stores vectors in FAISS for fast retrieval
5. RAG Chain - On each question, retrieves relevant chunks and passes them to Qwen model
6. Response - Returns cleaned answer and source context

## Author

Affan
GitHub: https://github.com/devAffaan
