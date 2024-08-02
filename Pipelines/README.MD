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
