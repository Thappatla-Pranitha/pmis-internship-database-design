# PMIS Internship Database Design

## Overview

This is a DBMS learning project in which I practiced database schema design using a fictional Internship Management System.

The goal was to understand how to identify entities, define columns, establish relationships, and design a structured relational database.

## Concepts Practiced

- Database schema design
- Entity Relationship Diagrams (ERD)
- Database Markup Language (DBML)
- Primary keys and foreign keys
- One-to-many and many-to-many relationships
- Database normalization
- Relational database design

## Database Tables

The schema contains five tables:

1. **interns** — stores intern and educational details.
2. **programs** — stores internship program information.
3. **enrollments** — connects interns with internship programs.
4. **assessments** — stores assessments associated with programs.
5. **assessment_results** — records individual assessment results.

## Entity Relationship Diagram

![Internship Database ERD](screenshots/erd-overview.png)

## Schema Source

The `schema.dbml` file contains the DBML code used to create the ER diagram with [dbdiagram.io](https://dbdiagram.io/).

## Key Learning

I learned how to convert a real-world scenario into database tables, define primary and foreign keys, represent relationships, and reduce unnecessary data duplication through normalization.

## Disclaimer

This is an independent educational exercise using fictional data. It is not an official PMIS implementation and does not represent any organization's internal database.

## Tools Used

- DBML
- dbdiagram.io
- GitHub
- DBMS concepts
