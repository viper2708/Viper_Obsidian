# SQL Tutorial Full Database Course

  

**Source** : Youtube

  

[**Video**](https://www.youtube.com/watch?v=HXV3zeQKqGY)

  

## What is a Database (DB)?

*  Any collection related information
	*	Phone Book
	*  Shopping List
	*  Todo List
	*  Your 5 best friends
	*  Facebook's User Base

*  Databases can be stored in different ways
	*  On paper
	*  In your mind
	*  On a computer
	*  This powerpoint
	*  Comments section

*  Database Management Systems (DBMS)
	*  A special software program that helps user create and maintain a database
	*  Makes it easier to manage large amounts of information
	*  Handles security
	*  Backups
	*  Importing/exporting data
	*  Concurrency
	*  Interacts with software applications
		*  Programming languages

*  C.R.U.D
	*  C   --  Create
	*  R   --  Read
	*  U   --  Update
	*  D   --  Delete

*  Two types of databases
	*  Relational Databases (SQL)
		*  Organize data into one or more tables
			*  Each table has columns and rows
			*  A unique key identifies each row
	*  Non-Relational (noSql / not just SQL)
		*  Organize data is anything but a traditional table
			*  Key-value stores
			*  Documents (JSON, XML, etc.)
			*  Graphs
			*  Flexible Tables

*  Relational Databases (SQL)
	*  Relational Database Management Systems (RDBMS)
		*  Help users create and maintain a relational database
			*  mySQL
			*  Oracle
			*  postgreSQL
			*  mariaDB
	*  Structured Query Language (SQL)
		*  Stardardized language for interacting with RDBMS
		*  Used to perform C.R.U.D operations, as well as other administrative tasks (user management, security, backups, etc.)
		*  Used to define tables and structures
		*  SQL code used on one RDBMS is not always protable to another without modification  

*  Non-Relational Databases (noSQL)
	*  Non-Relational Database Management Systems (NRDBMS)
		*  Help users create and maintain a non-relational database
			*  mongoDB
			*  dynamoDB
			*  apache cassandra
			*  firebase, etc.
	*  Implementation Specific
		*  Any non-relational database falls under this category, so there's no set language standard
		*  Most NRCBMS will implement their own language for performing C.R.U.D and administrative operations on the database

*  Database Queries
	*  Queries are requests made to the database management system for specific information
	*  As the database's structure become more and more complex it becomes more difficult to get the specific pieces of information we want
	*  A google search is a Query

*  Summary
	*  Database is any collection of related information
	*  Computer are great for storing databases
	*  DBMS make it easy to create, maintain, and secure a database
	*  DBMS allow you to perform the C.R.U.D operations and other administrative tasks
	*  Two types of Databases : Relational and Non-Relational
	*  Relational databses use SQL and store data in tables with rows and columns
	*  Non-Relational data store data using other data structures

## Tables and Keys

*  Tables are made of rows and columns

*  Types of Keys
	*  Primary Key
	*  Foreign Key
	*  Composite Key

## SQL Basics

*  SQL
	*  SQL is a language used for interacting with RDBMS
		*  You can use SQL to get the RDBMS to do things for you
			*  Create, retrieve, update and delete data
			*  Create and manage databases
			*  Design and create database tables
			*  Perform administration tasks (securit, user management, import/export. etc.)
	*  SQL implementations vary between systems
		*  Not all RDBMS' follow the SQL standard to a 'T'
		*  The concepts are the same but the implementation may vary
	*  SQL is actaully a hybrid language, it's basically 4 types of languages in one
		*  Data Query Language (DQL)
			*  Used to query the database for information
			*  Get information that is already stored there
		*  Data Definition Language (DDL)
			*  Used for controlling access to the data in the database
			*  User and permissions management
		*  Data Manipulation Language (DML)
			*  used for inserting, updating and deleting data from the database

*  Queries
	*  A query is a set of instructions given to the RDBMS (written in SQL) that tell the RDBMS what information you want it to retrieve for you
		*  Tons of data in a DB
		*  Often hidden in a complex schema
		*  Goal is to only get the data you need

## Creating Tables

*  Data types in SQL
	*  INT
	*  DECIMAL(M,N)
	*  VARCAHR(1)
	*  BLOB
	*  DATE
	*  TIMESTAMP

*  Create table syntax
```
        CREATE TABLE table_name(
           column1 datatype,
           column2 datatype,
           column3 datatype,
           .....
           columnN datatype,
           PRIMARY KEY( one or more columns )
        );
```

*  Drop table syntax
```
        DROP TABLE table_name;
```

## Inserting Data

*  Insert data syntax
```
        INSERT INTO TABLE_NAME (column1, column2, column3,...columnN)
        VALUES (value1, value2, value3,...valueN);
```

```
        INSERT INTO TABLE_NAME VALUES (value1,value2,value3,...valueN);
```

  

## Constraints

*  The following are commonly used constraints available in PostgreSQL:
	*  NOT NULL Constraint
		*  Ensures that a column cannot have NULL value.
	*  UNIQUE Constraint
		*  Ensures that all values in a column are different.
	*  PRIMARY Key
		*  Uniquely identifies each row/record in a database table.
	*  FOREIGN Key
		*  Constrains data based on columns in other tables.
	*  CHECK Constraint
		*  The CHECK constraint ensures that all values in a column satisfy certain conditions.
	*  EXCLUSION Constraint
		*  The EXCLUDE constraint ensures that if any two rows are compared on the specified column(s) or expression(s) using the specified operator(s), not all of these comparisons will return TRUE.
	*  DEFAULT Constraint
		*  If nothing is provided the default value is taken as the column value

## Update and Delete

*  Update query syntax
```
        UPDATE table_name
        SET column1 = value1, column2 = value2...., columnN = valueN
        WHERE [condition];
```

*  Delete query syntax
```
        DELETE FROM table_name
        WHERE [condition];
```

## Basic Queries

*  Select query syntax
```
        SELECT column1, column2, columnN FROM table_name;
```

```
        SELECT * FROM table_name;
```

```
        SELECT * FROM table_name WHERE [condition];
```

## More Basic Queries

*  LIMIT clause
	*  The PostgreSQL LIMIT clause is used to limit the data amount returned by the SELECT statement.
```
        SELECT column1, column2, columnN
        FROM table_name
        LIMIT [no of rows]
```

```
        SELECT column1, column2, columnN
        FROM table_name
        LIMIT [no of rows] OFFSET [row num]
```

*  ORDER BY clause
	*  The PostgreSQL ORDER BY clause is used to sort the data in ascending or descending order, based on one or more columns.
```
        SELECT column-list
        FROM table_name
        [WHERE condition]
        [ORDER BY column1, column2, .. columnN] [ASC | DESC];
```

*  GROUP BY clause
	*  The PostgreSQL GROUP BY clause is used in collaboration with the SELECT statement to group together those rows in a table that have identical data. This is done to eliminate redundancy in the output and/or compute aggregates that apply to these groups.
	*  The GROUP BY clause follows the WHERE clause in a SELECT statement and precedes the ORDER BY clause.
```
        SELECT column-list
        FROM table_name
        WHERE [ conditions ]
        GROUP BY column1, column2....columnN
        ORDER BY column1, column2....columnN
```

*  WITH clause
	*  In PostgreSQL, the WITH query provides a way to write auxiliary statements for use in a larger query. It helps in breaking down complicated and large queries into simpler forms, which are easily readable. These statements often referred to as Common Table Expressions or CTEs, can be thought of as defining temporary tables that exist just for one query.
```
        WITH
           name_for_summary_data AS (
              SELECT Statement)
           SELECT columns
           FROM name_for_summary_data
           WHERE conditions <=> (
              SELECT column
              FROM name_for_summary_data)
           [ORDER BY columns]
```

*  HAVING clause
	*  The HAVING clause allows us to pick out particular rows where the function's result meets some condition.
```
        SELECT column1, column2
        FROM table1, table2
        WHERE [ conditions ]
        GROUP BY column1, column2
        HAVING [ conditions ]
        ORDER BY column1, column2
```

*  DISTINCT keyword
	*  The PostgreSQL DISTINCT keyword is used in conjunction with SELECT statement to eliminate all the duplicate records and fetching only unique records.
```
        SELECT DISTINCT column1, column2,.....columnN
        FROM table_name
        WHERE [condition]
```

## Wildcards

*  SQL LIKE operator is used to compare a value to similar values using the wildcard operators.
*  SQL supports two wildcard operators in conjunction with the LIKE operator
	*  The percent sign (%)
		*  Matches one or more characters.
	*  The underscore (_)
		*  Matches one character.

  

## Unions

*  The PostgreSQL UNION clause/operator is used to combine the results of two or more SELECT statements without returning any duplicate rows.
*  To use UNION, each SELECT must have the same number of columns selected, the same number of column expressions, the same data type, and have them in the same order but they do not have to be the same length.
```
        SELECT column1 [, column2 ]
        FROM table1 [, table2 ]
        [WHERE condition]
        UNION
        SELECT column1 [, column2 ]
        FROM table1 [, table2 ]
        [WHERE condition]
```

## Joins

*  The PostgreSQL Joins clause is used to combine records from two or more tables in a database. A JOIN is a means for combining fields from two tables by using values common to each.

*  Join Types in PostgreSQL are −
	*  The CROSS JOIN
	*  The INNER JOIN
	*  The LEFT OUTER JOIN
	*  The RIGHT OUTER JOIN
	*  The FULL OUTER JOIN

*  The CROSS JOIN
	*  A CROSS JOIN matches every row of the first table with every row of the second table. If the input tables have x and y columns, respectively, the resulting table will have x+y columns. Because CROSS JOINs have the potential to generate extremely large tables, care must be taken to use them only when appropriate.
```
            SELECT ... FROM table1 CROSS JOIN table2 ...
```

*  The INNER JOIN
	*  A INNER JOIN creates a new result table by combining column values of two tables (table1 and table2) based upon the join-predicate. The query compares each row of table1 with each row of table2 to find all pairs of rows, which satisfy the join-predicate. When the join-predicate is satisfied, column values for each matched pair of rows of table1 and table2 are combined into a result row.
```
            SELECT table1.column1, table2.column2...
            FROM table1
            INNER JOIN table2
            ON table1.common_filed = table2.common_field;
```

*  The LEFT OUTER JOIN
	*  In case of LEFT OUTER JOIN, an inner join is performed first. Then, for each row in table T1 that does not satisfy the join condition with any row in table T2, a joined row is added with null values in columns of T2. Thus, the joined table always has at least one row for each row in T1.
```
            SELECT ... FROM table1 LEFT OUTER JOIN table2 ON conditional_expression ...
```

*  The RIGHT OUTER JOIN
	*  First, an inner join is performed. Then, for each row in table T2 that does not satisfy the join condition with any row in table T1, a joined row is added with null values in columns of T1. This is the converse of a left join; the result table will always have a row for each row in T2.
```
            SELECT ... FROM table1 RIGHT OUTER JOIN table2 ON conditional_expression ...
```

*  The FULL OUTER JOIN
	*  First, an inner join is performed. Then, for each row in table T1 that does not satisfy the join condition with any row in table T2, a joined row is added with null values in columns of T2. In addition, for each row of T2 that does not satisfy the join condition with any row in T1, a joined row with null values in the columns of T1 is added.
			name_for_summary_data.
```
            SELECT ... FROM table1 FULL OUTER JOIN table2 ON conditional_expression ...
```

## Nested query

*  A subquery is used to return data that will be used in the main query as a condition to further restrict the data to be retrieved.

*  Subqueries with the SELECT Statement
```
            SELECT column_name [, column_name ]
            FROM   table1 [, table2 ]
            WHERE  column_name OPERATOR
                  (SELECT column_name [, column_name ]
                  FROM table1 [, table2 ]
                  [WHERE])
```

*  Subqueries with the INSERT Statement
```
            INSERT INTO table_name [ (column1 [, column2 ]) ]
               SELECT [ *|column1 [, column2 ] ]
               FROM table1 [, table2 ]
               [ WHERE VALUE OPERATOR ]
```

*  Subqueries with the UPDATE Statement
```
            UPDATE table
            SET column_name = new_value
            [ WHERE OPERATOR [ VALUE ]
               (SELECT COLUMN_NAME
               FROM TABLE_NAME)
               [ WHERE) ]
```

*  Subqueries with the DELETE Statement
```
            DELETE FROM TABLE_NAME
            [ WHERE OPERATOR [ VALUE ]
               (SELECT COLUMN_NAME
               FROM TABLE_NAME)
               [ WHERE) ]
```

## Triggers

*  PostgreSQL Triggers are database callback functions, which are automatically performed/invoked when a specified database event occurs.
```
            CREATE  TRIGGER trigger_name [BEFORE|AFTER|INSTEAD OF] event_name
            ON table_name
            [
             -- Trigger logic goes here....
            ];
```

## ER Diagram

*  Entity
	*  An object we want to model and store information about

*  Attributes
	*  Specific pieces of information about an entity

*  Primary Key
	*  An attribute that uniquely identify an entry in the database table

*  Composite attribute
	*  An attribute that can be broken into sub-attributes

*  Multi-valued attribute
	*  An attribute that can have more than one value

*  Derived attribute
	*  An attribute that can be derived from the other attributes

*  Multiple entities
	*  You can define more than one entity in the diagram

*  Relationships
	*  Defines a relationship between two entities

*  Total participation
	*  All members must participate in the relationship

*  Relationship Attribute
	*  An attribute about the relationship

*  Relationship Cardinality
	*  The number of instances of an entity from a relation that can be associated with the relation

*  Weak entity
	*  An entity that cannot be uniquely identified by its attributes alone

*  Identifying relationship
	*  A relationship that serves to uniquely identify the weak entity