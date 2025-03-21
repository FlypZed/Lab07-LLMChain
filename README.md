# 🚀 Lab07-LLMChain

## 📌 Introduction
This repository contains the implementation of the LangChain LLM Chain tutorial. The objective of this lab is to provide hands-on experience with LangChain and Pinecone as a vector database, enabling retrieval-augmented generation (RAG) workflows.

## 📂 Project Structure
```
flypzed-lab08-llmchain/
├── README.md  # Documentation for the project
└── Lab07_AREP.ipynb  # Jupyter Notebook with the implementation
```

## 🔧 Requirements
Before running the notebook, ensure you have the following dependencies installed:
```bash
pip install -qU langchain-pinecone pinecone-notebooks langchain-openai
```

## ⚙️ Setup
### 🔑 1. Pinecone API Key
This project requires Pinecone for vector storage. To configure your API key:
```python
import getpass
import os
os.environ["PINECONE_API_KEY"] = getpass.getpass("Enter your Pinecone API key: ")
```

### 🔑 2. OpenAI API Key
This project uses OpenAI for embeddings. To set up:
```python
os.environ["OPENAI_API_KEY"] = getpass.getpass("Enter API key for OpenAI: ")
```

## 🌟 Key Features
- **Vector Store Creation:** Uses Pinecone as the backend for storing and retrieving embedded text data.
- **Embedding Generation:** Utilizes OpenAI's text-embedding-3-large model.
- **Similarity Search:** Retrieves relevant documents using cosine similarity.
- **Document Management:** Demonstrates adding and deleting vectorized documents.

## ▶️ Usage
1. Run the notebook `Lab07_AREP.ipynb` in Google Colab or locally.
2. Ensure API keys for Pinecone and OpenAI are set before executing the cells.
3. Follow the provided steps to create, retrieve, and manage vectors.

## 📌 Example Output
After adding documents to the vector store, you can retrieve the most relevant ones:
```python
results = vector_store.similarity_search_with_score(
    "Will it be hot tomorrow?", k=1, filter={"source": "news"}
)
for res, score in results:
    print(f"* [SIM={score:3f}] {res.page_content} [{res.metadata}]")
```

## 🔗 Quick Access
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FlypZed/Lab07-LLMChain/blob/main/Lab07_AREP.ipynb)

## 📌 Repository Link
[GitHub Repository](https://github.com/FlypZed/Lab07-LLMChain)

## 📜 License
This project is licensed under the MIT License.
