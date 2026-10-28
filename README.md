# PMIS Internship Database Design

A hands-on DBMS learning project focused on database schema design, Entity Relationship Diagrams (ERDs), relationships, and normalization using a fictional Internship Management System.

This project explores how to convert a real-world scenario into a structured relational database using DBML and MySQL concepts.

## Table of Contents

- [Introduction](#introduction)
- [Why Is Schema Design Important?](#why-is-schema-design-important)
- [Tools and Concepts](#tools-and-concepts)
- [Steps for Designing a Database](#steps-for-designing-a-database)
- [Step 1 - Identify Tables](#step-1---identify-tables)
- [Step 2 - Define Columns](#step-2---define-columns)
- [Step 3 - Determine Relationships](#step-3---determine-relationships)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Step 4 - Database Normalization](#step-4---database-normalization)
- [Practice Questions](#practice-questions)
- [Key Learnings](#key-learnings)
- [Future Improvements](#future-improvements)

## Introduction

Database schema design is the process of organizing and structuring data so that it can be stored, retrieved, and updated efficiently.

For this learning exercise, I designed a fictional Internship Management System inspired by common internship management workflows.

The system is intended to manage:

- Intern information
- Internship programs
- Intern enrollments
- Program assessments
- Assessment results

The goal is to understand how database tables are identified, how relationships are established, and how normalization helps reduce unnecessary data duplication.

## Why Is Schema Design Important?

A well-designed database schema helps achieve:

- **Data consistency:** Keeps related information accurate.
- **Reduced redundancy:** Avoids storing the same information repeatedly.
- **Data integrity:** Uses constraints and relationships to protect data quality.
- **Maintainability:** Makes the database easier to modify as requirements change.
- **Efficient querying:** Allows related information to be retrieved using SQL joins.

An Entity Relationship Diagram (ERD) provides a visual representation of database tables and their relationships.

## Tools and Concepts

### Tools

- [dbdiagram.io](https://dbdiagram.io/) — creating ER diagrams using DBML.
- MySQL — relational database concepts and SQL implementation.
- GitHub — documenting and publishing the learning project.

### Key Concepts

| Concept | Description |
|---|---|
| Schema Design | Organizing database tables and relationships |
| ERD | Visual representation of entities and relationships |
| DBML | Database Markup Language used to describe schemas |
| Primary Key | Uniquely identifies each record |
| Foreign Key | Connects related tables |
| Normalization | Organizes data to reduce redundancy and update anomalies |
| SQL | Language used to define, query, and modify relational databases |

## Steps for Designing a Database

The database design process follows these steps:

1. Identify the entities that need to be stored.
2. Define the columns and appropriate data types.
3. Determine primary keys, foreign keys, and relationships.
4. Normalize the tables to reduce redundancy.
5. Validate the design using an ERD and sample data.

## Step 1 - Identify Tables

The fictional Internship Management System contains five tables.

| Table | Purpose |
|---|---|
| `interns` | Stores intern and educational details |
| `programs` | Stores internship program information |
| `enrollments` | Connects interns to internship programs |
| `assessments` | Stores assessments associated with programs |
| `assessment_results` | Records individual assessment results |

Separating these entities makes the schema easier to maintain than storing all information in one large table.

## Step 2 - Define Columns

Each table contains columns that describe its entity.

### 1. interns

| Column | Data Type | Purpose |
|---|---|---|
| `intern_id` | INT | Primary key |
| `full_name` | VARCHAR(100) | Intern's name |
| `email` | VARCHAR(150) | Unique email address |
| `college` | VARCHAR(150) | College name |
| `graduation_year` | INT | Year of graduation |

### 2. programs

| Column | Data Type | Purpose |
|---|---|---|
| `program_id` | INT | Primary key |
| `program_name` | VARCHAR(100) | Program name |
| `duration_months` | INT | Program duration |

### 3. enrollments

| Column | Data Type | Purpose |
|---|---|---|
| `enrollment_id` | INT | Primary key |
| `intern_id` | INT | Foreign key referencing interns |
| `program_id` | INT | Foreign key referencing programs |
| `start_date` | DATE | Enrollment start date |
| `status` | VARCHAR(30) | Enrollment status |

### 4. assessments

| Column | Data Type | Purpose |
|---|---|---|
| `assessment_id` | INT | Primary key |
| `program_id` | INT | Foreign key referencing programs |
| `assessment_name` | VARCHAR(100) | Assessment name |
| `max_marks` | DECIMAL(5,2) | Maximum possible marks |

### 5. assessment_results

| Column | Data Type | Purpose |
|---|---|---|
| `result_id` | INT | Primary key |
| `enrollment_id` | INT | Foreign key referencing enrollments |
| `assessment_id` | INT | Foreign key referencing assessments |
| `marks_obtained` | DECIMAL(5,2) | Marks obtained |
| `result_status` | VARCHAR(20) | Result status |

## Step 3 - Determine Relationships

Relationships explain how records in one table connect to records in another table.

The schema uses the following relationships:

1. **Interns to Enrollments — One-to-Many:** One intern can have multiple enrollments over time.
2. **Programs to Enrollments — One-to-Many:** One program can contain many enrollments.
3. **Programs to Assessments — One-to-Many:** One program can contain multiple assessments.
4. **Enrollments to Assessment Results — One-to-Many:** One enrollment can have multiple assessment results.
5. **Assessments to Assessment Results — One-to-Many:** One assessment can have results for multiple enrollments.

The relationship between interns and programs is many-to-many, resolved through the `enrollments`
