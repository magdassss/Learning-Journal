## 2.1 Storing and querying data

### Objectives
- Data storage options
- Files systems and RDBS data
- Implementing cloud storage

**1. Data storage options:**
- Filesystems - text data, binary data
- RDBMS (SQL) - local, remote
- Non-relational databases (NoSQL) - Cloud

**2. Unicode**
- UTF 8
- UTF 16
- UTF 32

**3. MIME types**
A MIME type is a label used to identify a type of data. It is used so software can
know how to handle the data. It serves the same purpose on the Internet that
file extensions do on Microsoft Windows.

**4. File encryption**

**5. From files to databases:**
- Files get messy
- A filesystem is not the most efficient structure for querying data
- Databases are a structured way of querying data

**6. Types of cloud storage:**
- Block storage
- File storage
- Object storage

**7. Data model**
- Data models are conceptual ways for describing the data
- They can use SQL, or other languages
- They can also be visual (remember diagrams)

The data model description generally consists of three parts:
- Structure of the data – what does it look like
- Operations on the data – what's available
- Constraints on the data – what's allowed

**8. Commonly used data models:**
- Relational Data Model
- Key-Value Data Model
- Semi-structured Data
- Model (e.g., Json, XML)

**9. Terminology**
- Relations/Tables
- Columns/Attributes/Fields
- Rows/Tuples/Records
- Degree (arity) of a relation = #attributes
- Cardinality of a relation = #tuples
- relation schema name of the table
- database schema the set of schemas in relations of database
- domains - data types

**10. Keys**
- Key = one (or multiple) attributes that uniquely identify a record
- Multiple-attribute Key = multiple attributes that uniquely identify a record
- Foreign keys - Attribute(s) whose value is a key of a record in some other relation

**11. SQL**
- SQL stands for Structured Query Language
- Data Manipulation Language (DML) which allows users to create, modify and
query data
- Data Definition Language (DDL) which is used to define external and
conceptual schemas

❑ Which cloud storage solutions are used by your org?
❑ Which teams use them?
❑ What are the use cases and business requirements?
❑ How is the benefit to the business evidenced?


## 2.2 Schemas and Integration

### Objectives
- Demonstrate familiarity with industry database tools and best
practices for designing and setting up databases
- Explain fundamental SQL concepts, including the impact of
changes in database systems on diverse data consumers.
- Demonstrate the application of schemas, metadata, and data
modeling to ensure data reliability and sustainability, and to
mitigate data risks.
- Evaluate user and business needs to ensure the accuracy,
completeness, consistency, timeliness, and accessibility of
upstream data for downstream consumers, taking proactive
responsibility to solve issues.

**1. OLAP & OLTP**

*OLAP - Online Analytical Processing Software*
- analytical
- slow queries
- denormalised
- historical data
  
*OLTP - Online Transaction Processing*
- transactional
- fast processing
- normalised
- current data

**2. Star and  Snowflake schema**

*Star schema* - A database structure in which a central fact table is surrounded by dimension tables, resembling a star. The fact table
contains measurable quantities and foreign keys from dimension tables that describe the data's context.
Widely used in data warehousing for fast data retrieval in Business Intelligence applications due to less join complexity.
Star schemas typically offer faster query performance for large datasets due to fewer joins.

*Snowflake schema* - An extension of the star schema where dimension tables are normalized into multiple related tables, resulting in a more complex database structure that resembles a snowflake with branches radiating from a central node.
Suitable for environments where data integrity and detailed dimensional analysis are crucial.
Snowflake schemas provide higher data integrity through normalization, which can simplify maintenance and reduce errors.

**3. Normalised vs denormalised data**

*Normalised:*
- data integrity
- no or little redundant data
- many tables
- otpimised data storage

*Denormalised*
- data integrity is not maintained
- redundant data is common
- fewer tables

**4. Metadata repositories/catalogs**
- metadata catalog example - AWS Glue

**5. Datamarts**
- A focused database designed to facilitate specific, department-level data analysis and reporting.
Unlike data warehouses, which store comprehensive datasets, datamarts contain only relevant data.
 *star schema* - Smaller, more focused than entire data warehouses; designed to improve response
time and data relevance for specific business units.
*snowflake schema* - Typically segregated by department, function, or subject, enhancing performance and enduser productivity

**6. Apache Iceberg** 
- An open table format for huge analytic datasets, which allows for efficient schema evolution without downtime or performance penalties.
- A streaming service uses Apache Iceberg to manage user data across multiple regions, seamlessly adapting schemas as new data types and
sources are introduced.

**7. Basic Structure of SQL Queries:**
- The fundamental structure of a SQL query includesa SELECT clause to specify the columns, a FROM clause to designate the tables, and
an optional WHERE clause to filter records.

**8. Focus on open-source vs proprietary**

*Open Software*(Linux Ubuntu, OpenOffice.org Write,GIMP)
- Purchased with its source code
- User can get open software for free Of charge
- Users can modify the software
- Users can install software freely into any computer
- No one is responsible to the software
- Full support from vendor if anything happened to the software

*Proprietary Software* (Windows Vista. Microsoft Word 2007.Adobe Photoshop CS3)
- Purchased without its source code
- User must pay to get the proprietary software
- Users Cannot modify the software
- User must have a license from vendor before install into computer
- Full support from vendor if anything happened to the software

## 2.3. Advanced SQL

### Objectives
- Apply standard industry tools and best practices for designing, maintaining and optimising the performance of databases, data lakes, warehouses
- Explain the JOIN concept in SQL and its usefulness.
- Evaluate how views, nested queries and aggregation can fulfill advanced business and user requirements for data engineering.

**1. Types of SQL JOIN**

*EQUI JOIN* 
- EQUI JOIN is a simple SQL join.
- Uses the equal sign(=) as the comparison operator for the condition

*NON EQUI JOIN*
- uses comparison operator other than the equal sign.
- The operators uses like >, <, >=, <= with the condition.

**2. Types of SQL EQUI JOIN**
- INNER JOIN
- LEFT JOIN or LEFT OUTER JOIN
- RIGHT JOIN or RIGHT OUTER JOIN
- CROSS JOIN - The SQL CROSS JOIN produces a result set which is the number of rows in the first table multiplied by the number of rows in the second table, if no WHERE clause is used along with CROSS JOIN.
- UNION - is used to combine the result-set of two or more SELECT statements.
- SUBQUERY - can be simply defined as a query within another query. In other words we can say that a Subquery is a query that is embedded in WHERE clause of another SQL query.

**3. Aggregation** 
- SQL supports several aggregation operations: SUM, COUNT, MIN, MAX, AVG
- COUNT applies to duplicates, unless otherwise stated
- grouping and aggregation
- Group-by v.s. Nested Query

**4. Creating Tables**

**5. Deleting or Modifying a Table**

**6. Indexes**
- REALLY important for speeding up query processing time

**7. Defining Views**
- Views are relations, except that they are not physically stored.
- A Different View
- Types of Views (virtual views, materialized vies)
- updating views
- non-updatable views



  










