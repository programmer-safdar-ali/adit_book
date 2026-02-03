# Chapter 4: Database Management Systems

## Introduction

Database Management Systems (DBMS) are critical components of modern IT infrastructure. As an Assistant Director IT, understanding database concepts, design principles, and administration is essential for managing organizational data effectively. This chapter covers relational database concepts, SQL queries, normalization, administration, and various DBMS platforms.

## Relational Database Concepts

### ACID Properties

ACID properties ensure reliable database transactions:

#### Atomicity
- **Definition**: All operations in a transaction are treated as a single unit
- **Principle**: Either all operations succeed or all fail
- **Example**: In a bank transfer, both debit and credit must succeed or both must fail
- **Implementation**: Transaction logs and rollback mechanisms

#### Consistency
- **Definition**: Database remains in a consistent state before and after transactions
- **Principle**: All data must comply with existing rules (constraints, triggers, cascades)
- **Example**: Foreign key constraints ensure referential integrity
- **Implementation**: Constraints, triggers, and validation rules

#### Isolation
- **Definition**: Concurrent transactions don't interfere with each other
- **Levels**:
  - Read Uncommitted: Lowest isolation, allows dirty reads
  - Read Committed: Prevents dirty reads
  - Repeatable Read: Prevents dirty and non-repeatable reads
  - Serializable: Highest isolation, prevents phantom reads
- **Trade-off**: Higher isolation reduces concurrency

#### Durability
- **Definition**: Once committed, changes persist even after system failures
- **Implementation**: Write-ahead logging (WAL) and transaction logs
- **Guarantee**: Committed transactions survive crashes and power failures

### Transactions and Concurrency Control

#### Transactions
- **Definition**: Sequence of operations treated as a single logical unit
- **States**: Active, Partially Committed, Failed, Aborted, Committed
- **Control**: BEGIN TRANSACTION, COMMIT, ROLLBACK

#### Concurrency Control
- **Purpose**: Allow multiple transactions to execute simultaneously
- **Problems**:
  - Lost Updates: Two transactions update same data
  - Dirty Reads: Reading uncommitted data
  - Non-repeatable Reads: Data changes between reads
  - Phantom Reads: New rows appear between reads
- **Solutions**: Locking, Timestamp Ordering, Optimistic Concurrency Control

### Entity-Relationship (ER) Diagrams

#### Components
- **Entities**: Objects or concepts with independent existence
- **Attributes**: Properties of entities
- **Relationships**: Associations between entities
- **Keys**: Unique identifiers (Primary, Foreign, Candidate)

#### ER Diagram Symbols
- **Rectangles**: Entities
- **Diamonds**: Relationships
- **Ovals**: Attributes
- **Lines**: Connections between entities and relationships
- **Cardinality**: One-to-one (1:1), One-to-many (1:M), Many-to-many (M:N)

#### Design Process
1. Identify entities and attributes
2. Determine relationships between entities
3. Define cardinality and participation constraints
4. Normalize to eliminate redundancy
5. Convert to relational schema

### Functional Dependencies

#### Definition
- Relationship between attributes in a relation
- If A → B, knowing A determines B uniquely

#### Types
- **Trivial**: X → Y where Y ⊆ X
- **Non-trivial**: X → Y where Y ⊈ X
- **Complete**: X → Y where Y contains all attributes

#### Armstrong's Axioms
- **Reflexivity**: If Y ⊆ X, then X → Y
- **Augmentation**: If X → Y, then XZ → YZ
- **Transitivity**: If X → Y and Y → Z, then X → Z

## SQL Queries

### SELECT, INSERT, UPDATE, DELETE Statements

#### SELECT Statement
```sql
-- Basic syntax
SELECT column1, column2, ...
FROM table_name
WHERE condition
ORDER BY column(s);

-- Examples
SELECT * FROM employees;
SELECT first_name, last_name FROM employees WHERE department = 'IT';
SELECT DISTINCT city FROM customers;
```

#### INSERT Statement
```sql
-- Insert single row
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);

-- Insert multiple rows
INSERT INTO table_name (column1, column2, ...)
VALUES 
  (value1, value2, ...),
  (value1, value2, ...);

-- Insert from another table
INSERT INTO table_name (column1, column2, ...)
SELECT column1, column2, ...
FROM another_table
WHERE condition;
```

#### UPDATE Statement
```sql
-- Update specific rows
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

-- Example
UPDATE employees
SET salary = salary * 1.1
WHERE department = 'Sales';
```

#### DELETE Statement
```sql
-- Delete specific rows
DELETE FROM table_name
WHERE condition;

-- Delete all rows
DELETE FROM table_name;

-- Example
DELETE FROM orders
WHERE order_date < '2020-01-01';
```

### JOIN Operations

#### INNER JOIN
- **Purpose**: Returns rows with matching values in both tables
```sql
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id;
```

#### LEFT JOIN (LEFT OUTER JOIN)
- **Purpose**: Returns all rows from left table, matched rows from right table
```sql
SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.id;
```

#### RIGHT JOIN (RIGHT OUTER JOIN)
- **Purpose**: Returns all rows from right table, matched rows from left table
```sql
SELECT e.name, d.department_name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.id;
```

#### FULL OUTER JOIN
- **Purpose**: Returns all rows from both tables
```sql
SELECT e.name, d.department_name
FROM employees e
FULL OUTER JOIN departments d ON e.dept_id = d.id;
```

#### CROSS JOIN
- **Purpose**: Returns Cartesian product of both tables
```sql
SELECT e.name, d.department_name
FROM employees e
CROSS JOIN departments d;
```

#### SELF JOIN
- **Purpose**: Join a table with itself
```sql
SELECT e1.name AS employee, e2.name AS manager
FROM employees e1
JOIN employees e2 ON e1.manager_id = e2.id;
```

### Subqueries and Nested Queries

#### Scalar Subqueries
- Return a single value
```sql
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

#### Row Subqueries
- Return a single row
```sql
SELECT name, department
FROM employees
WHERE (department, salary) = (
  SELECT department, MAX(salary)
  FROM employees
  GROUP BY department
  ORDER BY MAX(salary) DESC
  LIMIT 1
);
```

#### Table Subqueries
- Return multiple rows and columns
```sql
SELECT name, department
FROM employees
WHERE department IN (
  SELECT department
  FROM departments
  WHERE budget > 100000
);
```

#### Correlated Subqueries
- Reference columns from outer query
```sql
SELECT e1.name, e1.salary
FROM employees e1
WHERE e1.salary > (
  SELECT AVG(e2.salary)
  FROM employees e2
  WHERE e2.department = e1.department
);
```

### Aggregate Functions

#### COUNT
- Count rows in a result set
```sql
SELECT COUNT(*) FROM employees;
SELECT COUNT(DISTINCT department) FROM employees;
```

#### SUM
- Calculate sum of numeric values
```sql
SELECT SUM(salary) FROM employees;
SELECT department, SUM(salary) FROM employees GROUP BY department;
```

#### AVG
- Calculate average of numeric values
```sql
SELECT AVG(salary) FROM employees;
SELECT department, AVG(salary) FROM employees GROUP BY department;
```

#### MIN and MAX
- Find minimum and maximum values
```sql
SELECT MIN(salary), MAX(salary) FROM employees;
SELECT department, MIN(salary), MAX(salary) 
FROM employees 
GROUP BY department;
```

### GROUP BY and HAVING Clauses

#### GROUP BY
- Groups rows with same values in specified columns
```sql
SELECT department, COUNT(*), AVG(salary)
FROM employees
GROUP BY department;
```

#### HAVING
- Filters groups created by GROUP BY
```sql
SELECT department, COUNT(*), AVG(salary)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5 AND AVG(salary) > 50000;
```

#### Difference Between WHERE and HAVING
- WHERE filters individual rows before grouping
- HAVING filters groups after grouping

### Window Functions and CTEs

#### Window Functions
- Perform calculations across a set of rows related to current row
```sql
-- ROW_NUMBER(): Sequential numbering
SELECT name, salary,
       ROW_NUMBER() OVER (ORDER BY salary DESC) AS rank
FROM employees;

-- RANK(): Similar to ROW_NUMBER but with ties
SELECT name, salary,
       RANK() OVER (ORDER BY salary DESC) AS rank
FROM employees;

-- LAG/LEAD: Access previous/next rows
SELECT name, salary,
       LAG(salary) OVER (ORDER BY hire_date) AS prev_salary
FROM employees;
```

#### Common Table Expressions (CTEs)
- Temporary named result sets
```sql
WITH high_earners AS (
  SELECT name, salary, department
  FROM employees
  WHERE salary > 75000
)
SELECT department, AVG(salary)
FROM high_earners
GROUP BY department;
```

#### Recursive CTEs
- Reference themselves to handle hierarchical data
```sql
WITH RECURSIVE employee_hierarchy AS (
  -- Base case: Top-level managers
  SELECT employee_id, name, manager_id, 1 as level
  FROM employees
  WHERE manager_id IS NULL
  
  UNION ALL
  
  -- Recursive case: Subordinates
  SELECT e.employee_id, e.name, e.manager_id, eh.level + 1
  FROM employees e
  JOIN employee_hierarchy eh ON e.manager_id = eh.employee_id
)
SELECT * FROM employee_hierarchy;
```

## Database Normalization

### 1NF, 2NF, 3NF, BCNF, 4NF, 5NF

#### First Normal Form (1NF)
- **Requirement**: Eliminate repeating groups
- **Rules**:
  - Each cell contains atomic (indivisible) values
  - Each record is unique
  - Each column has a unique name
- **Example**:
  - Before: Skills column with "Java,Python,C++"
  - After: Separate rows for each skill

#### Second Normal Form (2NF)
- **Requirement**: Meet 1NF + eliminate partial dependencies
- **Rules**:
  - Must be in 1NF
  - All non-key attributes must be fully functionally dependent on the entire primary key
- **Problem**: Partial dependencies in composite primary keys
- **Solution**: Decompose into separate tables

#### Third Normal Form (3NF)
- **Requirement**: Meet 2NF + eliminate transitive dependencies
- **Rules**:
  - Must be in 2NF
  - No non-key attribute is transitively dependent on the primary key
- **Transitive Dependency**: If A → B and B → C, then A → C (transitive)
- **Solution**: Move transitive dependencies to separate tables

#### Boyce-Codd Normal Form (BCNF)
- **Requirement**: Meet 3NF + every determinant is a candidate key
- **Rules**:
  - Must be in 3NF
  - For every functional dependency X → Y, X must be a superkey
- **Improvement**: Addresses anomalies not resolved by 3NF

#### Fourth Normal Form (4NF)
- **Requirement**: Meet BCNF + eliminate multi-valued dependencies
- **Multi-valued Dependency**: When two independent attributes depend on the same key
- **Example**: Employee → Skills and Employee → Languages (independent)

#### Fifth Normal Form (5NF)
- **Requirement**: Meet 4NF + eliminate join dependencies
- **Join Dependency**: When a table can be decomposed into multiple tables and rejoined without loss

### Denormalization Concepts and When to Use

#### Denormalization Definition
- Intentionally introducing redundancy to improve performance
- Opposite of normalization

#### When to Denormalize
- **Read-heavy applications**: More queries than updates
- **Reporting systems**: Data warehouses and analytics
- **Performance requirements**: When normalized structure causes performance issues
- **Simplified queries**: Reduce complex joins

#### Denormalization Techniques
- **Pre-joining**: Store joined data in single table
- **Spreading**: Duplicate data across related tables
- **Lookup tables**: Store computed values
- **Aggregate tables**: Pre-calculated summaries

#### Trade-offs
- **Pros**: Faster queries, simpler application logic
- **Cons**: Data inconsistency risk, increased storage, complex updates

## Database Administration

### User Management: Roles, Privileges, GRANT/REVOKE

#### Database Users
- **Authentication**: Verify user identity
- **Authorization**: Determine what user can do
- **User Types**:
  - Application users: For applications connecting to DB
  - Service accounts: For automated processes
  - Administrative users: For DBA tasks

#### Roles
- **Definition**: Named collections of privileges
- **Benefits**: Simplified privilege management
- **Types**:
  - Predefined roles: Provided by DBMS (e.g., db_datareader)
  - Custom roles: Created by administrators

#### Privileges
- **Object-level**: Specific to tables, views, procedures
- **System-level**: Database-wide operations
- **Common privileges**:
  - SELECT, INSERT, UPDATE, DELETE
  - CREATE, ALTER, DROP
  - CONNECT, RESOURCE

#### GRANT Statement
```sql
-- Grant privileges to users/roles
GRANT SELECT, INSERT ON employees TO hr_user;
GRANT ALL PRIVILEGES ON sales_data TO sales_team;
GRANT SELECT ON employees TO public;  -- All users
```

#### REVOKE Statement
```sql
-- Revoke previously granted privileges
REVOKE INSERT ON employees FROM hr_user;
REVOKE SELECT ON confidential_data FROM junior_staff;
```

### Backup Strategies: Full, Differential, Incremental

#### Full Backup
- **Definition**: Complete copy of all database data
- **Advantages**: Complete recovery possible, simple restore process
- **Disadvantages**: Large storage requirements, longer backup time
- **Frequency**: Typically performed weekly or monthly

#### Differential Backup
- **Definition**: Changes since last full backup
- **Advantages**: Faster than full backup, smaller than incremental
- **Disadvantages**: Size grows over time, requires full backup for restore
- **Frequency**: Performed daily between full backups

#### Incremental Backup
- **Definition**: Changes since last backup (full, differential, or incremental)
- **Advantages**: Fastest backup, smallest storage requirements
- **Disadvantages**: Complex restore process, requires all incremental backups
- **Frequency**: Performed frequently (hourly or daily)

#### Backup Strategy Considerations
- **RTO (Recovery Time Objective)**: Maximum acceptable downtime
- **RPO (Recovery Point Objective)**: Maximum acceptable data loss
- **Storage costs**: Balance between protection and cost
- **Automation**: Schedule and monitor backups

### Point-in-Time Recovery

#### Definition
- Restore database to specific moment in time
- Combines full backup with transaction logs

#### Process
1. Restore last full backup
2. Restore differential backup (if applicable)
3. Apply transaction logs up to desired point in time

#### Benefits
- Granular recovery capability
- Minimize data loss
- Flexibility in recovery options

#### Implementation
- Continuous transaction logging
- Regular log backups
- Proper backup scheduling

### Performance Tuning and Query Optimization

#### Query Optimization Techniques
- **Indexing**: Create appropriate indexes
- **Query rewriting**: Optimize SQL statements
- **Statistics**: Keep statistics updated
- **Execution plans**: Analyze query execution

#### Index Types
- **Clustered**: Determines physical order of data
- **Non-clustered**: Separate structure pointing to data
- **Composite**: Multiple columns
- **Unique**: Enforces uniqueness

#### Performance Monitoring
- **Query execution time**: Identify slow queries
- **Resource utilization**: CPU, memory, disk I/O
- **Lock waits**: Identify blocking issues
- **Buffer hit ratio**: Measure cache efficiency

### Index Types: Clustered, Non-Clustered, Composite

#### Clustered Index
- **Definition**: Determines physical storage order of table data
- **Limitation**: Only one per table
- **Benefits**: Fast range queries, sorting
- **Considerations**: Updates to indexed columns require data movement

#### Non-Clustered Index
- **Definition**: Separate structure containing index key and row locator
- **Limitation**: Multiple per table (database-dependent)
- **Benefits**: Multiple access paths, faster lookups
- **Considerations**: Additional storage, maintenance overhead

#### Composite Index
- **Definition**: Index on multiple columns
- **Benefits**: Covers queries with multiple conditions
- **Considerations**: Column order matters, follows leftmost prefix rule

### Stored Procedures, Triggers, and Views

#### Stored Procedures
- **Definition**: Precompiled collection of SQL statements
- **Benefits**:
  - Improved performance (precompiled)
  - Code reusability
  - Security (controlled access)
  - Reduced network traffic
- **Example**:
```sql
CREATE PROCEDURE GetEmployeeByDepartment
  @dept_name VARCHAR(50)
AS
BEGIN
  SELECT * FROM employees 
  WHERE department = @dept_name;
END
```

#### Triggers
- **Definition**: Special stored procedures that execute automatically
- **Types**:
  - DML triggers: Execute on INSERT, UPDATE, DELETE
  - DDL triggers: Execute on CREATE, ALTER, DROP
  - Logon triggers: Execute on login
- **Use Cases**: Audit trails, data validation, referential integrity

#### Views
- **Definition**: Virtual tables based on query results
- **Benefits**:
  - Simplified queries
  - Security (restrict access to specific columns)
  - Data abstraction
- **Types**:
  - Regular views: Query-based
  - Indexed views: Materialized (SQL Server)
  - Partitioned views: Union of multiple tables

### Database Replication and Sharding

#### Database Replication
- **Definition**: Copying data from one database to another
- **Purposes**: High availability, load distribution, disaster recovery
- **Types**:
  - Master-slave: One master, multiple read-only slaves
  - Master-master: Multiple masters accepting writes
  - Multi-source: Slave receives from multiple masters

#### Replication Methods
- **Statement-based**: Replicate SQL statements
- **Row-based**: Replicate changed rows
- **Mixed**: Combination of both

#### Sharding
- **Definition**: Horizontal partitioning of data across multiple databases
- **Strategies**:
  - Range-based: Partition by value ranges
  - Hash-based: Partition by hash of key
  - Directory-based: Use lookup table for partitioning
- **Benefits**: Scalability, performance
- **Challenges**: Cross-shard queries, consistency

## DBMS Platforms

### MySQL, PostgreSQL, Oracle, MS SQL Server

#### MySQL
- **Type**: Open-source relational database
- **Strengths**: Speed, ease of use, large community
- **Use Cases**: Web applications, small to medium businesses
- **Features**: ACID compliance, replication, partitioning

#### PostgreSQL
- **Type**: Open-source object-relational database
- **Strengths**: Advanced features, extensibility, standards compliance
- **Use Cases**: Complex applications, data warehousing
- **Features**: JSON support, advanced indexing, custom data types

#### Oracle
- **Type**: Enterprise commercial database
- **Strengths**: Performance, scalability, advanced features
- **Use Cases**: Large enterprises, mission-critical applications
- **Features**: Partitioning, clustering, advanced security

#### MS SQL Server
- **Type**: Microsoft commercial database
- **Strengths**: Integration with Microsoft ecosystem, tools
- **Use Cases**: Windows environments, enterprise applications
- **Features**: Business Intelligence tools, integration services

### MongoDB (NoSQL)

#### Document Database
- **Structure**: Stores documents in BSON format
- **Schema**: Flexible, no predefined schema
- **Benefits**: Agile development, horizontal scaling

#### MongoDB Features
- **Collections**: Groups of documents (equivalent to tables)
- **Documents**: Individual records (equivalent to rows)
- **Aggregation Pipeline**: Complex data processing
- **Replica Sets**: High availability and failover
- **Sharding**: Horizontal scaling

#### Use Cases
- Content management
- Real-time analytics
- Mobile applications
- IoT applications

## Advanced Concepts

### Data Warehousing: Star Schema, Snowflake Schema

#### Data Warehouse Characteristics
- **Subject-oriented**: Focused on specific business areas
- **Integrated**: Consolidated from multiple sources
- **Time-variant**: Historical data maintained
- **Non-volatile**: Data doesn't change once loaded

#### Star Schema
- **Structure**: Fact table surrounded by dimension tables
- **Characteristics**: Denormalized dimension tables
- **Benefits**: Simple queries, good performance
- **Components**:
  - Fact table: Contains measures and foreign keys
  - Dimension tables: Contain descriptive attributes

#### Snowflake Schema
- **Structure**: Normalized version of star schema
- **Characteristics**: Dimension tables further normalized
- **Benefits**: Reduced redundancy, normalized structure
- **Trade-offs**: More complex queries, more joins

### OLTP vs OLAP

#### OLTP (Online Transaction Processing)
- **Purpose**: Handle day-to-day transactions
- **Characteristics**:
  - Short, simple transactions
  - High volume of concurrent users
  - Normalized database design
  - Emphasis on data integrity
- **Examples**: Banking systems, retail POS, inventory management

#### OLAP (Online Analytical Processing)
- **Purpose**: Support complex analytical queries
- **Characteristics**:
  - Complex, long-running queries
  - Fewer concurrent users
  - Denormalized database design
  - Emphasis on query performance
- **Examples**: Business intelligence, data mining, reporting

### Materialized Views

#### Definition
- Physical storage of query results
- Refreshed periodically or on demand

#### Benefits
- Improved query performance
- Pre-computed aggregations
- Reduced load on base tables

#### Considerations
- Storage overhead
- Maintenance overhead
- Data freshness

## Summary

This chapter covered essential database management concepts, from fundamental relational database principles to advanced administration and design. Understanding these concepts is crucial for managing organizational data effectively. The next chapter will focus on data structures and algorithms.

## Key Takeaways

1. ACID properties ensure reliable database transactions
2. SQL provides comprehensive data manipulation and querying capabilities
3. Normalization eliminates redundancy and improves data integrity
4. Proper backup strategies are essential for data protection
5. Performance tuning requires understanding of indexing and query optimization
6. Different DBMS platforms offer various features for different use cases
7. Data warehousing concepts support analytical processing needs
8. OLTP and OLAP serve different business purposes

## Practice Questions

1. What are the four ACID properties and why are they important?
2. Explain the difference between 2NF and 3NF in database normalization.
3. What is the difference between a clustered and non-clustered index?
4. Name three types of database backup strategies.
5. What is the difference between OLTP and OLAP systems?

## Answers

1. Atomicity (all-or-nothing), Consistency (valid state), Isolation (concurrent transactions don't interfere), Durability (committed changes persist). These ensure reliable database transactions.
2. 2NF eliminates partial dependencies (non-key attributes depending on part of composite key), while 3NF eliminates transitive dependencies (non-key attributes depending on other non-key attributes).
3. A clustered index determines the physical storage order of table data (one per table), while a non-clustered index is a separate structure containing index key and row locator (multiple per table).
4. Full backup (complete copy), Differential backup (changes since last full backup), and Incremental backup (changes since last backup of any type).
5. OLTP handles day-to-day transactions with short, simple queries and emphasis on data integrity, while OLAP supports complex analytical queries with emphasis on query performance and historical data.