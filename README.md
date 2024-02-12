# python-mongo-library
[![Made with Python](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)](https://www.python.org)
[![Made with MongoDB](https://img.shields.io/badge/ArangoDB-DDE072?style=for-the-badge&logo=ArangoDB&logoColor=white](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://ferretdb.io)

Playground CRUD application in Python to manage a Public Library. Backed by MongoDB or similar.

## Requirements
- Python HTTP REST server with configurable environment variables (e.g. `$PORT`, `$MONGO_URL`, `$MONGO_USER`, `$MONGO_PASSWORD`)
- Script to launch the Dockerized version of the database
- Dockerfile to containerise the Python App
- Github Actions Pipeline to build the Docker image and push to Dockerhub to every released git tag.
- Optional: Frontend application to consume the Python API and corresponding Dockerfile

## Goals

- Learn Python
- Learn REST API convention
- Learn Unit Testing and Mocking (the database)
- Learn Project foldering
- Learn Docker
- Learn Github Action pipelines
- Learn Git Tagging
- Learn NoSQL Database Paradigm
- Learn CRUD (Create Read Update Release)

## Features

These the features:
- Each book has a title, author, genre, and the number of copies available.
- Each author has a name, birth year, and country.
- Each member has a name, email, and membership type (e.g., Premium, Standard).
- Each loan links a book to a member, with loan and return dates, and a flag indicating whether the book has been returned.
- These JSON documents can be stored in MongoDB collections named `books`, `authors`, `members`, and `loans`, respectively.

## JSON Collections structures

The collections must be:

`books`
```json
{
    "_id": ObjectId("5ff1ba4af2a2ff3a49c65435"),
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "genre": "Fiction",
    "copies": 10
}
```

`authors`
```json
{
    "_id": ObjectId("5ff1ba4af2a2ff3a49c65436"),
    "name": "F. Scott Fitzgerald",
    "birth_year": 1896,
    "country": "United States"
}
```

`members`
```json
{
    "_id": ObjectId("5ff1ba4af2a2ff3a49c65437"),
    "name": "John Doe",
    "email": "john@example.com",
    "membership_type": "Premium"
}
```

`loans`
```json
{
    "_id": ObjectId("5ff1ba4af2a2ff3a49c65438"),
    "book_id": ObjectId("5ff1ba4af2a2ff3a49c65435"),
    "member_id": ObjectId("5ff1ba4af2a2ff3a49c65437"),
    "loan_date": ISODate("2021-01-04T10:10:00Z"),
    "return_date": ISODate("2021-01-14T10:10:00Z"),
    "returned": true
}
```

## Hints

- Instead of Using MongoDB in the very spirit of Open Source you can evaluate to use [FerretDB](https://docs.ferretdb.io/quickstart-guide/docker) which is an Open Source alternative backed by PostGres
- Use the best practices of programming: do not push on `main`, merge only approved PRs, encourage discussions over PR Reviews and Issues
- Write unit tests where possible by mocking the access to the database
- Optimise the Dockerfile size and take care of Container security

## Contributing

Everyone is welcome to contribute! Get in touch with the Owners of the repository if you're willing to help!
