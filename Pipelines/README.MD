## Pipeline

### SQL Database
**SQLAlchemy** is a Python toolkit and object-relational mapper (ORM) that gives application developers the full power and flexibility of working with SQL databases and tables.

#### Features of SQLAlchemy
- **Object Relational Mapper (ORM)**: SQLAlchemy provides an object mapping on top of the MySQL database, allowing object-based entity creation within the application programming interface (API).
- **Interaction with Database**: SQLAlchemy provides object mapping against each of the SQL schema objects in the database, making it easier to work with SQL databases programmatically.

#### Example Usage
```python
from sqlalchemy import create_engine, text
from llama_index.core import SQLDatabase
from llama_index.llms.openai import OpenAI

# SQLAlchemy provides an object-relational mapper
# Create an engine and interact with the database
engine = create_engine('sqlite:///example.db')

### Llama Index Query Pipelines
- **Llama Index Query Pipelines is a new declarative API within LlamaIndex that allows you to concisely orchestrate simple-to-advanced query workflows within RAG applications.

###Features of Llama Index Query Pipelines
- **Query Pipeline Abstraction: At the core of this is the Query Pipeline abstraction. It can take in many LlamaIndex Modules (LLMs, prompts, query engines, retrievers, etc.) and create a computational graph over these modules.

- **Ease of Use: It makes it easier to build LLM workflows over the data.

### Example Usage:
```python
from llama_index.core.query_pipeline import QueryPipeline
from llama_index.llms.openai import OpenAI

# Define your query pipeline
pipeline = QueryPipeline.from_defaults(
    llm=OpenAI(model="text-davinci-002"),
    retriever=my_retriever,
    prompt_template=my_prompt_template,
    query_engine=my_query_engine
)

# Use the pipeline to process a query
response = pipeline.query("What is the capital of France?")
print(response)

