# Database Guide for the Todo App

### Before we can create the tables, let us identify the entities and the relationships between the entities based on the requirements that we have. Here entites can be any real work object that can be described using properties. This is similar to how we think of classes in `OOPS`. Tables can be used to represent entities or relations between entities.

</br>

### Based on the requirements we can create the following schema. It is always important to have a schema diagram to show the entities and their relationships.

</br>

![Database Structure](https://github.com/BetsolLLC/campus-workshops-knowledge-base/blob/master/Databases/assets/TodoDbStruct.png?raw=true "Database Structure")

### Here we have identifiled that we need two tables one to describe the Todo items and another to describe the users who will be creating the Todo lists.It was possbible for us to have the user information in the Todo table itself, but it is always best practice to normalize our tables from the start and reduce redendencies. If we have the user infomation stored in we would have to repeat the user information in every Todo item that the user creates.Hence we will keep the user information in a separte table. We can have a column `user_id` which can store the id of the user who created the Todo item in the `TODO` table. This will become the foreign key to the `Users` table.

</br>

### Here each record represents a Todo item created by the user and each record in the Users table is used to represent a unique user who create the Todo item.

</br>

## 1) Create a table using `CREATE` command

Now that we have the schema identified we can convert the schema to actual tables in the database.

Below is the syntax to create a table in `PostgreSQL` :

```
CREATE TABLE [IF NOT EXISTS] table_name (
   column1 datatype(length) column_contraint,
   column2 datatype(length) column_contraint,
   column3 datatype(length) column_contraint,
   table_constraints
);
```

Using the above syntax let us create the tables based on our schema diagram.

Below are the command by which we can create the two tables:

```
CREATE TABLE TODO
(
   id INT SERIAL PRIMARY KEY,
   title VARCHAR(50) NOT NULL,
   complete BOOLEAN,
   date_modified TIMESTAMP
);

CREATE TABLE Users
(
   id INT PRIMARY KEY,
   name VARCHAR(20)
);
```

Here we are adding an `id` properly to the Todo tables in order to uniquely identify the record and we have also make tis field to auto increment using `SERIAL` keyword. This ensurs that the id is automatically added and incremented whenever we add a new item and it does not need to be explicitly specified.

</br>

## 2) Add a column using the `ALTER` command

If you look at the previous create commands you can find the we have not added the `user_id` field to the Todo table and have not specified the relationship between the Todo and the users table. This was done intentionally in order to demostrate the `ALTER` command.

Below is the syntax for the `ALTER` command:

```
ALTER TABLE table_name
ADD COLUMN column_name datatype column_constraint;
```

PostgreSQL provides you with many actions:

- Add a column
- Drop a column
- Change the data type of a column
- Rename a column
- Set a default value for the column.
- Add a constraint to a column.
- Rename a table

Let us use the above syntax to add a new column to the Todo table with a foreign key reference to the Users table.

```
ALTER TABLE TODO
ADD COLUMN user_id INT
CONSTRAINT fk_user_id
REFERENCES Users(id);
```

</br>

## 3) Insert data to the tables using `INSERT` command

Now that we have created the tables. Let us add some data. The data is usually added from the backend application which connects to the database, but for our demostration let us create the data manually.

Below is the syntax to insert the records to a table:

```
INSERT INTO table_name(column1, column2, …)
VALUES (value1, value2, …);
```

Using the able syntax let us insert the data to the `Todo` and the `Users` table

```
INSERT INTO Users(id,name) VALUES (1,'John');
INSERT INTO Users(id,name) VALUES (2,'Jack');
INSERT INTO Users(id,name) VALUES (3,'Dan');
INSERT INTO TODO(title,complete,date_modified,user_id) VALUES ('Day 1',false,CURRENT_TIMESTAMP,1);
INSERT INTO TODO(title,complete,date_modified,user_id) VALUES ('Day 2',false,CURRENT_TIMESTAMP,1);
INSERT INTO TODO(title,complete,date_modified,user_id) VALUES ('Day 3',false,CURRENT_TIMESTAMP,1);
INSERT INTO TODO(title,complete,date_modified,user_id) VALUES ('Day 1',false,CURRENT_TIMESTAMP,2);
INSERT INTO TODO(title,complete,date_modified,user_id) VALUES ('Day 4',false,CURRENT_TIMESTAMP,3);
```

Note that we did not have to specify the value for the `id` propertly as it is added automatically and incremented as rows are added.

</br>

## 4) Update a record using the `UPDATE` command

We can also update the fieds of the table records using the `UPDATE` command.

Below is the syntax for the `UPDATE` command:

```
UPDATE table_name
SET column1 = value1,
    column2 = value2,
    ...
WHERE condition;
```

Let us update the `complete` field to `true` for one of the Todo item using the above syntax.

```
UPDATE TODO SET complete=true,date_modified=CURRENT_TIMESTAMP WHERE id=1
```

</br>

## 5) Join the tables using the `JOIN` clause

The `JOIN` clause is a very useful concept in databases and it is very crucial to learn how `JOINS` work.

In RDBMS, data is typically distributed in more than one table. To select complete data, you often need to query data from multiple tables.

This is where `JOINS` come in handy. They can be used to select data from multiple based on come common fileds in the combining tables, usually a foreign key field. We will be specifiaclly focusing on a specific type of `JOIN` called the `INNER JOIN` for this walkthrough.

<b>How the INNER JOIN works:</b>

For each row in the table A, inner join compares the value in the pka column with the value in the fka column of every row in the table B:

- If these values are equal, the inner join creates a new row that contains all columns of both tables and adds it to the result set.
- In case these values are not equal, the inner join just ignores them and moves to the next row.
  The following Venn diagram illustrates how INNER JOIN clause works.

![INNER JOIN](https://github.com/BetsolLLC/campus-workshops-knowledge-base/blob/master/Databases/assets/InnerJoin.png?raw=true "Inner Join")

Below is the syntax for the `JOIN` clause.

```
SELECT
	pka,
	c1,
	pkb,
	c2
FROM
	A
INNER JOIN B ON pka = fka;
```

Let us join the `Todo` table and the `Users` table using the foreign key `user_id` in the `Todo` table which points to the `id` field in the `Users` table.

```
SELECT t.title,u.name
FROM TODO t
JOIN Users u ON t.user_id=u.id
```

Note that we have use variables `t` and `u` in order to easily reference the `Todo` and `Users` table.

We are just selecting the title of the Todo item and the name of the user who created it.

</br>

## 6) Filter the data using `WHERE` clause and order the records using the ORDER BY clause

Let us go a step further and and filter the result by a specific user using the `WHERE` clause and order the data according to the `date_modified` field in the decending order so that we see the recently added items at the top.

```
SELECT t.title,u.name
FROM TODO t
JOIN Users u ON t.user_id=u.id
WHERE u.name ='John'
ORDER by t.date_modified desc
```

</br>

## 7) Find the count of records by grouping the data using `COUNT` function and `GROUP BY` clause

Let us now dive into another useful concept which is the `GROUP BY` clause.

We can use the `GROUP BY` clause whenever we need to group the data by specific fields and reduce the group to a single result by performing some operations. These operations can be one of the many `Aggregate Functions` that we have in SQL like `AVG(), COUNT(), SUM(), MIN(), MAX()..etc`.

You can find out more about the aggregate functions from the link below.

[Aggregate Functions Docs](https://www.postgresql.org/docs/9.5/functions-aggregate.html)

Below is the syntax for the `GROUP BY` clause:

```
SELECT
   column_1,
   column_2,
   ...,
   aggregate_function(column_3)
FROM
   table_name
GROUP BY
   column_1,
   column_2,
   ...;
```

Based on the above syntax let us find out how many items have each users created. To accomplish this, let us group the data according to the user name. This will divide the data into multiple groups and each group is represented by the username. Now in order to find the count the number of records in each group, let us apply the `COUNT` function which will count the number of records in each group and shrink each of the groups to a single record haveing the count of records in each group.

Below is the query for the same:

```
SELECT COUNT(1) AS Total, u.name
FROM TODO t
JOIN Users u ON t.user_id=u.id
GROUP BY u.name
```

Note that we have use the `AS` keyword to assign an alias name to the `COUNT` column.

It is also possible to group by muliple columns.

For more information regarding the `GROUP BY` clause, refer the link below.
[GROUP BY Docs](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-group-by/)

</br>

## 8) Filtering group by using the `HAVING` clause

Let us build on the previous query and apply a filter to the group using the `HAVING`. The `HAVING` clause is similar to the `WHERE` clause with regards to being used for filtering the data in the result set, but the `HAVING` clause is used to apply conditions to filter the groups that are created by the `GROUP BY` clause. The `HAVING` clause should be applied to the grouping field(Ex :- `u.name`) or we can also filter the group by the result of an aggregate function(Ex :- `HAVING COUNT(1) > 2`).

Let us use the `HAVING` to filter the group have `John` as the `username`.

```
SELECT COUNT(1) AS Total, u.name
FROM TODO t
JOIN Users u ON t.user_id=u.id
GROUP BY u.name
HAVING u.name = 'John'
```

</br>

## 9) Using `COUNT`, `GROUP BY` and `HAVING` together

Let us now try to group by multiple columns and find out among all the Todo items submitted by all the users, how many are of those items are completed by each user.

For this first we will have to first group the data by `username` and later within each user group we will futher group by the items that are completed and the items that are not completed which is tracked by the `completed` field.

After that we can add a condition in the `WHERE` clause to just have the items that are completed by specifying `completed=true`

```
SELECT COUNT(1) AS Total, u.name
FROM TODO t
JOIN Users u ON t.user_id=u.id
GROUP BY u.name,t.complete
HAVING t.complete=true
```

</br>

## 10) Delete a record using the `DELETE` command

Finally let us look at the DELETE statement which is used to remove data in the tables based on certain condition.

Below is a query to delete a record in the `TODO` table having the `id` of 5

```
DELETE FROM TODO WHERE id=5
```

Note that it is possible to remove multiple columns using the `DELETE` statement.

</br>

# Conclusion

Almost everytime in modern application development all the above queries/functionalities are executed using `ORMs` which are code absractions for connecting and working with databases. But nevertheless it is important to understand how the different SQL statements and clauses work under the hood.

Always take extra caution while executing delete and update statements in the database manually else you might get into a bad situation!

![Database Structure](https://github.com/BetsolLLC/campus-workshops-knowledge-base/blob/master/Databases/assets/DBDelete.jpg?raw=true "Database Structure")
