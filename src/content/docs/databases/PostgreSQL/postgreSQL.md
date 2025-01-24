# Development platforms – Postgre SQL
In this paper I will walk through the key features of PostgreSQL, its benefits and disadvantages as compared to other popular database systems.
PostgreSQL, from here written as Postgres, is an open-source relational database management system (RDBMS)
## History
PostgreSQL is the successor of the POSTGRES package, developed at the University of California, 
Berkeley, in the mid-1980s. The project was sponsored by several organizations, including 
the Defense Advanced Research Projects Agency (DARPA), the Army Research Office (ARO), 
the National Science Foundation (NSF), and ESL Inc. The implementation began in 1986. 
Version 1 of Postgres was released in 1989, followed by Version 2 in 1990, which incorporated 
feedback and further improvements.
The system initially focused on portability and reliability.

Postgres was used to implement different research and production applications, until Illustra Information Technologies (Now owned by IBM) picked it up and made it commercially available. Because of this, the size of the external user community nearly doubled during 1993. 
The POSTGRES project officially ended with Version 4.2.

In 1994, a SQL language interpreter was added to the original POSTGRES Berkey code, and under a new name, Postgres95, was released as an open-source descendant. This version was important in understanding and identifying problems in the server code, and is part of the reason why it has become an important tool today. 
By 1996, the name Postgres95, got a name change to PostgreSQL, to reflect the original name POSTGRE, and the recent versions with SQL capability. At the same time, they went back to version numbering starting at 6.0.

PostgreSQL is now at version 17.2.

(PostgreSQL, n.d). 
## Why use Postgres?
Postgres is free to use and distribute. It has a strong community of contributors, active
forums, and well-maintained documentation, ensuring that users can easily find solutions to
common issues.

Postgres supports advanced data types such as JSON/JSONB, XML, and arrays. This bridges the 
gap between traditional relational databases and NoSQL systems.

MVCC ensures that Postgres can handle multiple transactions simultaneously without conflicts,
which is crucial for performance in high-demand environments.

Postgres can manage massive datasets efficiently, with its capability to scale from small 
applications to large data warehouses or enterprise systems.

It features like row-level security (RLS) and robust authentication mechanisms make PostgreSQL 
a secure choice for handling sensitive data.

Using primary and foreign keys, PostgreSQL ensures data integrity and avoids duplicate 
information, which helps maintain accuracy across your system.

(MongoDB, n.d.)

## Downsides of Postgres
For beginners, PostgreSQL can be overwhelming, especially given its advanced features and 
complex configuration options.

Compared to lighter alternatives like SQLite or MySQL, PostgreSQL can be more demanding on 
system resources, particularly in memory and CPU usage.

Setting up replication in PostgreSQL can be more complicated compared to systems like MySQL 
or simpler alternatives, requiring more effort and expertise.

PostgreSQL was initially designed to run on a single machine, so scaling can sometimes 
require upgrading hardware or implementing complex clustering solutions. This can become 
costly as your application grows.

## SQL and NoSQL
Relational databases, such as PostgreSQL, organize data into tables, which consist of rows 
and columns. Tables are linked using foreign keys, which establish relationships between 
different datasets. This structure enforces data integrity and consistency, making relational
databases ideal for applications requiring complex queries, transactions, and strict data 
validation.

On the other hand, NoSQL databases (e.g., MongoDB) are designed to handle large volumes of 
unstructured or semi-structured data. Unlike SQL databases, NoSQL systems are schema-less, 
meaning that they do not require a predefined structure for storing data. This flexibility 
is beneficial for applications where the data model may change frequently or when dealing 
with huge amounts of data across distributed systems.

The choice between SQL and NoSQL often depends on the nature of the application. SQL 
databases like PostgreSQL offer strong consistency, robust querying capabilities, and 
well-defined schemas. In contrast, NoSQL databases are better suited for handling 
large-scale, rapidly changing, or unstructured data

(Noroff, n.d.; MongoDB, n.d.).

## PostgreSQL vs. other database systems
### MySQL
PostgreSQL supports more advanced features than MySQL, including custom data types, 
procedural languages, and full compliance with ACID (Atomicity, Consistency, Isolation, 
Durability) principles. This makes PostgreSQL suitable for complex applications that require
advanced data management capabilities.

PostgreSQL strictly adheres to ACID principles, ensuring that transactions are processed 
reliably. MySQL, on the other hand, depends on the storage engine used and may not always 
guarantee full consistency.

While PostgreSQL excels in complex queries and data integrity, MySQL can perform better in 
read-heavy applications due to its simplicity and lighter configuration.
### MongoDB
PostgreSQL provides a structured schema, which helps maintain data integrity through 
relationships and constraints. MongoDB, being schema-less, is more flexible but lacks the 
relational integrity and complex querying capabilities that PostgreSQL offers.

While MongoDB stores data in JSON format, PostgreSQL added JSON and JSONB support in later 
versions, allowing it to store and query semi-structured data efficiently, blurring the 
line between traditional RDBMS and NoSQL. However, it is still more flexible to use NoSQL datastores 
like MongoDB.

(Noroff, n.d.; MongoDB, n.d.).

## How to use
PostgreSQL uses Structured Query Language (SQL) for database operations, adhering to the 
CRUD principles: Create, Read, Update, and Delete. To use PostgreSQL, you need to install 
it on your platform. This can be done through package managers or downloadable installers 
from the official PostgreSQL website.

**Create a new database:**
```
createdb my_yarndatabase
```
**Create a New Table:**
```sql
CREATE TABLE yarn (
id SERIAL PRIMARY KEY,
name VARCHAR(100),
producer VARCHAR(100),
amount NUMERIC
);
```
**Insert data into table:**
```sql
INSERT INTO yarn (name, producer, amount)
VALUES(“finull”, “rauma”, 50)
```
**Query data:**
```sql
SELECT * FROM yarn
```
**Create indexes for improved performance:**
```sql
CREATE INDEX index _amount ON yarn(amount)
```

By following these steps, you can create a PostgreSQL database, define tables, and perform 
basic data manipulation.
## Conclusion
PostgreSQL is a powerful and reliable database management system suitable for a wide 
variety of applications. Its support for advanced data types, and scalability make it a top
choice for developers and organizations looking for a versatile database solution. 

While it has some disadvantages, such as its resource intensity and learning curve for 
beginners, these are often outweighed by its flexibility, security, and active community 
support. Compared to other database systems, PostgreSQL works great in scenarios requiring 
strong data integrity, complex queries, and handling of structured and semi-structured data.

Ultimately, the choice of whether to use PostgreSQL or an alternative depends on the 
specific needs of a project. SQL databases like PostgreSQL are ideal for applications where
consistency, and structured data are priorities, while NoSQL databases may better serve 
projects requiring flexibility, scalability, and handling of unstructured data. 

## Sources
PostgreSQL (n.d.). A Brief History of PostgreSQL. Postgresql.org. https://www.postgresql.org/docs/current/history.html

Noroff (n.d.). Relational Datastores. Mollify.Noroff.dev. https://mollify.noroff.dev/content/feu2/development-platforms/module-1/relational-datastores?nav=undefined

Noroff (n.d.). Non-Relational Datastores. Mollify.Noroff.dev. https://mollify.noroff.dev/content/feu2/development-platforms/module-1/non-relational-datastores?nav=undefined

MongoDB (n.d.). Relational vs. Non-Relational Databases. Mongodb.com. https://www.mongodb.com/resources/compare/relational-vs-non-relational-databases
