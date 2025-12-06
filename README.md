Multi-Modal Document Intelligence (RAG-Based QA System)

This repository contains a Multi-Modal Retrieval-Augmented Generation (RAG) System designed to answer questions from complex PDF documents such as IMF Article IV reports.
The system extracts text, tables, and images (OCR), retrieves relevant sections, and generates citation-backed answers using Groq LLMs.

🚀 Features
1. Multi-Modal Document Ingestion

Extracts information from text, tables, and images.

Uses PyMuPDF for PDF parsing.

OCR handled using EasyOCR.

2. Embedding & Vector Search

Text + OCR content embedded using all-MiniLM-L6-v2.

Stored in a FAISS vector index.

Supports fast and accurate retrieval.

3. Groq LLM Integration

Uses LLaMA 3.3 70B Versatile for answer generation.

Ensures answers are based strictly on PDF context.

Provides page citations for transparency.

4. Streamlit-Based QA Interface

Upload PDF → Ask Questions → Get Answers

Simple and fast UI for end users.

📂 Project Structure
├── app.py                      # Streamlit application
├── preprocess.ipynb            # PDF ingestion and index generation
├── outputs/
│   └── faiss_index/
│       ├── index.faiss
│       └── corpus_metadata.pkl
├── qatar_test_doc.pdf
└── README.md

🛠️ Installation
Install Required Packages
pip install streamlit groq faiss-cpu pymupdf easyocr sentence-transformers pyngrok

🔧 Usage
1. Set Groq API Key
export GROQ_API_KEY="your_api_key"

2. Generate Embeddings and Index

Run:

preprocess.ipynb


This will generate:

index.faiss

corpus_metadata.pkl

3. Run Streamlit App
streamlit run app.py


If running in Colab:

!nohup streamlit run app.py &
from pyngrok import ngrok
ngrok.connect(8501)

🧠 How It Works
Step 1 — Ingestion

Extract text, tables, and OCR from pages.

Chunk the data intelligently based on semantic structure.

Step 2 — Embedding

Convert chunks into dense vectors using MiniLM.

Step 3 — Retrieval

FAISS retrieves top-K relevant chunks for each query.

Step 4 — Generation

Groq LLaMA model generates final answers.

Answers include page citations for accuracy.

📘 Technical Report

This repository includes a 2-page technical report summarizing:

Architecture

Design choices

Retrieval strategy

Multi-modal pipeline

Limitations and improvements

🧩 Future Enhancements

Hybrid search (BM25 + embeddings)

Chart metadata extraction

Cross-modal reranking

Evaluation dashboard


Prabha M
Final Year — B.Tech AI & Data Science
