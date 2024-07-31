# LlamaIndex-Agent-Applications




## Description:

### LlamaIndex:

It is a framework for building context-augmented LLM Applications. It provides tools to make a multitude of Applications from prototype to production. These tools allow:

    1. Ingest Data and storing in Vector Stores
    2. Implement Complex Querying Workflows combining data access with LLM prototyping

### Agents:

It is an automated *reasoning* and *decision* engine. It can take a user input/query and can make internal decisions for executing that query in order to return the correct answer. Its components include 

- Breaking Complex question into smaller parts
- Choosing external tool to use + coming up with parameters for calling the tool.
- Planning out a set of tasks.
- Storing previously completed tasks in memory module

* Use Case Applications:

   - **Agentic RAG**
   - **SQL Agent**
   - **Pandas DataFrame Agent**
   - **Workflow Assistant**
   - **Coding Assitant**


## Methods Implemented
### Data-Backed LLM Applications

1. Structured Data Extraction

> Pydantic Extractors: Extract structured data from unstructured sources like PDFs and websites using LLMs. Essential for automating workflows by filling in missing pieces in a type-safe way.
   
2. Query Engines

> End-to-End Pipelines: Handle natural language queries and return responses with reference context retrieved and passed to the LLM.
   
3. Chat Engines

> Conversational Pipelines: Facilitate multiple back-and-forth interactions with your data instead of a single question-and-answer.

4. Agents

> Automated Decision-Makers: Use LLMs to interact with the world via a set of tools, dynamically deciding the best course of action to complete tasks.

### Retrieval-Augmented Generation (RAG)
   
Integrate your data with LLMs to enhance their capabilities. Crucial for chatbots, agents, and any data-driven LLM application.

![ScreenShot](/basic_rag.png)

> Loading: Import data from various sources like text files, PDFs, websites, databases, or APIs.

> Indexing: Create vector embeddings and other metadata for efficient data querying.

> Storing: Save indexed data and metadata to avoid re-indexing.

> Querying: Utilize various strategies for efficient and relevant data retrieval.

> Evaluation: Assess the pipeline’s effectiveness, accuracy, and speed.


### LlamaIndex Framework:

* Nodes and Documents:
  
  - Nodes represent chunks of data with metadata, while Documents are containers for data sources.
  
* Connectors:
  
  - Ingest data from various sources into Documents and Nodes. These could be APIs, PDFs, SQL and many other availaible on [llamaInde](https://docs.llamaindex.ai/en/stable/)


* Data Indexes:

  - Store vector embeddings and metadata for efficient data retrieval. It is a data structure that allows quick retrival of relevant context for a user query. At high level, indexes are built from documents, and enable LLM models to Q/A, and chat over the data.

  - Indexes store data in Node objects, (which represent chunks of the original documents), and expose a retriever interface that supports additional configuration, and automation.

  - The commonly used vector indexes are VectorStoreIndex, Pinecone, FAISS etc.
  -  For efficient semantic operations, the documents are broken into smaller chunks, or node objects. And we also store each document along with metadata of the document. For that the LlamaIndex offers *Spliiters* to chunk the documents.

* Query Engines:

  - Its is a generic interface that allows us to ask question over the data. It takes Natural-Language query and returns a rich response built on one or many indexes via retrievers.
 
  - We combined multiple query engines to achieve more advanced capability.
 
  - Query engines provide various post-processing capabilities such as *Response synthesizer, or Node Post processors*.
 

### Key Stages:

* Loading:
  
  - Import data from various sources like text files, PDFs, websites, databases, or APIs.

* Indexing:
  - Create vector embeddings and other metadata for efficient data querying.

- Storing: Save indexed data and metadata to avoid re-indexing.

- Querying: Utilize various strategies for efficient and relevant data retrieval.

- Evaluation: Assess the pipeline’s effectiveness, accuracy, and speed.






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
