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
- Keys (Super Key, Candidate Key, Primary key, Foreign key)
- DDL & DML
- Referential Integrity
- Indexes
- Constraints
- Transactions and ACID property
- Stored Procedure, Function and Trigger

Now going into details about each of these topics will increase the scope of this post, rather let's learn what they are and what purpose they serve.
In future posts in this series we will go a lot deeper about all of them and some more relevant topics such as Database Partitioning, Sharding in distributed.

#### Table
Relational databases stores data in Tables, consisting of rows and columns. In theoritical perspective, tables are called *Relation*, rows are *Tuples* and columns are referred to as *Attributes*. This is an example of a table with few columns and rows, tables have unique names, unique under a schmea.
 ![alt text](/assets/images/posts/a-table.png)


#### Schema
Schema is the logical design of the databse, in our example of the *Address* Table, the schema is the table name, all the column names and their meta data, like name, data type, constraint etc. The actual data is not shcema, just the desisgn is.
You have understand two things about schema -
- It's the logical design of the database without the data
- Schema has instances or snapshots with real data

Maybe a Object Oriented analogy will help more, schema is like a class definition and instance of that schema is like instances of the class, the real objects.

In our case the schema of the *Address* table will look something like this:
<!-- ![alt text](/assets/images/posts/table-schema.png) -->
```sql
CREATE TABLE [Person].[Address](
	[AddressID] [int] IDENTITY(1,1) NOT FOR REPLICATION NOT NULL,
	[AddressLine1] [nvarchar](60) NOT NULL,
	[AddressLine2] [nvarchar](60) NULL,
	[City] [nvarchar](30) NOT NULL,
	[StateProvinceID] [int] NOT NULL,
	[PostalCode] [nvarchar](15) NOT NULL,
	[SpatialLocation] [geography] NULL,
	[rowguid] [uniqueidentifier] ROWGUIDCOL  NOT NULL,
	[ModifiedDate] [datetime] NOT NULL,
 CONSTRAINT [PK_Address_AddressID] PRIMARY KEY CLUSTERED 
(
	[AddressID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
```

#### Keys
##### Super Key
Super key is a set of columns in a table that when considered collectively can uniquely identify each row of the table. consider following table:
```sql
Instructor (ID, Name, DepartmentName)
```
In this Instructor table we can identify several combination that can uniquely identify each row. All of them are super keys.
* {ID}
* {ID, Name}
* {ID, DepartmentName}
* {ID, Name, DepartmentName}
* {Name, DepartmentName}

##### Candidate Key
A candidate key is a minimal super key that when you take out one of it's item loses the status of super key. Let's examine each Super key to identify the candidate keys by this formula:

* {ID} is a candidate key because if you take out the only column it has it loses the super key status.
* {ID, Name} is not a candidate key, because ID is already a super key thus making the combination not minimal.
* {ID, DepartmentName} same as above, not minimal.
* {ID, Name, DepartmentName} same as above, not minimal.
* {Name, DepartmentName} this is a candidate key because, any of these columns individually is not a super key, but the combination itself is a super key.

So from this analysis we conclude that {ID} and {Name, DepartmentName} are the only candidate keys we have in the instructor table.

##### Primary key
From several candidate keys the one chosen by the database designer to be used as the principal way to identify a row is called Primary Key.

##### Foreign key



#### DDL
DDL stands for Data Definition Language and it is used to define varios database objects like Table, Stored Procedure, Function etc. The above image show an example of DDL where you can see statement `CREATE TABLE` and then the schema, table name and also notice that it goes on to describes the whole table with so much details. The DDL let's you 
- Describe the Table (Relation)
- Describe the integrity constraints (we will talk about them shortly)
- Types of values related to each column (Attribute)
- Indeces for the table
- Authorization information
- The physical structure of the data in the disk

#### DML
DML stands for Data Manipulation Language
#### Referential Integrity
#### Indexes
#### Constraints
#### Transactions and ACID property
#### Stored Procedure, Function and Trigger

