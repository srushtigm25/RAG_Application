📌 Overview

RAG_Application is an end-to-end project that demonstrates how to build a Retrieval-Augmented Generation (RAG) pipeline to extract structured insights from PDF documents using LangChain, OpenAI embeddings, Chroma vector database, and a Streamlit UI.

It covers every step — from reading and chunking PDFs, creating embeddings, storing them in a vector database, querying via an LLM, and displaying results interactively.



🚀 Key Features

📄 PDF Parsing & Chunking – Load and split large PDFs into coherent text segments.

🧩 Embedding Generation – Use OpenAI embeddings to convert text chunks into dense vector representations.

💾 Vector Database (Chroma) – Store and retrieve embeddings efficiently using similarity search.

🤖 Context-Aware Question Answering – Query PDFs via LangChain’s retriever + ChatOpenAI.

💬 Streamlit Frontend – Interactive interface for document upload and Q&A.

🐳 Docker Support – Easily containerize and deploy anywhere.



🏗️ Architecture
'''
PDF Document
│
▼
[Document Loader]
│
▼
[RecursiveCharacterTextSplitter]
│
▼
[OpenAI Embeddings]
│
▼
[Chroma Vector Store]
│
▼
[Retriever + LLM (ChatOpenAI)]
│
▼
Structured / Natural-Language Response
'''


🧰 Tech Stack
Component	Technology
Language	Python 3.11
Frameworks	LangChain (Core, Community, OpenAI), Streamlit
Vector Store	Chroma
LLM Provider	OpenAI
Containerization	Docker
Environment Management	.env + python-dotenv


🔑 Setup Instructions
1️⃣ Clone the repository
git clone https://github.com/srushtigm25/RAG_Application.git
cd RAG_Application

2️⃣ Create and activate a virtual environment
python3.11 -m venv .venv
source .venv/bin/activate

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Add your API key

Create a .env file in the project root:

OPENAI_API_KEY=your_openai_api_key_here

5️⃣ Run the Streamlit app
streamlit run streamlit_app.py


Then open http://localhost:8501
 in your browser.

🐳 Run with Docker
docker build -t rag_app .
docker run -p 8501:8501 rag_app

🧠 How It Works

Upload a PDF via the Streamlit app.

The document is split into smaller semantic chunks.

Each chunk is converted into embeddings using OpenAIEmbeddings.

Chunks are stored in a Chroma vector database.

On query, the retriever finds the most similar chunks.

These chunks are passed to ChatOpenAI, which generates a structured or natural-language response.

📊 Example Queries

“What is the title of the research paper?”

“Summarize the abstract.”

“List all datasets or methods mentioned.”

“What is the conclusion of the paper?”

🧩 Future Enhancements

✅ Multi-file PDF ingestion

✅ Metadata extraction (tables, figures)

✅ Support for other LLM providers (Claude, Gemini, Azure OpenAI)

✅ Evaluation metrics for RAG quality
