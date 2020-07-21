# Day 11

- Each framework does MVC different. 

## MVC
- Model
    - Business Logic
    - Simple (entities)
    - Complex
    - Data manipulation happens here
- View
    - What the user sees. 
    - View engine
        - rossalin complier (cshtml)
- Controller
    - traffic cop
    - Waiting room

- Business logic
    - data that can be manipulated
    - takes in data manipulates it and returns it
    - Adding properties

- EFcore - Entity Framework
    - talk to ef and ef will talk to the database
        - Works with databases
        - ORM - Object Relational Mapping
            - postgres is a version of ORM

- IISExpress
    - Internet Informational services

- Controller - class
- Action - method
- ID - property

## Databases
1. relational
    - tables can have relationships with each other
    - contain information
    - columns
    - type specific (statically typed)
    - structured data
1. non-relational
    - no relations between datasets
    - No keys between tables
    - document format
    - Big Data
    - CosmosDB - .NET
    - Document DB - .NET
    - 'raw' data

- Key
    1. Primary
        - unique
        - by convention just `ID`
        
    1. foreign
        - The primary key of a foreign key
        - convention
            - foreign table plus id [studentID]
        - can have more than 1 foreign key in a table.
    1. Composite

- Plan you ERD 
    - only have to do it a few times. 
    - each box is a table
    - the whole erd is the DB
    - each property is a column

- payload
    - composite key with additional data

- Relationships
    - 1:Many
    - Many:Many
        - it takes 3 tables to show this
    - 1:1

- Navigation property
    - tells how to consume that data from a table
    - when there is a foreign key always have a nav property on how to get that info.

    payload in a join table: any additional table