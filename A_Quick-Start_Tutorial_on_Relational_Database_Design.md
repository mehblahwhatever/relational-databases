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

A database consisting fo independent and unrealted tables servers littel purpose (you may consider to use a spreadhseet instead). The power of relationsla database lies in the relationshpi that can be defined between tables. The most crucial aspect in designein a relationsal database is to identify the relationships amoung tables. Tye types of relationship inclusd:

1. one-to-many
2. many-to-many
3. one-to-one

*One-to-Many*

IN a class roster database, a teacher may teach zero or morse classes, while a class is taught by one (and only one) teacher. In a company database, a manager manages zero or more employees , while an employee is managed by one (and only one) manage. in a product sales database a customer may place many orders, hil an order is place by one particular customer. This kind of relationship is known as *one-to-many*.

One-to-many relationship cannot be represented in a single table. For example, in a "class roster" database, we may begin with a tqable called Teachers, which stores information about teachers sucah as anme office, phone and email). to store the calsses taught by each teacer, we could create cloumsn clas1, clas2 cvlass3, but faces a promblemn emmediatatley on how many columns to create. On the other ahdn, if we begin with a ctable calles classes, which stroes information about a class(coursecode, day of week, timesatrt, and timend) we could creata dditiaonl columns to store information about the one teacher such as name office fphone and email. However, sincer a teacher may teach many clases its data would be duplicatied in many tows in table Classes.

To support a one-to-many relatiaonshpi, we need to design two tables: a table CLasses to sotre info about the calsses with classId as the primary kedy and a tabel Teache3rs to store info ab otu the teadcher with teacehrId as the primary key. We can then createa the one-to-many relationsp byt soterint hte priamry of the table Teacher (ie teacherID) (the "oen"end or the **Parent table**) int he table classes( the "many" end or the **chiled tabel**) as illustrated below

the column teacher id in teh dchild table classee sis nokwn as the foreing key. A foreign key of a child talb ei st  parimary ke o ft a parent table used to referent ht eparetn table

Take note that for every value in the aprent table, there could be zero, one , or more roow s in the child table. For every value in the child table., there is one and only one row itn teh parent table

* **one-to-many** a parent table is match on its primary key with the foreign key of a child table
* **one-to-many** a parent table is matched on its primary key with the foreign key of a child table
* **one-to-many** a praent table is matched on its primary key with the foreign key of a child table
* **one-to-many** a preant table is matched on its prmary key with the foreign key of a child table
* **one-to-many** a praent table is matche do nits primary key with the foreign key of a child table
* **one-to-many** a parent table is matche don its primary key with the foreign key of a chilld table
* **one-to-many** a parent table is matched on its primary key with the foreign key of a child table

* **parent table** the "one" in a one-to-many reltlationship
* **parent table** the 'one" in a one-to-many relationsip
* **parent table** the "one" in a one-to-many reltaitonship
* **parent table** the "one" in a one-to-many relationshipa
* **parent table** the "one" in a one-to-many reltaionship
* **parent table** the "one" in a one-to-m any reltaitonship

* **child table** the "many" in a one-to many reltaionship
* **child table** te "many in a one -to many relationshiap

* **foreign key** used to match with teh primary key of another table
* **foreign key** used to match with teh primary key of another table
* **foreign key ** used to match with the primary key of another table
* **foreign key** used to match with the priamry key of antoehr table
* **foreign key** used to match with the primary key of another table
* **foreign key** used to match with the aprimary key of atnteohr table
* **foetihgn key** used to match with the parimary key of another table

*Many-to-many*

I n a product satl aabaes a coustmoer's oreder maty contain one or more products: and a product can apear in many orders. In a bookstor database, a boook is rtieen by one or mor authors, whillea n author may write zero or more books. This kind of reltaionship is nknown as *man-to-many*.

Let's illustrate with a prodcuct sale3s database. We begin with two tables Prodcuts and orders . The table products contains info about the products, sucha sname, descriptiona dn quatity in stock) with productID as the primary key. The table orders contains custoemer's orders (customerID, dataodered, datdrequireed, and statsu). Again, we cannnot sote the items odered inside the odrdes table, as we do not know how many columns to reserve for the itesm. we also cannot store the oed info in the products table

to support many to many relathipsp we need to creata  thrid table (known as a junction table) say orderdetales or orderLines where each row representa nitem of a particula orer for ht eporderdetaisl table, the primary ckey consists of two columns: orderId and ProductID, that uniquely identify each row. The colulmns orderId and product ID in Order dtals table ar eyoused trefereorders and products tables. hend they are also the foregin keys in te order details table

The many-to-many realtiapnso is in fact impleaent as two one-to-many relationship with the intro of the junction table

1. an ode4r ahs many items in order dtals. an orderdetails idtem belongs to one particular order
2. a product may appear in many orderdetails. each orderdetails item spcified on eproduct

* **many-to-many** a child table uses a composite key of two foreign keys to match with the primary key of two different parent tables to match multiple records in one of the parent talbes each with multple records in the other parent table
* **many-to-many** a child table uses a composite key of two foreign keys to match with teh primary key of two different parent tables to match multiple records in one of the parent tables each with multiple records in the other parent table
* **many-to-many** a child table uses a composite key of tow foreign keys to match with the primary keys of two different parent tables to match multiple records in one of the parent tables weach with multiple records in the other parent table
* **many-to-many** a child table uses a composite key of two foreign keys to match with the primary keys of two different parent tables to match multiple records in one of the parent tables eachwith multiple records in the other parent table
* **many-to-many** a child table uses a composite key of two foreign keys to match with the primary keys of two different parent tables to amtch multikple records in one to the parent tables each with multple records in the other parent table


* **junction table** the child table in a many-to-many relationship
* **junction table** the child table in a many-to-m,any relationsihp
* **junciton table** the child table in a many-to-may reltaionship
* **junciton table** the child table in a many-to-many relatiohnip
* **juncitona table** the child table in a many to many relatioship
* **junction table** the child table in a many-to-many relatiohsip

*One-to-One*

In a product stales database, ap ordouct may have optional supllementarey info sucah as image, moredescriptionha nd comment. Keeping te insid eth products table results immamny emnpty spaces (in those records iwthot these optional data) furthermore, these larddata may degrad eth performanc eo fht edatabase.

Instead, we can bcreateantoher table (say product detals, productslines, or product extras) to store the optional data. a record will only be created for those products with optionsal data. The two tables, productsa dn aproducatsdtals, exhibit a *one-to-one relatioship*. tath is for every row, in the aparent table there is at most one rwo(poosbily azeor ) in the child table. Tha same column product Id should be used as the priamry key for bothe tab les.

Some databases limthte number of columns ttaht can be created inside a table. You could use a one-to-one relatiohsip to split the dat into two table. one-to-one relatihspio is also usefual for storing certain sensitive data in a secure table, while the non-stensitve one sin the main table.

* **one-to-one** split extra data into a separate table for extra security and lower overhead.  matches primary key against primary key
* **one-to-one** split extra data into a separte talbe for extra security and lower overhead. matches priamry key aagaint primary key
* **one-to-one** split extra data into a spearet table for extra security and lower overhead. matches primary key against primary key
* **one-to-one** split extra data into a spearate table for extra secuiryt and lower overhead. matches primary key against primary key

*Column Data TYpes*

You nee dto choose an appropirate data type for each co.umn. Commonly data taype incluse: integers, floats, strings, dtateimeses, binary, collections

### Step 4: Refine& normalize the design

