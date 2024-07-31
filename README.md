# LlamaIndex-Agent-Applications

## Description:

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
