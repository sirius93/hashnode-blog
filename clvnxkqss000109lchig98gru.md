---
title: "System Design: Databases and DBMS"
seoTitle: "System Design: Databases and DBMS - All about Databases - Nandan Kumar"
seoDescription: "Covers the topic of Databases and DBMS, providing information on all aspects of databases. Authored by Nandan Kumar."
datePublished: Wed May 01 2024 14:46:55 GMT+0000 (Coordinated Universal Time)
cuid: clvnxkqss000109lchig98gru
slug: system-design-databases-and-dbms
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714574316849/b1e9a1fc-40ed-4676-ac2c-2459738c6a53.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1714574673480/3c6ece46-4865-4b47-bd3c-4ebff15cc612.png
tags: software-architecture, databases, devops, software-engineering, system-design

---

## What is a Database?

A database is a structured collection of information or data that is typically stored electronically in a computer system. The management of the database is usually done by a Database Management System (DBMS). The combination of the data and the DBMS, along with the related applications, is commonly referred to as a database system, which is often shortened to just database.

## What is DBMS?

A database is a collection of data that requires a comprehensive database software program, known as a Database Management System (DBMS), to function. Essentially, a DBMS serves as an interface between the database and its end-users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized. Additionally, a DBMS enables oversight and control of databases, enabling a variety of administrative operations such as performance monitoring, tuning, backup, and recovery.

## Components

Here are some commonly found components that are present in different databases:

### Schema

A schema is responsible for defining the structure of a data storage system and specifying the types of data that can be stored in it. Schemas can be strictly enforced throughout the entire database, enforced loosely in some areas, or not enforced at all.

### Table

Each table can have anywhere from two to over a hundred columns, depending on the type of information it contains, similar to a spreadsheet.

### Column

A database column contains a single data value of a particular type for each row. The data value can be text, number, enum, timestamp, etc.

### Row

Data in a table is recorded in rows. There can be thousands or millions of rows in a table having any particular information.

## Types

![database-types](https://nandan.dev/system-design/images/database-types.png align="left")

Below are different types of databases:

* [**SQL**](https://nandan.dev/pages/courses/system-design/sql-databases)
    
* [**NoSQL**](https://nandan.dev/pages/courses/system-design/nosql-databases)
    
    * Document
        
    * Key-value
        
    * Graph
        
    * Timeseries
        
    * Wide column
        
    * Multi-model
        

## Challenges

Here's a revised version of the text to make it clearer and free of spelling, grammar, and punctuation errors:

Running databases at scale can pose some common challenges that need to be addressed.

* **Absorbing significant increases in data volume**: The explosion of data from sensors, connected machines, and other sources is increasing rapidly.
    
* **Ensuring data security**: Data breaches are becoming increasingly common, making it more important than ever to prioritize both data security and user accessibility.
    
* **Keeping up with demand**: For timely decision-making and seizing new opportunities, companies require real-time access to their data.
    
* **Managing and maintaining the database and infrastructure**: As data volumes increase and databases become more complex, companies face the expense of hiring additional talent to manage them.
    
* **Removing scalability limits**: A business needs to grow to survive, and its data management must grow with it. However, predicting the required capacity of on-premises databases can be challenging.
    
* **Ensuring data residency, data sovereignty, or latency requirements**: Some organizations have use cases that are better suited to run on-premises. In those cases, engineered systems that are pre-configured and pre-optimized for running the database are ideal..
    

# SQL databases

A SQL or relational database is a collection of items that are related to each other and organized into tables consisting of columns and rows. These tables hold the information about the objects to be represented in the database. Each column in a table holds a specific type of data, and each field stores the actual value of an attribute. The rows in the table represent a collection of related values of one object or entity.

Each row in a table can be identified uniquely with a primary key, and the rows among multiple tables can be related to each other using foreign keys. This data can be accessed in many different ways without the need to reorganize the database tables themselves. SQL databases usually follow the [ACID consistency model](https://nandan.dev/pages/courses/system-design/acid-and-base-consistency-models#base#acid).

## Materialized views

A materialized view is a pre-computed dataset that is derived from a query specification and stored for later use. The data is pre-computed, which makes querying a materialized view faster than executing a query against the base table of the view. This performance difference is significant when a query is run frequently or is complex.

Materialized views enable data subsetting, which improves the performance of complex queries that run on large datasets and reduces network loads. Though there are other uses of materialized views, they are primarily used for performance and replication purposes.

## N+1 query problem

The N+1 query problem occurs when the data access layer executes additional SQL statements (N) to retrieve the same data that could have been obtained when executing the primary SQL query. The greater the value of N, the more queries will be executed, leading to a performance impact.

This problem is commonly observed in GraphQL and ORM (Object-Relational Mapping) tools. It can be solved by optimizing the SQL query or by using a dataloader that batches consecutive requests and makes a single data request under the hood.

## Advantages

Let’s look at some advantages of using relational databases:

* Simple and accurate
    
* Accessibility
    
* Data consistency
    
* Flexibility
    

## Disadvantages

Below are the disadvantages of relational databases:

* Expensive to maintain
    
* Difficult schema evolution
    
* Performance hits (join, denormalization, etc.)
    
* Difficult to scale due to poor horizontal scalability
    

## Examples

Here are some commonly used relational databases:

* [PostgreSQL](https://www.postgresql.org/)
    
* [MySQL](https://www.mysql.com/)
    
* [MariaDB](https://mariadb.org/)
    
* [Amazon Aurora](https://aws.amazon.com/rds/aurora)
    

# NoSQL databases

NoSQL refers to a category of databases that do not primarily use SQL as their data access language. These databases are also known as non-relational databases. Unlike relational databases, NoSQL databases do not require data to follow a predefined schema. NoSQL databases follow [BASE consistency model](https://nandan.dev/pages/courses/system-design/acid-and-base-consistency-models#base).

Below are different types of NoSQL databases:

### Document

A document database, also known as a document-oriented database or a document store, is a versatile database that stores information in the form of documents. These databases can be used for transactional and analytical applications.

**Advantages**

* Intuitive and flexible
    
* Easy horizontal scaling
    
* Schemaless
    

**Disadvantages**

* Schemaless
    
* Non-relational
    

**Examples**

* [MongoDB](https://www.mongodb.com/)
    
* [Amazon DocumentDB](https://aws.amazon.com/documentdb)
    
* [CouchDB](https://couchdb.apache.org/)
    

### Key-value

One of the simplest types of NoSQL databases, key-value databases save data as a group of key-value pairs made up of two data items each. They’re also sometimes referred to as a key-value store.

**Advantages**

* Simple and performant
    
* Highly scalable for high volumes of traffic
    
* Session management
    
* Optimized lookups
    

**Disadvantages**

* Basic CRUD
    
* Values can’t be filtered
    
* Lacks indexing and scanning capabilities
    
* Not optimized for complex queries
    

**Examples**

* [Redis](https://redis.io/)
    
* [Memcached](https://memcached.org/)
    
* [Amazon DynamoDB](https://aws.amazon.com/dynamodb)
    
* [Aerospike](https://aerospike.com/)
    

### Graph

A graph database is a type of NoSQL database that uses graph structures to store and represent data. Instead of tables or documents, it uses nodes, edges, and properties to create relationships between data items.

The nodes represent the data items, while the edges represent the relationships between them. The relationships allow data in the store to be linked together directly and can be retrieved with a single operation in many cases.

**Advantages**

* Query speed
    
* Agile and flexible
    
* Explicit data representation
    

**Disadvantages**

* Complex
    
* No standardized query language
    

**Use cases**

* Fraud detection
    
* Recommendation engines
    
* Social networks
    
* Network mapping
    

**Examples**

* [Neo4j](https://neo4j.com/)
    
* [ArangoDB](https://www.arangodb.com/)
    
* [Amazon Neptune](https://aws.amazon.com/neptune)
    
* [JanusGraph](https://janusgraph.org/)
    

### Time series

A time-series database is a database optimized for time-stamped, or time series, data.

**Advantages**

* Fast insertion and retrieval
    
* Efficient data storage
    

**Use cases**

* IoT data
    
* Metrics analysis
    
* Application monitoring
    
* Understand financial trends
    

**Examples**

* [InfluxDB](https://www.influxdata.com/)
    
* [Apache Druid](https://druid.apache.org/)
    

### Wide column

Wide column databases, also known as wide column stores, are schema-agnostic. Data is stored in column families, rather than in rows and columns.

**Advantages**

* Highly scalable, can handle petabytes of data
    
* Ideal for real-time big data applications
    

**Disadvantages**

* Expensive
    
* Increased write time
    

**Use cases**

* Business analytics
    
* Attribute-based data storage
    

**Examples**

* [BigTable](https://cloud.google.com/bigtable)
    
* [Apache Cassandra](https://cassandra.apache.org/)
    
* [ScyllaDB](https://www.scylladb.com/)
    

### Multi-model

Multi-model databases combine different database models (i.e. relational, graph, key-value, document, etc.) into a single, integrated backend. This means they can accommodate various data types, indexes, queries, and store data in more than one model.

**Advantages**

* Flexibility
    
* Suitable for complex projects
    
* Data consistent
    

**Disadvantages**

* Complex
    
* Less mature
    

**Examples**

* [ArangoDB](https://www.arangodb.com/)
    
* [Azure Cosmos DB](https://azure.microsoft.com/en-in/services/cosmos-db)
    
* [Couchbase](https://www.couchbase.com/)
    

That's all folks.

In the next blog, I will try to cover more about SQL V/s NoSQL Databases.

Feel free to comment on how you like my blog on the system design series or shoot me an email at [connect@nandan.dev](http://mailto:connect@nandan.dev) If you have any queries I will try to answer them.

You can also visit my website to read some of the articles at [https://nandan.dev/](https://nandan.dev/)

Stay tuned & connect with me on my social media channels. Subscribe to my newsletter to get regular updates on my upcoming posts.

If you're interested in learning about system design, you can join Design Guru's course on [System Design Fundamentals](https://www.designgurus.io/course/grokking-system-design-fundamentals?aff=y0pphf).

[Twitter](https://twitter.com/_sirius93_) | [Instagram](https://www.instagram.com/nandandotdev) | [Github](https://github.com/sirius93) | [Website](https://nandan.dev)