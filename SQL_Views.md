## Building Views

> A view is a virtual table that doesn't contain any data or information. All it contains is the query that the user defines
when creating the view.

- A view is a named query that can be used against or or more tables

- Views are used
as a security measure by restricting users to accessing only certain columns or rows from an underlying table, as a
method of joining data from multiple tables and presenting it as if that data resided in one table, and as a method of
returning summary data instead of detailed data.

- Views can also be used to provide a method of accessing the underlying data in a manner that provides the end
user with a business-ready layout

### Functions

#### System

-  `CAST( )/CONVERT( )`  : Used to convert from one data type to another


The syntax for CAST() is as follows:

`CAST(variable_or_column AS datatype)`

This is different than the syntax for CONVERT(), which is as follows:

`CONVERT(datatype,variable_or_column)`

Not all data types can be converted between each other, such as converting a datetime to a text data type,
and some conversions need neither a CAST() nor a CONVERT(). 

##### Cast Example 
```SQL

DECLARE @Cast int
SET @Cast = 1234
SELECT CAST(@Cast as char(10)) + '-End'

-- Result
1234      -End

```
##### Convert Example 
```SQL

DECLARE @Convert int
SET @Convert = 5678
SELECT CONVERT(char(10),@Convert) + '-End'

-- Result
5678      End

```
