---
title: "System Design : SQL vs NoSQL databases"
seoTitle: "SQL v/s NoSQL Databases, What sets them apart."
seoDescription: "SQL v/s NoSQL Databases, What sets them apart. System Design series by Nandan Kumar"
datePublished: Tue Aug 13 2024 17:01:07 GMT+0000 (Coordinated Universal Time)
cuid: clzso5x9y000j09lih7g7969n
slug: system-design-sql-vs-nosql-databases
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723568306196/0a61975f-c413-49e2-9356-d45dc2078bcf.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1723568346930/faeb6cf5-a58d-4aa4-b72c-5281519f98e9.png
tags: nosql, databases, sql, system-design

---

In the realm of databases, two primary types of solutions exist, SQL (relational) and NoSQL (non-relational) databases. These two categories differ significantly in their construction, the nature of the data they store, and their storage methods. Relational databases are structured with predefined schemas, while non-relational databases are unstructured, distributed, and feature dynamic schemas.

## High-level differences

Here are some high-level differences between SQL and NoSQL:

### Storage

SQL stores data in tables where each row represents an entity, and each column represents a data point related to that entity.

NoSQL databases utilize various data storage models, including key-value, graph, and document-oriented approaches.

### Schema

In SQL, each record follows a fixed schema, which means that the columns must be determined and chosen before data entry, and each row must contain data for each column. The schema can be modified later, but this involves modifying the database using migrations.

NoSQL schemas are dynamic. Fields can be added on the fly, and each *record* doesn’t have to contain data for each *field*.

### Querying

SQL databases use Structured Query Language (SQL) to define and manipulate data, which is highly powerful.

In a NoSQL database, queries focus on a collection of documents, with different databases having different syntax for querying.

### **Scalability**

In most cases, SQL databases can be scaled vertically, which can become very costly. While it's feasible to scale a relational database across multiple servers, it's a difficult and time-consuming process.

NoSQL databases are horizontally scalable, which means it's easy to add more servers to handle large traffic. They can be hosted on inexpensive hardware or cloud instances, making them cost-effective compared to vertical scaling. Many NoSQL technologies also distribute data across servers automatically.

### Reliability

The majority of relational databases are ACID compliant. Therefore, SQL databases are still the best choice for data reliability and transaction safety.

Many NoSQL solutions prioritize performance and scalability over ACID compliance.

## Reasons

As always we should always pick the technology that fits the requirements better. So, let’s look at some reasons for picking SQL or NoSQL based database:

**For SQL**

* Structured data with strict schema
    
* Relational data
    
* Need for complex joins
    
* Transactions
    
* Lookups by index are very fast
    

**For NoSQL**

* Dynamic or flexible schema
    
* Non-relational data
    
* No need for complex joins
    
* Very data-intensive workload
    
* Very high throughput for IOPS
    

That's all folks.

Feel free to comment on how you like my blog on the system design series or shoot me an email at [connect@nandan.dev](http://mailto:connect@nandan.dev) If you have any queries I will try to answer them.

You can also visit my website to read some of the articles at [https://nandan.dev/](https://nandan.dev/)

Stay tuned & connect with me on my social media channels. Subscribe to my newsletter to get regular updates on my upcoming posts.

If you're interested in learning about system design, you can join Design Guru's course on [System Design Fundamentals](https://www.designgurus.io/course/grokking-system-design-fundamentals?aff=y0pphf).

[Twitter](https://twitter.com/_sirius93_) | [Instagram](https://www.instagram.com/nandandotdev) | [Github](https://github.com/sirius93) | [Website](https://nandan.dev)