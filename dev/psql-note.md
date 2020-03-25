# Postgresql Note

## Index
* [Postgresql Command](#Postgresql-Command)
* [Postgresql Query](#Postgresql-Query)

## Postgresql Command
* `\t`: turn on or off the tuple only mode
* `\dt`: show all tables in the current schema
* `\d+ table`: show the detailed information of the table
* `\conninfo`: see the connect infomation

## Postgresql Keyword
* `ON UPDATE CASCADE` </br>
  `ON DELETE CASCADE` </br>
  This is used when declaring the foreign keys.
  *CASCADE* means that when delete/update happens in the referenced table, the corresponding tuple in the current relation will also be deleted/updated automatically.

## Postgresql Query
* Drop a constraint
    ```sql
    ALTER TABLE table_name DROP CONSTRAINT constraint_name;
    ```
* Add a foreign key
    ```sql
    ALTER TABLE table_name ADD CONSTRAINT constraint_name FOREIGN KEY(a1) REFERENCES parent_table(b1);
    ```
* Add a unique constraint
    ```sql
    ALTER TABLE login ADD CONSTRAINT constraint_name UNIQUE(r);
    ```
* Add attributes to a table
    ```sql
    ALTER TABLE table_name ADD COLUMN new_column_name data_type;
    ```
* Change the value of an attribute to a table
    ```sql
    UPDATE table_name SET attr=... where ...
    ```
* Change data type of an attribute
    ```sql
    ALTER TABLE table_name
    ALTER COLUMN column_name [SET DATA] TYPE new_data_type;
    ```