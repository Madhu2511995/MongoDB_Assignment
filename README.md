# MongoDB_Assignment
Connect Python With MongoDB

Title: Connecting MongoDB with Python: A Comprehensive Guide

Introduction:
MongoDB, a popular NoSQL database, offers excellent support for Python through its official driver, PyMongo. This article will guide you through the process of connecting MongoDB with Python using PyMongo, covering the necessary steps and providing code examples to help you get started.

1. Installing PyMongo:
Before connecting to MongoDB from Python, you need to install the PyMongo package. It can be installed using pip, the Python package installer. Open your command prompt and run the following command:
```
pip install pymongo
```

2. Importing PyMongo:
Once PyMongo is installed, you need to import it into your Python script. Include the following line at the beginning of your Python script to import the necessary module:
```python
import pymongo
```

3. Establishing a Connection:
To connect to MongoDB, you need to create a connection object using the `MongoClient` class from PyMongo. The `MongoClient` constructor accepts the MongoDB server's connection string as an argument. Replace `<connection_string>` with the appropriate connection details, such as the server address and port number. Here's an example:
```python
from pymongo import MongoClient

# Create a MongoClient object
client = MongoClient('<connection_string>')
```

4. Accessing a Database:
After establishing a connection, you can access a specific database using the connection object's indexing syntax. Replace `'mydatabase'` with the name of your target database. If the specified database does not exist, MongoDB will create it when you first insert data. Here's an example:
```python
# Access a database
db = client['mydatabase']
```

5. Accessing a Collection:
Once you have a reference to the database, you can access a collection within that database using the indexing syntax. Replace `'mycollection'` with the name of your target collection. If the specified collection does not exist, MongoDB will create it when you first insert data. Here's an example:
```python
# Access a collection
collection = db['mycollection']
```

6. Performing CRUD Operations:
Now that you have a reference to the collection, you can perform various CRUD (Create, Read, Update, Delete) operations on it using PyMongo's methods. Here are some common operations:

- Inserting a Document:
To insert a document into the collection, use the `insert_one()` or `insert_many()` methods. Here's an example using `insert_one()`:
```python
# Insert a document
document = {"name": "John", "age": 30}
result = collection.insert_one(document)
```

- Querying Documents:
To retrieve documents from the collection, use the `find()` method, optionally with a filter. Here's an example:
```python
# Query documents
cursor = collection.find({"age": {"$gt": 25}})
for document in cursor:
    print(document)
```

- Updating Documents:
To update one or more documents in the collection, use the `update_one()` or `update_many()` methods. Here's an example using `update_one()`:
```python
# Update a document
filter = {"name": "John"}
update = {"$set": {"age": 32}}
result = collection.update_one(filter, update)
```

- Deleting Documents:
To delete one or more documents from the collection, use the `delete_one()` or `delete_many()` methods. Here's an example using `delete_one()`:
```python
# Delete a document
filter = {"name": "John"}
result = collection.delete_one(filter)
```

7. Closing the Connection:
After you have finished working with the MongoDB database, it's good practice to close the connection. Use the `close()` method
