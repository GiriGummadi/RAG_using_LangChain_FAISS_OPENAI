📚 Retrieval-Augmented Generation (RAG) Pipeline using LangChain + FAISS + OpenAI

This repository contains a Jupyter Notebook implementation of an end-to-end RAG pipeline built using:

🔹 LangChain – document loading, chunking, retrieval, prompting <br>
🔹 FAISS – vector indexing + similarity search <br>
🔹 OpenAI – embeddings + LLM generation <br>
🔹 Python – easy-to-follow step-based workflow <br>

This project demonstrates how Large Language Models can be grounded with retrieved knowledge to generate accurate, context-aware answers without hallucination.

🔥 What this project does
| Step | Description | Tools Used |
| -------------------------- | ----------------------------------------------- | -------------------------------- |
| **1. Data Ingestion** | Reads PDF/Text/Markdown documents | LangChain Loaders |
| **2. Chunking** | Splits text into manageable overlapping chunks | `RecursiveCharacterTextSplitter` |
| **3. Embeddings** | Converts chunks into numerical vectors | `OpenAIEmbeddings` |
| **4. Vector Storage** | Indexes embeddings for similarity search | **FAISS** |
| **5. Retrieval** | Retrieves context relevant to a query | MMR / k-NN search |
| **6. Augmentation** | Injects retrieved chunks into prompt as context | `PromptTemplate` |
| **7. Generation** | Produces final grounded answer | `ChatOpenAI` |
| **8. Source Transparency** | Returns text chunks used for the answer | `return_source_documents=True` |

The entire flow is implemented inside a single .ipynb notebook for easy demonstration.

📁 Project Structure<br>
📦 RAG-LangChain-FAISS<br>
│<br>
├── data/ # Place your documents here<br>
├── store/ # FAISS index will be saved/loaded here automatically<br>
├── RAG_Pipeline.ipynb # Main notebook containing full implementation<br>
└── README.md # (this file)<br>
The first run requires a document inside data/.<br>
If the folder is empty, the notebook automatically generates a sample file.

🚀 Setup Instructions

1. Clone the project<br>
   git clone <repo-link> <br>
   cd RAG-LangChain-FAISS<br>

2. Create virtual environment (recommended)<br>
   python -m venv .venv<br>
   .venv\Scripts\activate # Windows<br>

3. Install dependencies<br>
   pip install -r requirements.txt

4. Add your OpenAI API key<br>
   setx OPENAI_API_KEY "sk-xxxxx"<br>

Restart terminal afterward.<br>

▶ Run the Notebook <br>
jupyter notebook <br>
Open RAG_Pipeline.ipynb<br>
Run each cell in order to execute the full pipeline.

🧠 How the pipeline works – Conceptual Flow<br>
📄 Documents (.pdf/.txt/.md)<br>
│<br>
[1] Load & Ingest<br>
│<br>
[2] Split into Chunks<br>
│<br>
[3] Create Embeddings (OpenAI)<br>
│<br>
[4] Store in FAISS Vector Index<br>
│<br>
User asks question<br>
│<br>
[5] Retrieve Similar Chunks (MMR)<br>
│<br>
[6] Augment Prompt w/ Context<br>
│<br>
[7] Generate Answer (LLM)<br>
↓<br>
🧩 Final context-grounded answer<br>

🌟 Key Features
✔ No hallucinations — answers come from your data<br>
✔ Local vector search (FAISS) for speed<br>
✔ Works fully inside Jupyter (no backend server needed)<br>
✔ Supports TXT, PDF, Markdown ingestion<br>
✔ Transparent — prints retrieved context chunks<br>
✔ Great starter template for production RAG systems<br>

📌 Ideal Use Cases<br>
🔹QA on internal knowledge documents<br>
🔹University/Policy/Manual based answering systems<br>
🔹Company private knowledge bots<br>
🔹PDF summarization + question answering<br>
🔹Personal research assistant<br>
