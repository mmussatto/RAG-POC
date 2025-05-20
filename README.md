# Customization of Language Models Using Vector Databases

This repository presents the final undergraduate thesis project of Murilo Mussatto, developed at the Institute of Mathematical and Computer Sciences (ICMC) of the University of São Paulo (USP). The project explores how to customize Large Language Models (LLMs) using external knowledge bases stored in vector databases through a technique known as Retrieval-Augmented Generation (RAG).

## 🧠 Project Overview

Large Language Models, such as GPT and BERT, often rely solely on their training data, which limits their knowledge and makes them prone to hallucination. RAG is a powerful architecture that mitigates these issues by retrieving relevant information from external sources at inference time.

This project demonstrates how to implement a simplified RAG pipeline capable of answering extractive questions about a specific text (in this case, an article about Brazil). The approach includes:

- Splitting documents into semantic chunks.
- Creating vector embeddings using multilingual SBERT.
- Storing and querying embeddings using PGVector with PostgreSQL.
- Using Hugging Face pipelines to extract answers with two LLMs: **BERTimbau** and **MDeBERTa**.

## 📊 Sample Results

The system was tested with five factual questions about Brazil. Here are a few examples:

- **Q:** *What are the two imaginary lines that cross Brazil?*  
  **A (MDeBERTa):** *Equator and Tropic of Capricorn.*

- **Q:** *Who discovered Brazil?*  
  **A (BERTimbau):** *Pedro Álvares Cabral.*

The results show that both models could retrieve and extract accurate answers using the information supplied by the external vector database, showcasing the effectiveness of the RAG architecture.

## 🚀 How to Run the Code

The entire implementation is available in a Jupyter Notebook (`RagPoc.ipynb`) in the root directory of this repository. To run it, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mmussatto/RAG-POC.git
   cd RAG-POC
   ```

2. **Install dependencies**:
   It is recommended to use a virtual environment. The main libraries required include:

   * `langchain_community`
   * `transformers`
   * `pgvector`
   * `sentence-transformers`
   * `psycopg2` (for PostgreSQL connection)


3. **Start PostgreSQL with PGVector**:
   Make sure PostgreSQL and the PGVector extension are correctly installed and configured. Details on how to install PGVector can be found [here](https://github.com/pgvector/pgvector).

4. **Update HuggingFace API Token**
	Make sure you add a valid HuggingFace API Token in the **Embedding** section.

5. **Run the Notebook**:
   Open the notebook using Jupyter:

   ```bash
   jupyter notebook notebook.ipynb
   ```

   Follow the cells sequentially to understand each part of the RAG implementation.

## 📄 Full Monograph

For a complete explanation of the methodology, theoretical foundation, and experiment results, you can read the full monograph here (Portuguese only): [MonografiaMuriloMussatto.pdf](./MonografiaMuriloMussatto.pdf)


