Sinatra app for Todo webapp

## Installation

You need to have ruby 3.1.2 installed. You also need to have postgres installed.

### Download the code

run

```
git clone https://github.com/SarahBunker/todo_v2_app.git
```

from your terminal.

### Create the database `todos`

```
createdb todos
```

### upload the schema

```
psql -d todos < schema.sql
```

## Starting the application

bundle exec ruby todo.rb

**Note**
Using bundle exec to execute the file ensures that the file is executed using the correct gem versions. You can have multiple versions of a gem installed in your operating system and Bundler is used to isolate the applications gem dependancies from other gems installed on your system.

## What this project accomplishes

This application moves from using session persistence through cookies to using a psql database for data persistence.

This involves dynamically creating SQL statements.

### Usefule PG commands

| Command |	What it does |
| -------- | -------- |
| PG.connect(dbname: "a_database") |	Create a new PG::Connection object |
| connection.exec("SELECT * FROM table_name")	| execute a SQL query and return a PG::Result object |
| result.values |	Returns an Array of Arrays containing values for each row in result |
| result.fields |	Returns the names of columns as an Array of Strings |
| result.ntuples | Returns the number of rows in result |
| result.each(&block) |	Yields a Hash of column names and values to the block for each row in result |
| result.each_row(&block) |	Yields an Array of values to the block for each row in result |
| result[index] |	Returns a Hash of values for row at index in result |
| result.field_values(column) |	Returns an Array of values for column, one for each row in result |
| result.column_values(index) |	Returns an Array of values for column at index, one for each row in result |

adding a schema to the database


from command line
```
psql -d expenses < schema.sql
```
from postgres interface (replace the file path with the location of the schema file)
```
\i ~/Documents/LS/RB185/demo_project/schema.sql
```

