# LlamaIndex-Agent-Applications


#![ScreenShot](/pipeline.png)

## Description:

### LlamaIndex:

It is a framework for building context-augmented LLM Applications. It provides tools to make a multitude of Applications from prototype to production. These tools allow:
    1. Ingest Data and storing in Vector Stores
    2. Implement Complex Querying Workflows combining data access with LLM prototyping

### Agents:



## Methods Implemented

### Data-Backed LLM Applications

1. Structured Data Extraction

        Pydantic Extractors: Extract structured data from unstructured sources like PDFs and websites using LLMs. Essential for automating workflows by filling in missing pieces in a type-safe way.
   
2. Query Engines

        End-to-End Pipelines: Handle natural language queries and return responses with reference context retrieved and passed to the LLM.
   
3. Chat Engines

        Conversational Pipelines: Facilitate multiple back-and-forth interactions with your data instead of a single question-and-answer.

4. Agents

    Automated Decision-Makers: Use LLMs to interact with the world via a set of tools, dynamically deciding the best course of action to complete tasks.

### Retrieval-Augmented Generation (RAG)
   
Integrate your data with LLMs to enhance their capabilities. Crucial for chatbots, agents, and any data-driven LLM application.

> Loading: Import data from various sources like text files, PDFs, websites, databases, or APIs.
> Indexing: Create vector embeddings and other metadata for efficient data querying.
> Storing: Save indexed data and metadata to avoid re-indexing.
> Querying: Utilize various strategies for efficient and relevant data retrieval.
> Evaluation: Assess the pipeline’s effectiveness, accuracy, and speed.

Key Stages:

Loading: Import data from various sources like text files, PDFs, websites, databases, or APIs.
Indexing: Create vector embeddings and other metadata for efficient data querying.
Storing: Save indexed data and metadata to avoid re-indexing.
Querying: Utilize various strategies for efficient and relevant data retrieval.
Evaluation: Assess the pipeline’s effectiveness, accuracy, and speed.
Important Concepts
Nodes and Documents: Nodes represent chunks of data with metadata, while Documents are containers for data sources.
Connectors: Ingest data from various sources into Documents and Nodes.
Indexes: Store vector embeddings and metadata for efficient data retrieval.
Embeddings: Numerical representations of data used to filter for relevance.
Retrievers and Routers: Define and manage strategies for retrieving relevant context.
Node Postprocessors and Response Synthesizers: Transform retrieved nodes and generate responses from LLMs.


## Features:

## Setting Up Project Locally


    pip install pipenv
    pipenv shell
    pipenv install llama-index-llms-gemini google-generativeai llama-index-embeddings-gemini 

    pipenv install chromadb
    pipenv install llama_index.vector_stores.chroma
    
- Check pipfile.lock
- create new .py and select the env

#For SQL functionalities

    pipenv install llama-index pymysql -q
    pipenv install ipython
    pipenv install llama-index-embeddings-openai


#Installing specific dependencies for dag-chain.py

    pipenv install llama-index-postprocessor-cohere-rerank > /dev/null

#Installing specific dependencies for dataframe-pipeline.ipynb

    !pip install llama-index llama-index-experimental

#Installing streamlit library for chatbot UI in code-checker.py

    !pip install streamlit

# Setting up environment varaiable containng API private keys

    File > New File > .env

    API keys required for this project:
    
        OPENAI_AP_KEY =
        GOOGLE_AP_KEY =
        PINECONE_AP_KEY =
        COHERE_AP_KEY =
        MISTRAL_AP_KEY =

# Creating a VS Code runner

    > Self executable with dynamic variables

    - Creating a run configuration that loads the environment variables
    - Run and Debug option
    - Create launch.json
    - Update and add env file variables
    - Create code to display the env variable of the OpemAI API Key

## Usage:
