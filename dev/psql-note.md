# Postgresql Note

## Index
* [Postgresql Command](#Postgresql-Command)
* [Postgresql Query](#Postgresql-Query)

## Postgresql Command
* `\t`: turn on or off the tuple only mode
* `\dt`: show all tables in the current schema
* `\d+ table`: show the detailed information of the table
* `\conninfo`: see the connect infomation

## Postgresql Query
* Add foreign keys
    ```sql
    ALTER TABLE table_name ADD CONSTRAINT constraint_name FOREIGN KEY(a1) REFERENCES parent_table(b1);
    ```
* Add unique constraints
    ```sql
    ALTER TABLE login ADD CONSTRAINT constraint_name UNIQUE(r);
    ```
* Add attributes to a table
    ```sql
    ALTER TABLE table_name ADD COLUMN new_column_name data_type;
    ```
* Change the value of an attribute to a table
    ```sql
    UPDATE TABLE table_name SET attr=... where ...
    ```
* Change data type of an attribute
    ```sql
    ALTER TABLE table_name
    ALTER COLUMN column_name [SET DATA] TYPE new_data_type;
    ```