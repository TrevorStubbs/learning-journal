# Read 14 - Database Normalization
- Database Normalization is a process used to organize a db into tables and columns. 
- a table should be about a specific topic and only supporting topics included.
- limiting a table to one purpose allows for the reduction of the number of duplicate data contained withing a DB.
## Reasons for DB normalization
1. to minimized duplicate data
1. minimized or avoid data modification issues
1. simplify queries.
- a table should do 1 thing
## Data Duplication and Mod anomalies
- 2 problems
    1. Increased storage and decreased performance.
    1. becomes more difficult to maintain data changes
- insert anomalies
    - cannot record until all columns are info is known
- update anomaly
    - multiple updates are needed to be made
- deletion anomaly
    - can cause loose of other data.
## Search and sort issues
## Definition of DB normalization
1. first Normal form- the information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns
1. second normal form - the table is in first normal form and all the columns depend on the table's primary key.
1. third normal form - the table is in second normal form and all of its columns are not transitively dependent on the primary key.