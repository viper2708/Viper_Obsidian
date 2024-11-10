## Introduction

* Introduction to JDBC
    * JDBC is an API for the Java programming language that defines how a client may access a Database.
* Architecture of JDBC
    * JDBC supports
        * Two Tier Architecture
        * Three Tier Architecture
    * JDBC contains 2 layers
        * JDBC API - Application-to-JDBC Manager Connection
        * JDBC Driver API - JDBC Manager-to-Driver Connection
* Role of Driver Manager
    * The basic service for managing a set of JDBC drivers
    * Driver Manager updates from JDBC 4.0
        * getConnection and getDrivers methods have been enhanced
        * No need to load JDBC Drivers explicitly
        * Application using Class.forName() will work without modification
        * getConnection method of DriverManager will locate suitable Driver
* Understanding JDBC Driver Types
    * A JDBC driver is a set of Java classes that implement the JDBC interfaces, targeting a specific Database
        * The JDBC interfaces comes with standard Java
        * Implementation of these interfaces is specific to the Database
    * Types of JDBC drivers
        * Type 1 : JDBC-ODBC bridge
            * Advantages
                * It is very easy to use
                * Almost any database is supported
            * Limitations
                * Performance will not be efficient
                * ODBC driver needs to be installed
                * Type 1 drivers are not portable
                * Not suitable for applets
        * Type 2 : Native-API driver
            * Advantages
                * Faster than Type 1 driver
            * Limitations
                * Client Side Library is not available for all databases
                * Vendor Client Library needs to be installed
                * It is a Platform Dependent
                * Not Thread Safe
        * Type 3 : Network-Protocol driver (Middleware driver)
            * Advantages
                * No additional library installation is required on client system
                * No changes are required at client for any Database
                * Supports Caching of Connection, Query Results, Load Balancing, Logging and Auditing etc.
                * A single driver can handle any database provided the middleware supports it
            * Limitations
                * Performace will be slow
                * Requires Database-specific coding
                * Maintenance of Network Protocol driver becomes costly
        * Type 4 : Database-Protocol driver (Pure Java driver)
            * Advantages
                * Platform independent
                * No intermediate format is required
                * Application connects directly to the database server
                * Performance will be very fast
                * JVM manage all aspects
            * Limitations
                * Drivers are database dependent

## Performing basic CRUD operations using JDBC

* Executing static SQL statements
    * Statement interface
        * Used for executing a static SQL statement
        * Methods:
            * ResultSet executeQuery(String SQL)
            * int executeUpdate(String SQL)
            * boolean execute(String SQL)
* Iterating through ResultSets
    * Java.Sql.ResultSet interface represents the result set of a database Query
        * When the ResultSet is first returned, the starting cursor position is before the first row of data
    * Methods of the ResultSet can be divided into 3 categories
        * Navugational methods
        * Get methods
        * Update methods
    * Common methods of ResultSet interface
        * beforeFirst()
        * afterLast()
        * first()
        * last()
        * previous()
        * next()
        * getRow()
    * ResultSet interface get methods
        * get method for each data type
        * Each get method has two versions
            * One that takes in a column name
            * One that takes in a column index
* Understanding Scrollable ResultSets
    * ResultSet Types
        * Type_Forward_Only
        * Type_Scroll_Insensitive
        * Type_Scroll_Sensitive
    * ResultSet Concurrency Types
        * Concur_Read_Only
        * Concur_Updatable
* Understanding Updatable ResultSets
    * Updatable ResultSet allows modification to data in a table through the ResultSet
        * Each Update method has two versions
            * One that takes in a column name
            * One that takes in a column index
    * To update a String Column of the current row
        * public void updateString(int columnIndex, String s)
        * public void updateString(String columnName, String s)
    * Methods to reflect updates to database
        * updateRow()
        * deleteRow()
        * refreshRow()
        * cancelRowUpdates()
        * insertRow()
* Understanding PreparedStatement
    * Benefits
        * Improves performance of an Application
        * Easy to set SQL parameter value
        * Prevents SQL dependency injection attacks

## Working with Stored Procedures

* Understanding CallableStatements
    * A Stored Procedure is a group of SQL statements that perform a particular task
        * Stored Procedures created by DBA
        * Every database has its own language for creating Stored Procedures
    * CallableStatements are used to make a call to the Stored Procedures
        * Types of parameters
            * Input (Default)
            * Output
            * Input Output
* Batch Processing
    * Supported by
        * Statement
        * PreparedStatement
        * CallableStatement
    * Methods
        * addBatch() : Returns void
        * executeBatch() : Returns an array of integer
* IN OUT Parameter
    * Both appropriate setter and RegisterOutParameter method should be used
    * Supplied setter value type 4 JDBC type supplied to the method RegisterOutParameter should be same

## Working with CLOB and BLOB

* What is CLOB
    * A CLOB(Character Large Object) is a collection of character data stored as a single entity in a database
* What is BLOB
    * A BLOB (Binary Large Object) is a collection of Binary data stored as a single entity in a database
    * BLOBs are typically documents, images, audio or other binary objects

## Working with Metadata

* Metadata Programming is useful to know the capabilities, limitations and facilities of underlying database software and its resources
    * JDBC Metadata programming concepts
        * Databse Metadata
        * ResultSet Metadata
        * Parameter Metadata