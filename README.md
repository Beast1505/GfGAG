# GfGAG
Basic RAG pipeline with LangChain and Gemini
Retrieval-Augmented Generation (RAG) with LangChain and Gemini
This repository contains a Google Colab notebook (RAG.ipynb) that demonstrates a basic Retrieval-Augmented Generation (RAG) pipeline. The pipeline extracts text from a webpage, processes it, and uses Google's Gemini models to answer natural language questions based specifically on that scraped context.

Overview of the Pipeline
This notebook walks through the standard steps of building a RAG application:

Document Loading: Uses LangChain's WebBaseLoader to scrape content from a GeeksforGeeks tutorial on Artificial Intelligence.

Document Chunking: Employs RecursiveCharacterTextSplitter to break the scraped webpage into manageable, overlapping text chunks (1000 characters per chunk, with a 200-character overlap).

Vector Embeddings & Storage: Uses GoogleGenerativeAIEmbeddings (gemini-embedding-001) to convert the text chunks into vector embeddings and stores them locally using Chroma DB.

Retrieval: Configures the Chroma database as a retriever to find the most relevant chunks of text based on a user's query.

Generation (LLM): Utilizes LangChain Expression Language (LCEL) to pipe the retrieved context and user query into a custom prompt template, which is then sent to the gemini-2.5-flash model for a final, synthesized answer.

Prerequisites
To run this notebook, you will need:

A Google account (to run the Colab notebook).

A Google Gemini API Key.

Within Google Colab, you must save your API key in the Colab Secrets tab under the name RAG so that userdata.get('RAG') can securely load it.

Dependencies
The notebook installs the following core libraries:

langchain / langchain_community / langchainhub

langchain-google-genai (For Gemini LLM and Embeddings)

chromadb (For the local vector store)

Usage
Open the notebook in Google Colab.

Add your Google API Key to the Colab Secrets manager and name it RAG. Ensure the "Notebook access" toggle is turned on.

Run all cells sequentially.

Modify the rag_chain.invoke("your question here") commands at the end of the notebook to ask questions about the scraped AI tutorial!
