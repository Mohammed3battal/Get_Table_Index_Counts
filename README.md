## Script: List_Table_Index_Counts.sql

**Description**:
This script returns the number of indexes (including heap, clustered, and non-clustered) on each user-defined table in the current database. It helps DBAs review indexing coverage and spot over-indexed or under-indexed tables.

**What It Shows**:
- `DatabaseName`: Name of the database where the script is run
- `TableName`: Name of each user table
- `TotalIndexes`: Number of indexes (heap, clustered, non-clustered)

**Index Types Included**:
- `0`: Heap (no clustered index)
- `1`: Clustered index
- `2`: Non-clustered index

**Use Case**:
- Audit index usage per table
- Detect missing or excessive indexing
- Use as a basis for index tuning or documentation

**Requirements**:
- SQL Server 2005 or later
- Must run per database (or wrap in `sp_MSforeachdb` or a cursor to run across all)

**Notes**:
- System tables and internal objects are excluded
- To analyze all databases, wrap this in a cross-database loop
