# Databases-for-DevOps-Engineers

![](Databases.png)  

## Self Assessment

<details>
<summary><b><i>1.What type of databases are you familiar with?</i></b></summary>

$\color{green}{\text{Answer}}$

- Relational (SQL)
- NoSQL
- Time series

</details>

## SQL

<details>
<summary><b><i>2.What is a relational database?</i></b></summary>

$\color{green}{\text{Answer}}$

Data Storage: system to store data in tables

SQL: programming language to manage relational databases

Data Definition Language: a standard syntax to create, alter and delete tables

</details>

<details>
<summary><b><i>3.What does it mean when a database is ACID compliant?</i></b></summary>

$\color{green}{\text{Answer}}$

ACID stands for Atomicity, Consistency, Isolation, Durability. In order to be ACID compliant, the database must meet each of the four criteria

1. Atomicity - When a change occurs to the database, it should either succeed or fail as a whole.

For example, if you were to update a table, the update should completely execute. If it only partially executes, the update is considered failed as a whole, and will not go through - the DB will revert back to it's original state before the update occurred. It should also be mentioned that Atomicity ensures that each transaction is completed as it's own stand alone "unit" - if any part fails, the whole statement fails.

2. Consistency - any change made to the database should bring it from one valid state into the next.

For example, if you make a change to the DB, it shouldn't corrupt it. Consistency is upheld by checks and constraints that are pre-defined in the DB. For example, if you tried to change a value from a string to an int when the column should be of datatype string, a consistent DB would not allow this transaction to go through, and the action would not be executed

3. Isolation - this ensures that a database will never be seen "mid-update" - as multiple transactions are running at the same time, it should still leave the DB in the same state as if the transactions were being run sequentially.

For example, let's say that 20 other people were making changes to the database at the same time. At the time you executed your query, 15 of the 20 changes had gone through, but 5 were still in progress. You should only see the 15 changes that had completed - you wouldn't see the database mid-update as the change goes through.

4. Durability - Once a change is committed, it will remain committed regardless of what happens (power failure, system crash, etc.). This means that all completed transactions must be recorded in non-volatile memory.

Note that SQL is by nature ACID compliant. Certain NoSQL DB's can be ACID compliant depending on how they operate, but as a general rule of thumb, NoSQL DB's are not considered ACID compliant

</details>

<details>
<summary><b><i>4.What is sharding?</i></b></summary>

$\color{green}{\text{Answer}}$

Sharding is a horizontal partitioning.

</details>

<details>
<summary><b><i>5.You find out your database became a bottleneck and users experience issues accessing data. How can you deal with such situation?</i></b></summary>

$\color{green}{\text{Answer}}$

Not much information provided as to why it became a bottleneck and what is current architecture, so one general approach could be to reduce the load on your database by moving frequently-accessed data to in-memory structure.

</details>

<details>
<summary><b><i>6.What is a connection pool?</i></b></summary>

$\color{green}{\text{Answer}}$

Connection Pool is a cache of database connections and the reason it's used is to avoid an overhead of establishing a connection for every query done to a database.

</details>

<details>
<summary><b><i>7.What is a connection leak?</i></b></summary>

$\color{green}{\text{Answer}}$

A connection leak is a situation where database connection isn't closed after being created and is no longer needed.

</details>

<details>
<summary><b><i>8.What is Table Lock?</i></b></summary>

$\color{green}{\text{Answer}}$

A Table Lock is a database mechanism that locks an entire table to prevent other transactions from modifying or accessing its data concurrently, ensuring data consistency during bulk operations.

</details>

<details>
<summary><b><i>9.Your database performs slowly than usual. More specifically, your queries are taking a lot of time. What would you do?</i></b></summary>

$\color{green}{\text{Answer}}$

- Query for running queries and cancel the irrelevant queries
- Check for connection leaks (query for running connections and include their IP)
- Check for table locks and kill irrelevant locking sessions

</details>

<details>
<summary><b><i>10.What is a Data Warehouse?</i></b></summary>

$\color{green}{\text{Answer}}$

A data warehouse is a subject-oriented, integrated, time-variant and non-volatile collection of data in support of organisation's decision-making process.

</details>

<details>
<summary><b><i>11.Explain what is a time-series database.</i></b></summary>

$\color{green}{\text{Answer}}$

A time-series database (TSDB) is a software system optimized for storing, querying, and analyzing large volumes of time-stamped data, such as metrics, logs, or sensor readings, tracked over time.

</details>


