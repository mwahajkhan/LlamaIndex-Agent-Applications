# LlamaIndex-Agent-Applications




## Description:

### LlamaIndex:

It is a framework for building context-augmented LLM Applications. It provides tools to make a multitude of Applications from prototype to production. These tools allow:

    1. Ingest Data and storing in Vector Stores
    2. Implement Complex Querying Workflows combining data access with LLM prototyping

### Agents:

It is an automated *reasoning* and *decision* engine. It can take a user input/query and can make internal decisions for executing that query in order to return the correct answer. Its components include 

- Breaking Complex questions into smaller parts
- Choosing an external tool to use + coming up with parameters for calling the tool.
- Planning out a set of tasks.
- Storing previously completed tasks in the memory module

![ScreenShot](/images/agent_reasoning_loop.png)

* Agents use Case Applications:

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
   
Integrate your data with LLMs to enhance their capabilities. This is crucial for chatbots, agents, and any data-driven LLM application. RAG techniques combine the enterprise's data with the Natural Language Processing capabilities of LLMs which include:

 - Recommendation   - Decisioning  - Query Responses   - Content Generation   - Summarization

- RAG architecture, combined with agents, and LLM generative model provides robust and scalable applications across different industries.

![ScreenShot](/images/basic_rag.png)



### LlamaIndex Framework:

* Nodes and Documents:
  
  - Nodes represent chunks of data with metadata, while Documents are containers for data sources.
  
* Connectors:
  
  - Ingest data from various sources into Documents and Nodes. These could be APIs, PDFs, SQL, and many others availaible on [llamaInde](https://docs.llamaindex.ai/en/stable/)


* Data Indexes:

  - Store vector embeddings and metadata for efficient data retrieval. It is a data structure that allows quick retrieval of relevant context for a user query. At a high level, indexes are built from documents and enable LLM models to Q/A, and chat over the data.

  - Indexes store data in Node objects, (which represent chunks of the original documents), and expose a retriever interface that supports additional configuration, and automation.

  - The commonly used vector indexes are VectorStoreIndex, Pinecone, FAISS, etc.
  -  For efficient semantic operations, the documents are broken into smaller chunks, or node objects. And we also store each document along with metadata of the document. For that the LlamaIndex offers *Spliiters* to chunk the documents.

![ScreenShot](/images/vector_store_query.png)

* Query Engines:

  - Its is a generic interface that allows us to ask question over the data. It takes Natural-Language query and returns a rich response built on one or many indexes via retrievers.
 
  - We combined multiple query engines to achieve more advanced capability.
 
  - Query engines provide various post-processing capabilities such as *Response synthesizer, or Node Post processors*.
 
![ScreenShot](/images/query_engine.png) 

### Key Stages:

* **Prompts:**

  - In programmatic interactions with LLMs the prompts have to be specialized and include context. The prompt has the following components:

    1. InstrUctions: Tell the model what role it is playing, the situation, response approach, how to use external information if provided. What to do with the query and how to construct the output.
    2. External Information: Context additional information for the model can be manually inserted into prompts, retrived via vector database, or pulled via other means.
    3. User Input/Query: A query input or question to the system by the user.
    4.  Output Indicator: Determines the format of the to-be-generated response. The prompt can mention a meaningful textual structure or a technical structure like JSON, XML, or HTML etc. In RAG applications the prompts have to be generic so the variables passed in the prompt have to be dynamic so they can change based on the question provided by the user.
   
* **Semantic Similarity Evaluator**

To check whether the two pieces of text are similar to each other, especially in RAG application to retrieve relevant and concise context for augmented/final prompt to be sent to the LLM. To perform, semantic similarity, the pieces of text must be embedded, then the similarity search operations find the distance between language embeddings in the n-dimensional space.  

* **Language Embeddings:**

Embeddings are vectors created as numerical representations of non-numerical data objects like Natural Language, images, sounds, etc. In the case of Natural Language Processing embedding vectors capture the **semantic and syntactic** senses. The embedding models involve complex machine learning techniques including sophisticated neural networks. Text embeddings capture the semantic meanings of words, and their relationships within a language, as they encode semantic simalarity between words. Some common text embedding models are:

-> TF-IDF (Term frequency -Inverse document frequency    -> Word-2-Vec    -> BERT (Bidirectional Encode Representations from Transformers)

The simalarity between two data points can be measured via:

1. Euclidean Distance
    
2. Cosine Distance


* **Vector Databases:**

These are specialized databases that can store and retrieve Embedding Vectors, as high-dimensional points. They have specialized capabilities for efficient and smart lookup of nearest neighbors in the N-dimensional space. They offer comprehensive data management capabilities, allowing for meta data storage, filtering, and dynamic querying based on associated meta-data. Vector databases are scalable and can handle large volumes of vector data, ensuring high performance as data grows.


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
