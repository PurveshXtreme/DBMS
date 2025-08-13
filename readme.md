# Database Management System (DBMS) Study Guide

## Table of Contents
- [Database Management System (DBMS)? What are its types, advantages, and applications?](#database-management-system-dbms-what-are-its-types-advantages-and-applications)
- [What are the problems with traditional file-based systems?](#what-are-the-problems-with-traditional-file-based-systems)
- [What is the difference between DBMS and RDBMS?](#what-is-the-difference-between-dbms-and-rdbms)
- [What is the difference between File System and DBMS?](#what-is-the-difference-between-file-system-and-dbms)
- [What are the different types of DBMS architecture?](#what-are-the-different-types-of-dbms-architecture)
- [Relations, tables, rows, columns, and keys in DBMS? Also, what are the primary components of a DBMS?](#relations-tables-rows-columns-and-keys-in-dbms-also-what-are-the-primary-components-of-a-dbms)
- [Entity-Relationship (ER) Model](#entity-relationship-er-model)
- [Normalization](#normalization)

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
