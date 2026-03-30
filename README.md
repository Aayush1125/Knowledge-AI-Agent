This repository contains a Retrieval-Augmented Generation (RAG) application built using the Google Gemini API. It allows users to ask questions about the Indian Constitution and receive concise, context-aware answers derived directly from the official document.

Features:-

PDF Ingestion: Automatically loads and processes the "Indian_Constitution.pdf".

Vector Search: Uses ChromaDB and GoogleGenerativeAIEmbeddings for efficient document retrieval.

Gemini 1.5 Pro: Leverages Google's state-of-the-art LLM for generating accurate responses.

Streamlit UI: A clean, chat-based interface for easy interaction.

Tech Stack:-

LLM: Google Gemini 1.5 Pro

Orchestration: LangChain

Vector Database: ChromaDB

Frontend: Streamlit

Embeddings: Google Generative AI Embeddings (models/embedding-001)

Prerequisites:-

Before running the project, ensure you have:

A Google AI Studio API Key.

Python 3.9+ installed.

The Indian_Constitution.pdf file in the root directory.

Installation & Setup

Clone the repository:

git clone https://github.com/Aayush1125/Knowledge-AI-Agent.git
cd your-repo-name

Install dependencies:

pip install streamlit langchain-google-genai langchain-community langchain-chroma pypdf python-dotenv

Set up environment variables:
Create a .env file in the root directory and add your API key:

Code snippet
GOOGLE_API_KEY=your_actual_api_key_here
Run the application:

streamlit run app.py

How It Works:-

Loading: The PyPDFLoader reads the Indian Constitution PDF.

Splitting: The text is broken into 1,000-character chunks using RecursiveCharacterTextSplitter.

Embedding: Chunks are converted into high-dimensional vectors and stored in a local chroma_db/ directory.

Retrieval: When you ask a question, the system finds the top 10 most relevant snippets from the PDF.

Generation: Gemini 1.5 Pro synthesizes the snippets into a concise, 3-sentence maximum answer.
