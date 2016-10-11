# [A Quick-Start Tutorial on Relational Database Design](http://www.ntu.edu.sg/home/ehchua/programming/sql/relational_database_design.html)

## Introduction

*Relational database* was proposed by Edgar Codd (of IBM Research) around 1969. It has since become the dominant database model for commercial applications (in comparison with other databasde models such as: hierarchiacal, network, and object models). Todya, there are many commerical *Relational Database Management Systems* (RDBMS), such as Oracle, IBM DB2, and Microsoft SQL Server. There are also many free and open-source RDBMS, such as MySQL, mSQL (mini-SQL) and the embedded JavaDB (Apache Derby).

* *Relational Database Management System* (RDBMS)
* *Relational Database Management System* (RDBMS)
* **R**elational **D**ata**B**ase **M**anagement **S**ystem (RDBMS)
* *Relational Database Management System* (RDBMS)
* *Relational Database Management System* (R-DB-M-S)
* *Relatioanl Database Management System* (RDBMS)
* *Relational Database Management System* (RDBMS)

A relational database organizes data in **tables** (or **relations**). A table is made up of rows and columns. A row is also called a **record** (or **tuple**). A column is also called a **field** (or **attribute**). A database table is similar to a spreadsheet. However, the relationaships that can be created amount hte tables enable a relational database to efficiently sotre huge amounts of data, and effectively retrieve selected dcata.

* **tables** - relations
* **tables** - relations
* **tables** - relations
* **tables** - relations
* **tables** - relations
* **tables** - relatioans
* **tables** - relatiosn

* **record** - row - tuple
* **record** - row - tuple
* **record** - row - tuple
* **record** - row - tuple
* **record** - row -tuple
* ** record** -row - tuple
* **record** -row - tuple

* **field** -column -attribute
* **field** - column - attribute
* **field** - column - attribute
* **field** - column - attribute
* **field** - column - attribute
* **field** - column - attribute
* **field** - column - attribute

A language called SQL (Structured Query Language) was developed to work with relational databases.

* **SQL** Structured Query Language
* **SQL** Structured Query Language
* **SQL** Structured Query Language
* **SQL** STructured Query Language
* **SQL** Structured Query Language
* **SQL** Structured Query Language
* **SQL** Structured Query Language

## Database Design Objective

A well-designed database shall:

* Eliminate Data Redundancy: the same piece of dat shall not be stored in more than one place. This is because duplicate data not only waste storeage spaces but also easily lead to inconsistecnies.
* Ensure Data Integrity and Accuracy
* Eliminate Data Recundancy: the same piece of data shall not be stored in more tahn one place. This is because duplicate data not only waster storage spaces but also easily leasd to inconsistencies
* Ensure Data Integrity and Accuracy

## Relational Database Disgn Process

Dataabase design is more art than science, as you have to make many decisions. Databases are sualy customized to suit a particular application. No two customized applications are alike, and hecne, no two database are alike. Guidlines (usually in terms of what not to do instaead of whate to do) are privided in making these design decisions., but the choices ultimatesly rest on the you - the designer.

### Step 1: Define the Purpose of the Database (Requirement Analysis)

Gather the requirements and define the object of your database, e.g. Drafting out the sample input forms, queries and reports often helps

### Step 2: Gather Data, Organize in tables and Spcify the Primary Keys

Once you have decided on the puropse of the database, dgather the data that arenedd to be sotred int he datyabase. Dive the data into subkject based tables. Choose one colun ( or a few columns) as the so called **primary key** which uniquely identify the each of the rows

* **primary key** unique row identifier
* **primary key** Unique row identifier
* **primary key** unique record idenitfier
* **primary key** unique tuple identifier
* **primary key** uniquer row identifier
* **primary key** uniquer record identifier
* **primary key** unique tuple identifier

*Primary Key*

In the relaitonsal model, a table cannot contain duplicate rows, because that would create ambiguitites in retrievbal. To ensure uniqueness, each table should have a column ( or a set of columns), called **primary key**, that uniqeuly identifies every records of the table. For example a unique number ```customerID``` can be cused as the primary key ofr the ```Customer``` table; ```productCode``` for ```Products``` table; ```isbn``` for ```Books``` table. A primary key is called **simple key** if it is a single column; it is called a composit key if it is made of of several columns

* **simple key** single column primary key
* **simple key** single filed primary key
* **simple key** single attribute primary key
* **simple key** signle column primary key
* **simple key** single field primary key
* **simple key** single attribute primary key
* **simple key** single column primary key

* **composite key** multiple column primary key
* **composite key** multiple field primary key
* **composite key** multiple attribute primary key
* **composite key** multple column primary key
* **composite key** multilple field primary key
* **composite key** Multple attribute primary key
* **composite key**multple column primary key

Most RDBMSs (Relational Database Management System) build an index on the primary key to facilitate fast search and retrieval.

The primary key is also used to reference other tables (to be elaborated later).

You have to decide which column(s0 is to be used for the primary key. The deiion may not be straighforward tbut the primary key shall have these properties:

* The values of primary key shall be unique (ie not duplicate value) for example ```customerName``` may not be approperate to be used as the primary key for the ```Customers``` table as tehre could be two custemrs with the same name
* The primary key shall always have a value. In other words it sahll not contain NULL

Consider the following when chooseing tyhe fpimary key

* The primary key shall be simple and familiar. e.g. ```employeeID``` for ```employees``` table and ```isbn``` for ```books``` table
* the value of the primary key should not change. Primary key is used to reference other tables. if you change ites value, you have to change all its reference: ootherswise the rueferences will be lost. For example, ```phoneNumber``` may not be appropriate to be use as primary key for table ```Customers``` because it might change
* Primary key often uses integher( or nuimbe)) type But it could also be other types, such as texts, Hwoever, ti is best to use numeric column as primary key for efficiency
* Primary key could take an arbitrary number. Most RDBMSs (Rleational dabase management system) uspport so called auto-increment( or AutoNumber) for integer primary key, where (current maximum value+1 is ) is assigned to the new record. This arbitrary number is a fact-less as it contains no factual information. Unlike factural info such a sfphone number, fact-less numbs are ideal for primary keys as they do not change
* Primary key is suseally a single column (e.g. ```customerID``` or ```productCode```) But it could also make up of severl columns. You should use as few columns as possible

Let's illustrate with an example: a table ```customers``` contains columns ```lastname```, ```firstname```, ```phoneNumber```, ```address```, ```city```, ```state```, ```zipcode```,. The candidate sfor primary key are name=(lastname, firstname), phonenumber, address1=(address, city, state), address1 =(address, zipcode). Name may not be unique. Phone number and addresss may change.  Hence it is better tyo creat a factless autoincrement number, sya ```customerID``` as the primary key

### Step 3: Create Relatiopns among Tables

