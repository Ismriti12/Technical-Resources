Most of the world's data live in databases, so learning how to access and unlock insights from these data is an essential skill for every data scientist. 
SQL, or ess-que-el, is the native language for interacting with databases and is designed for exactly this purpose. 
This course will give you a basic introduction to SQL. We hope you enjoy it.

1. Printing Something
`<SELECT 'SQL is cool'
AS result;`

query result: SQL is cool

SQL, which stands for Structured Query Language, is a language for interacting with data stored in something called a relational database.

You can think of a relational database as a collection of tables. A table is just a set of rows and columns, like a spreadsheet, which represents exactly one type of entity. For example, a table might represent employees in a company or purchases made, but not both.

Each row, or record, of a table contains information about a single entity. For example, in a table representing employees, each row represents a single person. Each column, or field, of a table contains a single attribute for all rows in the table. For example, in a table representing employees, we might have a column containing first and last names for all employees.

The table of employees might look something like this:

| id | name	    | age	| nationality | 
| 1	 | Jessica	| 22	| Ireland     | 
| 2	 | Gabriel	| 48	| France      | 
| 3	 | Laura	  | 36	|  USA        | 


While SQL can be used to create and modify databases, the focus of this course will be querying databases. 
A query is a request for data from a database table (or combination of tables). Querying is an essential skill for a data scientist, since the data you need for your analyses will often live in databases.

##### SELECTing single columns
In SQL, you can select data from a table using a SELECT statement. For example, the following query selects the name column from the people table:

SELECT name
FROM people;
In this query, SELECT and FROM are called keywords. In SQL, keywords are not case-sensitive, which means you can write the same query as:

select name
from people;
That said, it's good practice to make SQL keywords uppercase to distinguish them from other parts of your query, like column and table names.

It's also good practice (but not necessary for the exercises in this course) to include a semicolon at the end of your query. This tells SQL where the end of your query is!

Select the name of each person in the people table:
` SELECT name FROM people; `

##### SELECTing multiple columns
Well done! Now you know how to select single columns.

In the real world, you will often want to select multiple columns. Luckily, SQL makes this really easy. To select multiple columns from a table, simply separate the column names with commas!

For example, this query selects two columns, name and birthdate, from the people table:

SELECT name, birthdate
FROM people;
Sometimes, you may want to select all columns from a table. Typing out every column name would be a pain, so there's a handy shortcut:

SELECT *
FROM people;
If you only want to return a certain number of results, you can use the LIMIT keyword to limit the number of rows returned:

SELECT *
FROM people
LIMIT 10;

##### SELECT DISTINCT
Often your results will include many duplicate values. If you want to select all the unique values from a column, you can use the DISTINCT keyword.

This might be useful if, for example, you're interested in knowing which languages are represented in the films table:

` SELECT DISTINCT language FROM films; `


Learning to COUNT
What if you want to count the number of employees in your employees table? The COUNT() function lets you do this by returning the number of rows in one or more columns.

For example, this code gives the number of rows in the people table:

` SELECT COUNT(*)
  FROM people; `



Practice with COUNT
As you've seen, COUNT(*) tells you how many rows are in a table. However, if you want to count the number of non-missing values in a particular column, you can call COUNT() on just that column.

For example, to count the number of birth dates present in the people table:

SELECT COUNT(birthdate)
FROM people;
It's also common to combine COUNT() with DISTINCT to count the number of distinct values in a column.

For example, this query counts the number of distinct birth dates contained in the people table:

SELECT COUNT(DISTINCT birthdate)
FROM people;
Let's get some practice with COUNT()!
