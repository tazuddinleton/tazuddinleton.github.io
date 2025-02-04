The absolute minimum series is a series of blogs I intend to write for the beginners. I'll guide you through the software engineering paradigm in this series, you'll learn everything you need to be a solid junior to mid level developer in 2025.


But why am I starting with databases, and not somethign like how to leverage AI? Because you'll learn to leverage AI in 2025 that is a given, what is unsure is that you'll learn the basics of SQL or the basics of any technology in 2025.

The basics are more important than ever to master, specailly becasue of AI.

As a beginner software engineer I hated databases for so long, because I didn't understand them well.
It was not until I had to work in a ERP project and had to write serios sql to generate reports I really understood sql.


Let's start with some concepts around this topic

- What is a database?
In short a database is the collection of data, that is organized in a way that makes it easier and efficient to store, retrieve and manipulate.
- What is DBMS (Database Management System)
A database management system is the tools and services around the database that makes it convenient to interact with the data. 
By management, what means is defining the structure, and techniques to interact and manipulate the information stored.


In practice, a Databse is always comes with a DBMS, when we talk about different databases like MySQL, PostgreSQL, MongoDB,
etc, they are both a Database and a Database Management System. Because without the management system we don't have all the
good stuff like the Data Integrity, Security, Consistency and all that really nice features. Without these features a database barely something
you would want to interact with, and use in your application.

So what are the features that a DBMS gives us?
- ACID properties
- Constraints
- Triggers
- Transactions
- Indexes
- Backup and Recovery and more

So when I refer to a database from now on, I mean both, a database and a database management system that is bunled with it.

Okay now let's look at how many categories of database we have to choose from. There are many, but broadly falls under
two categories:
- Relational Database Management System aka RDBMS, the most popular ones are MySQL, PostgreSQL, Microsoft SQL Server, Oracle Database, etc.
- Non-relatinal Databse Management System, the most popular ones are Cassandra, Redis, MongoDB, Neo4j, etc.

The non-relational databases are of four categories:
- Key-value stores  
- Graph stores
- Column stores
- Document stores

Now, let's look at each of these to understand what they are about, what are the differences and when they should be considered.

### Relational Database Management System
Relational databases or SQL databases stores the data in tables, rows and columns and uses SQL or Structured Query Language to read, write and modify the data.
Without going into lots of detail about theories of relational databses, understanding a few concepts around this will help:
- Table, row and column
- Schema
- DDL
- DML
- Referential Integrity
- Keys (Primary key, Foreign key)
- Indexes
- Constraints
- Transactions and ACID property
- Stored Procedure, Function and Trigger

Now going into details about each of these topics will increase the scope of this post, rather let's learn what they are and what purpose they serve.
In future posts in this series we will go a lot deeper about all of them and some more relevant topics such as Database Partitioning, Sharding in distributed.

We all know the best way to learn is by doing, so let's install a RDBMS and play with the above topics. 
I am going to use PostgreSQL, but you are free to choose any relational db like MySQL, Oracle or MSSQL Server. The goal is to understand the concept andnot learn any particular
database. 

#### Installation
To install PostgreSQL locally without docker you can follow the official page: [Installation Guide](https://www.postgresql.org/download/)

If you want to use docker, make sure you have docker installed and use this compose file to get started:




#### What are the pros of this
#### What the cons
#### When should you consider using it



### Key-value database
As the names suggests a key-value stores the data in key-value structure. 
#### What are the pros of this
#### What the cons
#### When should you consider using it
#### Example use case

### Graph database
Graph database stores data in graphs.
#### What are the pros of this
#### What the cons
#### When should you consider using it

### Column store database
Graph database stores data in graphs.
#### What are the pros of this
#### What the cons
#### When should you consider using it


### Document store database
Graph database stores data in graphs.
#### What are the pros of this
#### What the cons
#### When should you consider using it
