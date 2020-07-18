# Read: Relational Databases

- [Data Models (Review the DB Schema)](https://docs.microsoft.com/en-us/aspnet/core/data/ef-mvc/complex-data-model?view=aspnetcore-2.0)
- [DBMS](https://www.tutorialspoint.com/dbms/dbms_overview.htm)
- [Definitions of Keys](https://www.guru99.com/dbms-keys.html#:~:text=Summary&text=Seven%20Types%20of%20DBMS%20keys,identifies%20rows%20in%20a%20table.&text=Primary%20Key%20never%20accept%20null%20values%20while%20a,may%20accept%20multiple%20null%20values.)

---

- What is a Schema?
    - Why do we use them?
        - Defines the layout of our databases
        - Each table will have it's own schema defining each column and datatype
    - What do they look like?
``` C#
using System;
using System.Collections.Generic;
using System.ComponentModel.DataAnnotations;
using System.ComponentModel.DataAnnotations.Schema;

namespace ContosoUniversity.Models
{
    public class Student
    {
        public int ID { get; set; }
        [StringLength(50)]
        public string LastName { get; set; }
        [StringLength(50)]
        [Column("FirstName")]
        public string FirstMidName { get; set; }
        [DataType(DataType.Date)]
        [DisplayFormat(DataFormatString = "{0:yyyy-MM-dd}", ApplyFormatInEditMode = true)]
        public DateTime EnrollmentDate { get; set; }

        public ICollection<Enrollment> Enrollments { get; set; }
    }
}
```
- What are the different types of Database Keys?
    - What is a Primary Key?
        - The column in a table that uniquely identify every row in the table.
        - They cannot be a duplicate. 
        - A table cannot have more than 1 primary key.
    - What is a Foreign Key?
        - A column that creates a relationship between 2 tables.
        - The goal is to maintain data integrity and allow navigation between 2 different instances of an entity.
        - Acts as a cross-reference between 2 tables.
            - it references the primary key of another table. 
    - What is a Composite Key?
        - A combination of 2 or mor columns that uniquely id rows in a table
            - The combination of columns guarantees uniqueness.
    - How are they different? When do you use 1 over the others?
    
Primary Key |	Foreign Key
--- | ---
Helps you to uniquely identify a record in the table. |	It is a field in the table that is the primary key of another table.
Primary Key never accept null values. |	A foreign key may accept multiple null values.
Primary key is a clustered index and data in the DBMS table are physically organized in the sequence of the clustered index. |	A foreign key cannot automatically create an index, clustered or non-clustered. However, you can manually create an index on the foreign key.
You can have the single Primary key in a table. |	You can have multiple foreign keys in a table.
- What are Relationships in a relational database?
    - What is a 1:1 relationship?
        - Each record in 1 table relates to only 1 record on another table
    - What is a Many:Many relationship?
        - 0+ records of 1 table can relate to 0+ records of another table
    - How about a 1: Many or a Many:1?
        - 1:Many - The record in 1 table can relate to 0+ records in another table. 
        - Many:1 - 0+ records in 1 table will relate to only 1 record in another table


## Customize the Data model
### The DataType attribute
``` C#
Using System.ComponentModel.DataAnnotations;

public class Student
{
    // properties
    // properties
    [DataType(Date)]
    [DisplayFormat(DataFormatString = "{0:yyy-MM-dd}", ApplyFormatInEditMode = true)]
    // properties
}
```
- The `DataType` attribute is used to specify a data type that's more specific that the database intrinsic type. 
    - In the example DataType.Date doesn't specify the format of the date that's displayed. 
### StringLength attribute
``` C#
[StringLength(50)]
public string FirstMidName{get;set}
```
- set the maximum length in the db.
    - won't prevent user from entering whitespace (use Regex for that)

### The Column Attribute
```C#
[Column("FirstName")]
public string FirstMidName{get;set}
```
- defines which column the data will go
### Required Attribute
`[Required]`
- this data is required

### Key Attribute
[Key]
### Column Attribute
[Column]

## DBMS
- A Database is a collection of related data and data is a collection of facts and figures that can be processed to produce information.
- A Database management system stores data in such a way that it becomes easier to retrieve, manipulate, and produce information.