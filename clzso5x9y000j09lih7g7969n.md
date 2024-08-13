---
title: "SQL vs NoSQL databases"
seoTitle: "SQL v/s NoSQL Databases, What sets them apart."
seoDescription: "SQL v/s NoSQL Databases, What sets them apart. System Design series by Nandan Kumar"
datePublished: Tue Aug 13 2024 17:01:07 GMT+0000 (Coordinated Universal Time)
cuid: clzso5x9y000j09lih7g7969n
slug: sql-vs-nosql-databases
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723568306196/0a61975f-c413-49e2-9356-d45dc2078bcf.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1723568346930/faeb6cf5-a58d-4aa4-b72c-5281519f98e9.png
tags: nosql, databases, sql, system-design

---

In the world of databases, there are two main types of solutions, SQL (relational) and NoSQL (non-relational) databases. Both of them differ in the way they were built, the kind of information they store, and how they store it. Relational databases are structured and have predefined schemas while non-relational databases are unstructured, distributed, and have a dynamic schema.

## High-level differences

Here are some high-level differences between SQL and NoSQL:

### Storage

SQL stores data in tables, where each row represents an entity and each column represents a data point about that entity.

NoSQL databases have different data storage models such as key-value, graph, document, etc.

### Schema

In SQL, each record conforms to a fixed schema, meaning the columns must be decided and chosen before data entry and each row must have data for each column. The schema can be altered later, but it involves modifying the database using migrations.

Whereas in NoSQL, schemas are dynamic. Fields can be added on the fly, and each *record* (or equivalent) doesn’t have to contain data for each *field*.

### Querying

SQL databases use SQL (structured query language) for defining and manipulating the data, which is very powerful.

In a NoSQL database, queries are focused on a collection of documents. Different databases have different syntax for querying.

### Scalability

In most common situations, SQL databases are vertically scalable, which can get very expensive. It is possible to scale a relational database across multiple servers, but this is a challenging and time-consuming process.

On the other hand, NoSQL databases are horizontally scalable, meaning we can add more servers easily to our NoSQL database infrastructure to handle large traffic. Any cheap commodity hardware or cloud instances can host NoSQL databases, thus making it a lot more cost-effective than vertical scaling. A lot of NoSQL technologies also distribute data across servers automatically.

### Reliability

The vast majority of relational databases are ACID compliant. So, when it comes to data reliability and a safe guarantee of performing transactions, SQL databases are still the better bet.

Most of the NoSQL solutions sacrifice ACID compliance for performance and scalability.

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