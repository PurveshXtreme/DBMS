# Database Management System (DBMS) Study Guide

## Table of Contents
- [Database Management System (DBMS)? What are its types, advantages, and applications?](#database-management-system-dbms-what-are-its-types-advantages-and-applications)
- [What are the problems with traditional file-based systems?](#what-are-the-problems-with-traditional-file-based-systems)
- [What is the difference between DBMS and RDBMS?](#what-is-the-difference-between-dbms-and-rdbms)
- [What is the difference between File System and DBMS?](#what-is-the-difference-between-file-system-and-dbms)
- [What are the different types of DBMS architecture?](#what-are-the-different-types-of-dbms-architecture)
- [Relations, tables, rows, columns, and keys in DBMS? Also, what are the primary components of a DBMS?](#relations-tables-rows-columns-and-keys-in-dbms-also-what-are-the-primary-components-of-a-dbms)
- [Entity-Relationship (ER) Model](#entity-relationship-er-model)
- [Data Redundancy, Referential Integrity, and DBMS Role](#data-redundancy-referential-integrity-and-dbms-role)
- [Normalization](#normalization)
- [Schema, Constraints, and Keys](#schema-constraints-and-keys)
- [Joins in SQL](#joins-in-sql)
- [SQL Queries and Operations](#sql-queries-and-operations)
- [Transactions and ACID](#transactions-and-acid)
- [Views](#views)  
- [Stored Procedures and Functions](#stored-procedures-and-functions)  
- [Triggers](#triggers)  
- [Indexing](#indexing)
- [Concurrency Control and Deadlocks](#concurrency-control-and-deadlocks) 
- [B-trees and B+ trees](#b-trees-and-b+-trees)  
- [Hashing](#hashing)  
- [Database Locks](#database-locks)  
- [Cursors](#cursors)  
- [Materialized Views](#materialized-views)  
- [Data Partitioning](#data-partitioning)  
- [Backup and Recovery](#backup-and-recovery)  
- [Database Administration](#database-administration)



---

## Database Management System (DBMS)? What are its types, advantages, and applications?

A **Database Management System (DBMS)** is software used to efficiently manage and organize databases. It provides an interface for storing, retrieving, updating, and managing data while ensuring **data integrity**, **security**, and **concurrency control**. Examples include **MySQL**, **PostgreSQL**, **Oracle**, and **SQL Server**.

### Types of DBMS:
1. **Hierarchical DBMS** – Organizes data in a tree-like structure with parent-child relationships.  
   *Example:* IBM IMS  
2. **Network DBMS** – Represents data as a graph with many-to-many relationships.  
   *Example:* Integrated Data Store (IDS)  
3. **Relational DBMS (RDBMS)** – Stores data in tables (relations) and manages it using SQL.  
   *Example:* MySQL, PostgreSQL  
4. **Object-Oriented DBMS** – Stores data as objects, similar to object-oriented programming.  
   *Example:* ObjectDB  

### Advantages of DBMS:
- **Data Integrity:** Maintains accuracy and consistency of data.  
- **Data Security:** Provides controlled access via user permissions.  
- **Efficient Retrieval:** Uses indexing and query optimization for faster results.  
- **Reduced Redundancy:** Minimizes duplicate data through normalization.  
- **Backup & Recovery:** Supports automatic backup and restoration.  
- **Concurrent Access:** Enables multiple users to work simultaneously without conflicts.  

### Applications of DBMS:
- **Banking:** Account management, transaction processing.  
- **E-commerce:** Product catalogs, order tracking, customer data.  
- **Healthcare:** Patient records, diagnosis history.  
- **Education:** Student grades, schedules, course management.  
- **Social Media:** User profiles, interactions, content storage.  
- **Data Science:** Storing and processing large datasets for analytics and predictions.  

**Illustration:**  
![Database Applications](https://media.geeksforgeeks.org/wp-content/uploads/20250729183922080793/Database-Applications.webp)

---

## What are the problems with traditional file-based systems?

Before the introduction of modern DBMS, data was stored and managed using basic file systems on hard drives. Although these systems allowed storing, retrieving, and updating files, they had several drawbacks:

- **Data Redundancy:** Duplicate entries often existed across multiple files.  
- **Data Inconsistency:** Conflicting or outdated information could occur due to redundant storage.  
- **Difficult Data Access:** Manual searching was time-consuming and inefficient.  
- **Poor Security:** No built-in access control to restrict unauthorized access.  
- **Single-User Limitation:** No support for multi-user collaboration.  
- **No Backup & Recovery:** Data loss was often permanent without recovery mechanisms.  

---

## What is the difference between DBMS and RDBMS?

- **DBMS (Database Management System):**  
  A software system that enables users to create, store, modify, and delete data. It does **not** require a relational structure for organizing data.  
  *Examples:* Microsoft Access, XML databases.

- **RDBMS (Relational Database Management System):**  
  A type of DBMS that stores data in structured **tables (relations)** and supports relational operations like **joins**. It enforces **data integrity** using primary keys and foreign keys, and supports SQL for querying.  
  *Examples:* MySQL, Oracle, SQL Server.

---

## What is the difference between File System and DBMS?

| Aspect                | File System | DBMS |
|-----------------------|-------------|------|
| **Data Storage**      | Stores data in separate files without structured relationships. | Stores data in a structured format (tables, objects) with relationships. |
| **Data Redundancy**   | High redundancy due to duplicate records in multiple files. | Redundancy minimized through normalization. |
| **Data Consistency**  | Inconsistencies common due to lack of centralized control. | Maintains consistency via integrity constraints. |
| **Data Access**       | Manual searching; slow for large datasets. | Uses query languages (e.g., SQL) for efficient retrieval. |
| **Security**          | Limited or no built-in access control. | Role-based permissions and authentication mechanisms. |
| **Multi-user Support**| Typically single-user; difficult for concurrent access. | Supports concurrent multi-user operations with concurrency control. |
| **Backup & Recovery** | No automatic backup/recovery; data loss may be permanent. | Provides built-in backup and recovery mechanisms. |
| **Data Integrity**    | No enforcement of data validation rules. | Enforces integrity via constraints (primary key, foreign key, etc.). |

---

## What are the different types of DBMS architecture?

A **DBMS architecture** defines how users interact with the database for reading, writing, and updating data. A well-designed architecture ensures **data consistency**, **performance**, and **security**.  
The main types are:

### 1. 1-Tier Architecture
The client, server, and database are all on the same system. Suitable for personal or standalone applications.  
*Example:* Microsoft Excel.

**Advantages:**
- Simple and cost-effective
- Easy to implement

**Disadvantages:**
- Single-user limitation
- Poor security
- No centralized control

**Illustration:**  
![DBMS 1-Tier Architecture](https://media.geeksforgeeks.org/wp-content/uploads/20230509110722/DBMS-1-Tier-Architecture.webp)

### 2. 2-Tier Architecture
A client-server model where the application (client) communicates directly with the database server.  
*Example:* Library Management System.

**Advantages:**
- Easy access and deployment
- Scalable and low cost

**Disadvantages:**
- Limited scalability with many users
- Security risks due to direct database access
- Tight coupling between client and database

**Illustration:**  
![DBMS 2-Tier Architecture](https://media.geeksforgeeks.org/wp-content/uploads/20250108093805302915/2_tier.webp)

### 3. 3-Tier Architecture
Adds an **application server** between the client and database. The client interacts with the application server, which communicates with the database. Common in large web applications.  
*Example:* E-commerce websites.

**Advantages:**
- Enhanced scalability and security
- Better data integrity

**Disadvantages:**
- More complex and costly
- Slower response time due to extra layer

**Illustration:**  
![DBMS 3-Tier Architecture](https://media.geeksforgeeks.org/wp-content/uploads/20250108093901256398/3_tier.webp)

---

## Relations, tables, rows, columns, and keys in DBMS? Also, what are the primary components of a DBMS?

### Relation in DBMS
A **relation** is essentially a table consisting of rows and columns.  
- **Rows** represent individual records (tuples).  
- **Columns** represent attributes or properties of the entity.  
Relations are defined by a **schema**, which specifies the table's attributes.

### Table in DBMS
A **table** is the primary structure for storing data in a relational database.  
- Each **row** represents one entity (record).  
- Each **column** represents one attribute of that entity.

### Rows and Columns
- **Rows (Tuples):** Each row holds the values for all attributes of a single entity.  
- **Columns (Attributes):** Each column represents a property of the entity and has a defined data type.

### Primary Components of a DBMS
1. **Database Engine:** Manages data storage, retrieval, and updates.  
2. **Database Schema:** Defines the database structure and relationships.  
3. **Query Processor:** Interprets and executes SQL queries.  
4. **Transaction Manager:** Maintains ACID properties for transactions.  
5. **Storage Manager:** Manages the physical storage of data.

### Primary Key
A **Primary Key** uniquely identifies each record in a table.  
- It must be **unique** and **not NULL**.  
- Example: In a `STUDENT` table, `ROLL_NO` can be the primary key.

**Example:**
| ROLL_NO | NAME   | ADDRESS |
|---------|--------|---------|
| 1       | Ram    | Delhi   |
| 2       | Suresh | Delhi   |

### Foreign Key
A **Foreign Key** is an attribute in one table that references the **primary key** in another table, ensuring **referential integrity**.

**Example:**

**STUDENT Table**
| ROLL_NO | NAME   | BRANCH_CODE |
|---------|--------|-------------|
| 1       | Ram    | CS          |
| 2       | Suresh | IT          |

**BRANCH Table**
| BRANCH_CODE | BRANCH_NAME          |
|-------------|----------------------|
| CS          | Computer Science     |
| IT          | Information Technology |

Here, `BRANCH_CODE` in `STUDENT` is a foreign key referencing `BRANCH_CODE` in `BRANCH`.

### Candidate Key
A **Candidate Key** is a set of one or more attributes that can uniquely identify a tuple in a relation.  
- A relation can have **multiple candidate keys**.  
- One of these is selected as the **primary key**.
###Superkey:
A set of one or more attributes that can uniquely identify a row in a table. It may contain unnecessary attributes.

---

## Entity-Relationship (ER) Model

The **ER Model** is a conceptual framework for database design.  
It visually represents entities, their attributes, and the relationships between them through **Entity-Relationship Diagrams (ERDs)**.

### Components of ER Diagram
![Components of ER Diagram](https://media.geeksforgeeks.org/wp-content/uploads/20230428090323/Introduction-to-ER-Model-1.webp)

- **Entity**: Real-world object/concept stored as data (e.g., Student, Course).
- **Attribute**: Properties describing an entity (e.g., StudentID, CourseName).
- **Relationship**: Association between entities (e.g., Student enrolls in Course).

### Why Use ER Diagrams
- Easy conversion into relational tables.
- Models real-world objects in a clear way.
- Requires no technical DBMS knowledge to understand.
- Simplifies complex systems into visual form.

### Symbols in ER Model
![Symbols used in ER Diagram](https://media.geeksforgeeks.org/wp-content/uploads/20230428115454/Introduction-to-ER-Model-2-768.webp)

- **Rectangle**: Entity
- **Ellipse**: Attribute
- **Diamond**: Relationship
- **Line**: Connects entities/attributes
- **Double Ellipse**: Multivalued attribute
- **Double Rectangle**: Weak entity

### Entities

#### What is an Entity?
- Real-world object/concept about which data is stored.
- **Entity Type**: Structure definition (e.g., Student table).
- **Entity Instance**: A single occurrence (row in table).

#### Entity Set
- Collection of all entities of a specific type.

### Types of Entities
![Strong Entity and Weak Entity](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210219121849/12310.png)

1. **Strong Entity**
   - Has its own unique key attribute.
   - Does not depend on another entity.
   - Represented by **rectangle**.

2. **Weak Entity**
   - Cannot be uniquely identified without a related strong entity.
   - Depends on an identifying relationship with a strong entity.
   - Represented by **double rectangle**.

### Attributes
![Entity and Attributes](https://media.geeksforgeeks.org/wp-content/uploads/20250517122835356955/studn-dbms.png)

- **Key Attribute**: Uniquely identifies each entity (underlined oval).
- **Composite Attribute**: Composed of multiple sub-attributes.
- **Multivalued Attribute**: Can store multiple values for an entity (double oval).
- **Derived Attribute**: Calculated from other attributes (dashed oval).

### Degree of Relationship (Number of entity sets in relationship)
1. **Unary** – 1 entity set involved.
2. **Binary** – 2 entity sets involved.
3. **Ternary** – 3 entity sets involved.
4. **N-ary** – n entity sets involved.

### Cardinality in ER Model
Defines maximum number of relationships per entity.

#### 1. One-to-One
![One to One Cardinality](https://media.geeksforgeeks.org/wp-content/uploads/20230920133529/onetoone.jpg)  
![Set Representation of One-to-One](https://media.geeksforgeeks.org/wp-content/uploads/20220131223352/121.jpg)

- Each entity relates to only one entity in the other set.

#### 2. One-to-Many
![One to Many Cardinality](https://media.geeksforgeeks.org/wp-content/uploads/20230920133617/onetomany.jpg)  
![Set Representation of One-to-Many](https://media.geeksforgeeks.org/wp-content/uploads/20230428115353/12n.webp)

- One entity can relate to multiple entities in the other set.

#### 3. Many-to-One
![Many to One Cardinality](https://media.geeksforgeeks.org/wp-content/uploads/20230920133703/manytoone.jpg)  
![Set Representation of Many-to-One](https://media.geeksforgeeks.org/wp-content/uploads/20220131232355/m21.jpg)

- Multiple entities relate to one entity in the other set.

#### 4. Many-to-Many
![Many to Many Cardinality](https://media.geeksforgeeks.org/wp-content/uploads/20230920133746/manytomany.jpg)  
![Many-to-Many Set Representation](https://media.geeksforgeeks.org/wp-content/uploads/20220208105038/manytomantrelationship.jpg)

- Entities from both sets can have multiple relationships with each other.

### 48. Differences between an ER Diagram and a Relational Schema

| Feature                | Entity-Relationship Diagram (ERD)                                                                 | Relational Schema                                                                                  |
|------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| **Definition**         | A conceptual blueprint that models entities, relationships, and attributes of the database.       | A logical schema that defines the structure of a relational database (tables, columns, constraints). |
| **Purpose**            | Used during the **database design phase** to understand how data entities relate to each other.   | Represents **how data is physically organized** in tables and columns.                            |
| **Representation**     | Graphical form showing **entities, attributes, and relationships**.                               | Tabular form showing **tables, columns, keys, and data types**.                                   |
| **Focus**              | Focuses on **conceptual design** — "what" data will be stored and how it relates.                  | Focuses on **implementation details** — "how" data will be stored in the DBMS.                    |
| **Constraints**        | Shows relationships and cardinalities between entities.                                            | Defines **primary keys, foreign keys, and other constraints**.                                    |

---

## Data Redundancy, Referential Integrity, and DBMS Role

### **Data Redundancy**
**Definition:**  
Data redundancy refers to the **unnecessary repetition of data** in a database.  
It can cause:
- **Inconsistencies** in data
- **Increased storage requirements**
- **Maintenance challenges**

**Reduction Methods:**
1. **Normalization** – Splitting large tables into smaller ones to eliminate redundancy.
2. **Eliminating Duplicate Data** – Using constraints like `UNIQUE` and `PRIMARY KEY` to enforce data consistency.

---

### **Referential Integrity**
**Definition:**  
Referential integrity ensures that **relationships between tables are maintained correctly**.  
It requires that:
- A **foreign key** in one table must match a **primary key** or **unique key** in another table, **or be NULL**.
- Prevents **orphan records** (records referencing non-existent entries).

**Example:**
```sql
-- Ensuring CustomerID in Orders table is valid
ALTER TABLE Orders
ADD CONSTRAINT FK_Customer
FOREIGN KEY (CustomerID)
REFERENCES Customers(CustomerID);
```

---

### **Role of DBMS in Data Integrity and Security**
1. **Data Integrity:**
   - Enforced using constraints like **Primary Key**, **Foreign Key**, and **Check** constraints.
   - Ensures **accuracy** and **consistency** of data.

2. **Data Security:**
   - **User Authentication** – Validates users before access.
   - **Access Control** – Grants or restricts permissions to data.
   - **Encryption** – Protects data from unauthorized viewing.
   - **Role-Based Access Control (RBAC)** – Allows only authorized users to perform specific actions.

---


---

## Normalization

### What is Normalization? Why is it Important in DBMS?

**Definition:**  
Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity.  
It involves splitting large tables into smaller, related tables and defining relationships between them.

**Importance of Normalization:**
- Eliminates redundant data.
- Prevents anomalies during insert, update, and delete operations.
- Improves data integrity and consistency.

### What is Denormalization? How Does it Differ from Normalization?

**Definition:**  
Denormalization is the process of combining tables to improve query performance, often at the cost of introducing redundancy.  

**Difference:**

| Aspect         | Normalization                           | Denormalization                           |
|----------------|----------------------------------------|--------------------------------------------|
| Goal           | Minimize redundancy, improve integrity | Improve performance for read-heavy tasks  |
| Data Redundancy| Reduced                                | Increased                                 |
| Use Case       | Transactional systems                  | Analytical / reporting systems            |

### Normal Forms in DBMS

Normal Forms help structure data logically, reduce redundancy, and maintain integrity. Each normal form builds upon the previous.

### Why is Normalization Important?
- **Reduces Data Redundancy:** Saves storage space and prevents inconsistencies.
- **Improves Data Integrity:** Ensures accuracy and consistency.
- **Simplifies Database Design:** Easier to maintain and update.
- **Optimizes Performance:** Reduces anomalies and boosts operational efficiency.

## Q: What is a Candidate Key in DBMS?
A **Candidate Key** is a **minimal set of one or more attributes** that can **uniquely identify a tuple** in a relation.  
- **Minimal** means if you remove any attribute from it, it will no longer be able to uniquely identify tuples.  
- A table can have multiple candidate keys, and one of them is chosen as the **Primary Key**.

**Example:**  
In a `STUDENT` table with `(RollNo, Email, Phone)`, both `RollNo` and `Email` can uniquely identify a student — hence they are **candidate keys**.

---

## Q: What is a Prime Attribute in DBMS?
A **Prime Attribute** is any attribute that is **part of at least one candidate key**.  
- If an attribute is not part of any candidate key, it’s called a **Non-Prime Attribute**.

**Example:**  
For `STUDENT(RollNo, Email, Name)`:
- **Candidate keys:** `{RollNo}`, `{Email}`
- **Prime attributes:** `RollNo`, `Email`
- **Non-prime attribute:** `Name`

---

### Quick Comparison Table

| Term              | Definition | Example (STUDENT: RollNo, Email, Name) |
|-------------------|------------|----------------------------------------|
| **Candidate Key** | Minimal set of attributes that uniquely identify a tuple | `{RollNo}`, `{Email}` |
| **Primary Key**   | One chosen candidate key to uniquely identify tuples | `{RollNo}` |
| **Alternate Key** | Candidate keys other than the primary key | `{Email}` |
| **Prime Attribute** | Attribute part of at least one candidate key | `RollNo`, `Email` |
| **Non-Prime Attribute** | Attribute not part of any candidate key | `Name` |


### Types of Normal Forms

#### 1. First Normal Form (1NF) – Eliminating Duplicate Records
- Columns contain **atomic values**.
- No repeating groups or arrays.
- Each row is unique.

**Example Violation:**  
A single cell storing multiple phone numbers → split into separate rows.

#### 2. Second Normal Form (2NF) – Eliminating Partial Dependency
- Must be in **1NF**.
- No partial dependency (non-key attributes depend on **entire** primary key).
- In 2NF, every non-prime attribute must be fully functionally dependent on the whole of every candidate key — it must not depend on just a part of any composite candidate key.

**Example Violation:**  
For `(StudentID, CourseID)` as key, `StudentName` depends only on `StudentID` → move `StudentName` to separate table.

#### 3. Third Normal Form (3NF) – Eliminating Transitive Dependency
A relation is in **3NF** if:

1. It is already in **2NF**.
2. **No transitive dependency** exists — i.e., a **non-prime attribute** must **not** depend on another **non-prime attribute**.
3. **Equivalently:** For every functional dependency `X → Y` in the table, at least one of these must be true:
   - **X** is a **superkey** (meaning it can uniquely identify a row), **or**
   - **Y** is a **prime attribute** (part of some candidate key).


**Example Violation:**  
If `Instructor` depends on `CourseID`, which depends on `StudentID` → move `Instructor` to table linked by `CourseID`.

#### 4. Boyce–Codd Normal Form (BCNF) – Strongest 3NF
- Must be in **3NF**.
- For every dependency `X → Y`, **X must be a superkey**.

**Example Violation:**  
If `(StudentID, CourseID) → Instructor` but neither `StudentID` nor `CourseID` is a superkey → decompose the table.

![BCNF](https://media.geeksforgeeks.org/wp-content/uploads/20250108151038174913/bcnf.webp)

#### 5. Fourth Normal Form (4NF) – Removing Multi-Valued Dependencies
- Must be in **BCNF**.
- No multi-valued dependencies.

**Example Violation:**  
If `(StudentID, Language, Hobby)` exists with independent languages & hobbies → split into separate `Language` and `Hobby` tables.

#### 6. Fifth Normal Form (5NF) – Eliminating Join Dependency
- Must be in **4NF**.
- All join dependencies removed without losing information.

### Advantages of Normalization
1. Reduces redundancy.
2. Improves consistency.
3. Simplifies design.
4. Improves query performance.
5. Easier maintenance.
6. Facilitates scalability.
7. Better data modeling.
8. Prevents update anomalies.
9. Improves security & integrity.
10. Optimizes storage usage.

### Challenges of Over-Normalization
- Complex queries with many joins.
- Possible performance overhead in large systems.

**When to Use:**
- **Normalization:** Transaction-heavy systems (e.g., banking).
- **Denormalization:** Read-heavy systems (e.g., data warehousing).

### Normal Forms Summary Table

| Normal Form | Rule / Condition | Purpose |
|-------------|------------------|---------|
| **1NF (First Normal Form)** | No repeating groups or arrays; each cell contains atomic (indivisible) values. | Remove duplicate columns and ensure atomicity. |
| **2NF (Second Normal Form)** | Must be in 1NF **and** all non-key attributes must be fully dependent on the primary key (no partial dependency). | Remove partial dependency in composite keys. |
| **3NF (Third Normal Form)** | Must be in 2NF **and** no transitive dependency (non-key attributes should not depend on other non-key attributes). | Remove transitive dependencies. |
| **BCNF (Boyce-Codd Normal Form)** | Must be in 3NF **and** every determinant must be a candidate key. | Handle anomalies not covered by 3NF. |
| **4NF (Fourth Normal Form)** | Must be in BCNF **and** no multi-valued dependencies. | Eliminate multi-valued dependency issues. |
| **5NF (Fifth Normal Form)** | Must be in 4NF **and** no join dependency (table should not be decomposable without loss of data). | Ensure lossless decomposition. |

---

# Normal Forms Examples with Conflicts & Resolutions

---

## **1NF (First Normal Form)**
**Rule:**  
- Only **atomic values** (no repeating groups or multi-valued attributes)  
- No composite attributes  
- No duplicate rows  

**Conflicting Table (Not in 1NF):**
| StudentID | Name     | Phone Numbers         |
|-----------|----------|-----------------------|
| 1         | Alice    | 12345, 67890           |
| 2         | Bob      | 55555                  |

**Issue:**  
`Phone Numbers` column contains multiple values (multi-valued attribute).

**Resolved Table (1NF):**
| StudentID | Name     | Phone Number |
|-----------|----------|--------------|
| 1         | Alice    | 12345        |
| 1         | Alice    | 67890        |
| 2         | Bob      | 55555        |

---

## **2NF (Second Normal Form)**
**Rule:**  
- Must be in **1NF**  
- **No partial dependency** (No non-prime attribute should depend on part of a composite key)

**Conflicting Table (1NF but not 2NF):**
| StudentID | CourseID | StudentName | CourseName |
|-----------|----------|-------------|------------|
| 1         | C1       | Alice       | DBMS       |
| 1         | C2       | Alice       | OS         |

**Issue:**  
- Candidate key = `(StudentID, CourseID)`  
- `StudentName` depends **only** on `StudentID`  
- `CourseName` depends **only** on `CourseID` → **Partial dependency**

**Resolved Tables (2NF):**
**Student Table:**
| StudentID | StudentName |
|-----------|-------------|
| 1         | Alice       |

**Course Table:**
| CourseID  | CourseName  |
|-----------|-------------|
| C1        | DBMS        |
| C2        | OS          |

**Enrollment Table:**
| StudentID | CourseID |
|-----------|----------|
| 1         | C1       |
| 1         | C2       |

---

## **3NF (Third Normal Form)**
**Rule:**  
- Must be in **2NF**  
- No **transitive dependency** (No non-prime attribute depends on another non-prime attribute)

**Conflicting Table (2NF but not 3NF):**
| StudentID | StudentName | DeptID | DeptName  |
|-----------|-------------|--------|-----------|
| 1         | Alice       | D1     | Computer  |
| 2         | Bob         | D2     | Physics   |

**Issue:**  
- Candidate key = `StudentID`  
- `DeptName` depends on `DeptID` (which is a non-prime attribute) → **Transitive dependency**

**Resolved Tables (3NF):**
**Student Table:**
| StudentID | StudentName | DeptID |
|-----------|-------------|--------|
| 1         | Alice       | D1     |
| 2         | Bob         | D2     |

**Department Table:**
| DeptID | DeptName  |
|--------|-----------|
| D1     | Computer  |
| D2     | Physics   |

---

## **4NF (Fourth Normal Form)**
**Rule:**  
- Must be in **Boyce–Codd Normal Form (BCNF)**  
- No **multi-valued dependencies** (MVDs) unless trivial  

**Conflicting Table (3NF/BCNF but not 4NF):**
| StudentID | Hobby       | Language |
|-----------|-------------|----------|
| 1         | Chess       | English  |
| 1         | Chess       | French   |
| 1         | Painting    | English  |
| 1         | Painting    | French   |

**Issue:**  
- `Hobby` and `Language` are **independent multi-valued facts** about `StudentID`  
- This leads to redundant combinations

**Resolved Tables (4NF):**
**StudentHobby Table:**
| StudentID | Hobby     |
|-----------|-----------|
| 1         | Chess     |
| 1         | Painting  |

**StudentLanguage Table:**
| StudentID | Language  |
|-----------|-----------|
| 1         | English   |
| 1         | French    |


----

## Schema, Constraints, and Keys

**Schema in DBMS:**  
A **schema** defines the **organization and structure** of data in a database.  
It includes:
- **Tables** and their columns
- **Views**
- **Relationships**
- **Constraints** and keys

It serves as the **blueprint** for how the database is constructed, specifying **data types, keys, and relationships**.

---

**Constraints in DBMS:**  
Constraints are **rules** applied to table data to maintain **data integrity** and **consistency**.  

| Constraint     | Description                                                                                          | Example |
|----------------|------------------------------------------------------------------------------------------------------|---------|
| **NOT NULL**   | Ensures a column cannot have NULL values.                                                            | `Name VARCHAR(50) NOT NULL;` |
| **PRIMARY KEY**| Uniquely identifies each record; no NULLs allowed.                                                   | `ID INT PRIMARY KEY;` |
| **FOREIGN KEY**| Ensures referential integrity by linking a column to a primary key in another table.                 | `BranchCode INT FOREIGN KEY REFERENCES Branch(BranchCode);` |
| **UNIQUE**     | Ensures all values in a column are distinct; allows NULL values.                                     | `Email VARCHAR(100) UNIQUE;` |
| **CHECK**      | Ensures column values meet a specific condition.                                                     | `Age INT CHECK (Age >= 18);` |
| **DEFAULT**    | Assigns a default value if none is provided during insertion.                                        | `Status VARCHAR(10) DEFAULT 'Active';` |

---

**Primary Key vs. Unique Key:**

| Feature           | Primary Key                                                                                 | Unique Key                                                                             |
|-------------------|----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| **Purpose**       | Uniquely identifies each record in a table.                                                  | Ensures all values in a column/set of columns are unique.                              |
| **NULL Values**   | Cannot contain NULL values.                                                                  | Can contain NULL values (but only one NULL in most DBMS).                              |
| **Count per Table**| Only **one** primary key is allowed.                                                         | Multiple unique keys can exist in the same table.                                      |
| **Uniqueness**    | Guarantees uniqueness for the **entire table**.                                               | Guarantees uniqueness for the specific column(s) it is applied to.                     |

---

## Joins in SQL

**Definition:**  
A **JOIN** in SQL is an operation that combines columns from two or more tables based on a **related column** between them.  
It is used to query and retrieve data from multiple tables in a relational database.

---

### Types of Joins

1. **INNER JOIN**  
   Returns only the rows where there is a match in both tables.  

   **Example:**
   ```sql
   SELECT * 
   FROM Student
   INNER JOIN Course 
       ON Student.ID = Course.StudentID;
   ```

2. **LEFT JOIN (LEFT OUTER JOIN)**  
   Returns all rows from the **left** table and matching rows from the right table.  
   If no match exists, NULL values are returned for columns from the right table.

   **Example:**
   ```sql
   SELECT * 
   FROM Student
   LEFT JOIN Course 
       ON Student.ID = Course.StudentID;
   ```

3. **RIGHT JOIN (RIGHT OUTER JOIN)**  
   Returns all rows from the **right** table and matching rows from the left table.  
   If no match exists, NULL values are returned for columns from the left table.

   **Example:**
   ```sql
   SELECT * 
   FROM Student
   RIGHT JOIN Course 
       ON Student.ID = Course.StudentID;
   ```

4. **FULL JOIN (FULL OUTER JOIN)**  
   Returns all rows when there is a match in **either** left or right table.  
   If no match exists, NULL values are returned for columns of the table without a match.

   **Example:**
   ```sql
   SELECT * 
   FROM Student
   FULL JOIN Course 
       ON Student.ID = Course.StudentID;
   ```

5. **CROSS JOIN**  
   Returns the **Cartesian product** of two tables — every combination of rows from both tables.

   **Example:**
   ```sql
   SELECT * 
   FROM Student
   CROSS JOIN Course;
   ```

6. **SELF JOIN**  
   Joins a table with itself, useful for comparing rows in the same table.  
   Uses table aliases to differentiate instances.

   **Example:**
   ```sql
   SELECT E1.Employee_ID, E1.Employee_Name, E2.Employee_Name AS Manager_Name
   FROM Employee E1
   LEFT JOIN Employee E2 
       ON E1.Manager_ID = E2.Employee_ID;
   ```

---

### INNER JOIN vs OUTER JOIN

| Aspect        | INNER JOIN                                                | OUTER JOIN                                                                 |
|---------------|-----------------------------------------------------------|------------------------------------------------------------------------------|
| **Result Set**| Only matching rows from both tables.                       | All rows from one or both tables, with NULL where no match is found.         |
| **Types**     | Single type.                                               | Three types: **LEFT**, **RIGHT**, **FULL**.                                  |
| **Use Case**  | When you only need intersecting data.                      | When you want to preserve all data, even with mismatches.                    |
| **Performance**| Generally faster (fewer rows).                            | Can be slower (handles more rows and NULLs).                                 |
| **Reliability**| Reliable for matched data.                                | Reliable for full data retention, but may introduce NULL-related complexities.|

---
---

## SQL Queries and Operations

## What is the use of the SQL SELECT statement?

The **SELECT** statement is used to query data from one or more tables. It allows you to retrieve specific columns or all columns, optionally applying filters (WHERE), sorting (ORDER BY), and joining multiple tables.

**Example:**
```sql
SELECT NAME, AGE FROM STUDENT WHERE AGE > 18;
```

## What is the difference between DELETE and TRUNCATE in SQL?

**DELETE:** Deletes specific rows from a table based on a condition. It logs each row deletion and can be rolled back.

**TRUNCATE:** Removes all rows from a table without logging individual row deletions. It cannot be rolled back and is faster than DELETE.

## What is a subquery in SQL? Provide an example.

A subquery in SQL is a query embedded within another query. It is used to retrieve data that will be used in the outer query. Subqueries can be used in SELECT, INSERT, UPDATE, or DELETE statements.

There are two types of subqueries:
- **Single-row subquery:** Returns a single value.
- **Multiple-row subquery:** Returns multiple values.

**Example of a subquery:** To find the names of students who have a higher age than the average age:
```sql
SELECT Name FROM Student
WHERE Age > (SELECT AVG(Age) FROM Student);
```

## What are aggregate functions in SQL? Name a few examples.

Aggregate functions in SQL are functions that operate on a set of values (or a group of rows) and return a single result. They are often used in conjunction with the GROUP BY clause. Here are a few commonly used aggregate functions in SQL:

1. **COUNT():** Returns the number of rows or non-NULL values in a column
   ```sql
   SELECT COUNT(*) FROM Student;
   ```

2. **SUM():** Returns the sum of values in a numeric column.
   ```sql
   SELECT SUM(Amount) FROM Orders;
   ```

3. **AVG():** Returns the average value of a numeric column.
   ```sql
   SELECT AVG(Salary) FROM Employees;
   ```

4. **MAX():** Returns the maximum value in a column
   ```sql
   SELECT MAX(Age) FROM Student;
   ```

5. **MIN():** Returns the minimum value in a column.
   ```sql
   SELECT MIN(Salary) FROM Employees;
   ```

## What is the difference between UNION and UNION ALL in SQL?

**UNION:** Combines the result of two queries and removes duplicate rows.

**UNION ALL:** Combines the result of two queries but does not remove duplicates, thus it is faster than UNION.

**Example:**
```sql
SELECT Name FROM Students
UNION
SELECT Name FROM Teachers;  -- Removes duplicates

SELECT Name FROM Students
UNION ALL
SELECT Name FROM Teachers;  -- Does not remove duplicates
```

## What is the purpose of the GROUP BY clause in SQL?

The GROUP BY clause is used in SQL to group rows that have the same values in specified columns into summary rows, often with aggregate functions like COUNT, SUM, AVG, MIN, or MAX. It is typically used to organize data for reporting or analysis.

**Example:** This groups the employees by department and counts the number of employees in each department.
```sql
SELECT Department, COUNT(*) FROM Employees
GROUP BY Department;
```


---
---

## Transactions and ACID

## What is a transaction in DBMS? What are the properties of a transaction?

A **transaction** in DBMS is a sequence of one or more SQL operations executed as a single unit of work. A transaction ensures data integrity, consistency, and isolation, and it guarantees that the database reaches a valid state, regardless of errors or system failures.

**Properties of a transaction (ACID Properties):**
* **Atomicity:** All operations within the transaction are completed successfully, or none are applied (i.e., the transaction is atomic).
* **Consistency:** The transaction brings the database from one valid state to another valid state.
* **Isolation:** The operations of one transaction are isolated from others; intermediate results are not visible to other transactions.
* **Durability:** Once a transaction is committed, its effects are permanent, even in the event of a system crash.

## What is the ACID Property in DBMS?

In **Database Management Systems (DBMS)**, the **ACID** property is a set of principles that ensure reliable, consistent, and safe transaction processing. Each letter in ACID represents a fundamental property:

1. **Atomicity**  
   - Definition: A transaction is treated as a single, indivisible unit of work.  
   - Meaning: Either **all operations** in a transaction succeed, or **none do**.  
   - Example: If a bank transfer involves debiting one account and crediting another, both operations must succeed together. If one fails, the entire transaction is rolled back.

2. **Consistency**  
   - Definition: Ensures that a transaction takes the database from one valid state to another valid state.  
   - Meaning: All database rules, constraints, and relationships are maintained after the transaction.  
   - Example: If a table enforces a constraint that account balances cannot be negative, any transaction violating this is rejected.

3. **Isolation**  
   - Definition: Transactions are executed in isolation from each other.  
   - Meaning: The intermediate state of a transaction is **invisible to other transactions** until it is committed.  
   - Example: Two users updating the same record simultaneously will not interfere with each other; each sees a consistent snapshot of the database.

4. **Durability**  
   - Definition: Once a transaction is committed, its results are permanent.  
   - Meaning: Changes are saved even in the event of a system crash, power failure, or hardware issue.  
   - Example: After successfully transferring money, the debit and credit changes remain in the database even if the server fails immediately afterward.

## What is the Importance of COMMIT and ROLLBACK Operations?

In **DBMS**, **COMMIT** and **ROLLBACK** are essential operations that manage transaction control and ensure the **ACID** properties of a database.

1. **COMMIT**  
   - Definition: Permanently saves all changes made during the current transaction to the database.  
   - Importance: Ensures that the changes are **durable** and visible to other transactions.  
   - Example: After transferring funds between accounts, a `COMMIT` ensures the updated balances are permanently recorded.

2. **ROLLBACK**  
   - Definition: Reverses all changes made during the current transaction, restoring the database to its previous state.  
   - Importance: Maintains **atomicity**, allowing the database to remain consistent in case of errors or failures.  
   - Example: If an error occurs while updating multiple tables during a transaction, `ROLLBACK` will undo all partial changes, preventing inconsistent data.

## What is a transaction log in DBMS?

A **transaction log** is a record that keeps track of all transactions executed on a database. It ensures that changes made by transactions are saved, and in case of a system failure, the log can be used to recover the database to its last consistent state. The transaction log contains:
* The details of each transaction (e.g., start, commit, rollback).
* Information about data modifications (insertions, updates, deletions).
* Details about the data before and after the change.

---
---

## Views 

**Q: What is a view in DBMS? How does it differ from a table?**

**A:**  
A **View** is a **virtual table** created by querying one or more base tables. Unlike a regular table, a view:  
- Does not store data physically.  
- Retrieves data dynamically from the underlying base tables when queried.  
- Acts as a saved SQL query that simplifies complex queries and improves security by restricting data access.  

**Difference from a Table:**  
- A **table** physically stores data in rows and columns.  
- A **view** does not store its own data; it only presents data derived from other tables.

---

**Q: What is the use of the "WITH CHECK OPTION" in SQL views?**

**A:**  
The **WITH CHECK OPTION** is used when creating a view to ensure that any `INSERT` or `UPDATE` operation performed through the view must satisfy the conditions defined in the view’s `WHERE` clause.  
- If the data being modified does not meet the view condition, the operation will be rejected.  
- This maintains data integrity and prevents inconsistent data entry.

**Example:**  
```sql
CREATE VIEW ActiveStudents AS
SELECT * FROM Students WHERE Status = 'Active'
WITH CHECK OPTION;
```

---
---

## Stored Procedures and Functions

## Stored Procedures in DBMS

### Q: Explain the concept of a stored procedure in DBMS.

**A:**  
A **stored procedure** is a **precompiled collection of one or more SQL statements** stored in the database. It allows execution of a series of operations as a single unit, improving performance, reusability, and security.  

- Can accept **input parameters**.  
- Can perform multiple operations such as `INSERT`, `UPDATE`, `DELETE`, or `SELECT`.  
- Can return results, but returning a value is optional.  

**Example:**
```sql
CREATE PROCEDURE GetStudentDetails(IN student_id INT)
BEGIN
   SELECT * FROM Student WHERE ID = student_id;
END;
```


## Stored Functions in DBMS

### Q: What are stored functions in DBMS?

**A:**  
A **stored function** is a set of SQL statements stored in the database that performs some logic and **must return a single value**.  

- Accepts **input parameters**.  
- Always returns a value (unlike procedures).  
- Commonly used for calculations, validations, or retrieving specific values.  

**Example:**
```sql
CREATE FUNCTION GetEmployeeSalary(EmployeeID INT)
RETURNS DECIMAL(10,2)
BEGIN
   DECLARE salary DECIMAL(10,2);
   SELECT Salary INTO salary FROM Employee WHERE ID = EmployeeID;
   RETURN salary;
END;
```

---
---

## Triggers

## Triggers in DBMS

### Q: What are triggers in DBMS? How do they differ from stored procedures?

**A:**  
A **trigger** is a special kind of stored procedure that automatically executes (or *fires*) in response to specific events on a table, such as `INSERT`, `UPDATE`, or `DELETE`. They are mainly used to enforce business rules, maintain data consistency, or log changes automatically.

**Example:**
```markdown
CREATE TRIGGER after_student_insert
AFTER INSERT ON Student
FOR EACH ROW
BEGIN
   INSERT INTO AuditLog (Action, StudentID, ActionTime)
   VALUES ('INSERT', NEW.ID, NOW());
END;
```

| Aspect           | Trigger                                                                 | Stored Procedure                                                                 |
|------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| **Execution**    | Executes automatically when a specific event (`INSERT`, `UPDATE`, `DELETE`) occurs on a table. | Executed manually by a user or application.                                      |
| **Invocation**   | Cannot be invoked explicitly; tied to table events.                     | Must be invoked explicitly using `CALL` or from an application.                  |
| **Return Value** | Does not return values directly.                                        | Can return values and output parameters.                                         |
| **Use Case**     | Enforcing business rules, maintaining consistency, logging changes.     | Performing complex logic, batch processing, calculations, or repeated operations.|

---
---

## Indexing

## Indexing in DBMS

### Q: What is an index in DBMS, how is indexing used, and what is the difference between clustered and non-clustered indexes?

**A:**  
An **index** in DBMS is a data structure that improves the speed of data retrieval operations on a database table. It works like a **table of contents** in a book, allowing the database to quickly locate the position of a record based on a column value.  

**Indexing** is the technique of creating indexes to speed up the retrieval of records from a table. Instead of scanning the entire table, the DBMS uses the index for a quick lookup, leading to better performance.

---

### Types of Indexes
- **Single-column index:** Created on one column.  
- **Composite index:** Created on multiple columns.  
- **Unique index:** Ensures that no two rows have the same values in the indexed columns.  

---

### Difference between Clustered and Non-Clustered Indexes

| Aspect                  | Clustered Index                                                                 | Non-Clustered Index                                                        |
|-------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------|
| **Data Storage**        | Organizes and stores the actual table rows according to the index key.           | Creates a separate structure with pointers to the data rows in the table.  |
| **Number per Table**    | Only one clustered index is allowed per table.                                   | Multiple non-clustered indexes can exist on the same table.                |
| **Access Speed**        | Faster for range queries due to physical ordering of data.                       | Slower compared to clustered for large scans, but useful for lookups.      |
| **Sorting**             | Determines the physical order of data in the table.                              | Does not affect the physical order of the data in the table.               |

---
---

## Concurrency Control and Deadlocks

## Concurrency Control and Deadlocks in DBMS

### Q: What is a deadlock in DBMS, how can it be prevented, and how does DBMS handle concurrency control?

**A:**  

A **deadlock** occurs when two or more transactions are blocked because each transaction is waiting for the other to release resources. This creates a cycle where none of the transactions can proceed.  

---

### Deadlock Prevention Techniques
- **Lock ordering:** Ensure that all transactions acquire locks in the same predefined order.  
- **Timeouts:** Automatically roll back transactions that have been waiting too long for resources.  
- **Deadlock detection:** Periodically check for deadlocks and abort one of the transactions to break the cycle.  

---

### Concurrency Control in DBMS
Concurrency control ensures that multiple transactions can execute simultaneously **without causing conflicts or inconsistencies** in the database.  

**Techniques used for concurrency control:**
- **Locking:**  
  Transactions acquire locks to control access to data.  
  - *Shared lock (S-lock):* Allows multiple transactions to read the same data but not modify it.  
  - *Exclusive lock (X-lock):* Allows only one transaction to modify the data.  

- **Timestamp Ordering:**  
  Each transaction is assigned a unique timestamp, and operations are executed in timestamp order to maintain consistency.  

- **Optimistic Concurrency Control:**  
  Transactions execute without acquiring locks. Before commit, the system checks for conflicts and aborts the transaction if any conflict is found.  

- **Two-Phase Locking (2PL):**  
  - *Growing phase:* Transaction acquires all required locks.  
  - *Shrinking phase:* Transaction releases locks but cannot acquire new ones.  
  This ensures **serializability** and helps in avoiding deadlocks.  

---
---

