# PostgreSQL Meta-Commands

## **1. Connection and Session**

| Meta-Command           | Description                                      |
| ---------------------- | ------------------------------------------------ |
| `\c [DBNAME]`          | Connect to another database                      |
| `\conninfo`            | Display information about the current connection |
| `\password [USERNAME]` | Change a user's password                         |
| `\q`                   | Quit the `psql` terminal                         |

## **2. Database Operations**

| Meta-Command | Description                                    |
| ------------ | ---------------------------------------------- |
| `\l`         | List all databases                             |
| `\l+`        | List all databases with additional information |
| `\c DBNAME`  | Connect to a specified database                |

## **3. Schema and Table Operations**

| Meta-Command | Description                                     |
| ------------ | ----------------------------------------------- |
| `\dn`        | List all schemas                                |
| `\dn+`       | List schemas with additional information        |
| `\dt`        | List tables in the current schema search path   |
| `\dt *.*`    | List tables in all schemas                      |
| `\dt+`       | List tables with additional information         |
| `\d TABLE`   | Describe a table, including columns and indexes |
| `\d+ TABLE`  | Describe a table with additional information    |
| `\di`        | List indexes                                    |
| `\dv`        | List views                                      |
| `\dm`        | List materialized views                         |
| `\ds`        | List sequences                                  |
| `\df`        | List functions                                  |
| `\df+`       | List functions with additional information      |
| `\dT`        | List data types                                 |

## **4. User and Permission Operations**

| Meta-Command | Description                            |
| ------------ | -------------------------------------- |
| `\du`        | List database roles (users and groups) |
| `\du+`       | List roles with additional information |

## **5. Query and Output Settings**

| Meta-Command | Description                                        |
| ------------ | -------------------------------------------------- |
| `\x`         | Toggle expanded output mode                        |
| `\timing`    | Toggle query execution time display                |
| `\pset`      | Configure output formatting                        |
| `\a`         | Toggle between aligned and unaligned output        |
| `\t`         | Toggle the display of column headers and row count |
| `\H`         | Toggle HTML output mode                            |
| `\o [FILE]`  | Send query output to a file                        |
| `\e`         | Open the query buffer in an external editor        |
| `\p`         | Display the current query buffer                   |
| `\r`         | Clear the query buffer                             |

## **6. Help and Information**

| Meta-Command | Description                                    |
| ------------ | ---------------------------------------------- |
| `\?`         | Display help for all meta-commands             |
| `\h`         | Display help for SQL commands                  |
| `\h SELECT`  | Display syntax help for the `SELECT` statement |
| `\version`   | Display PostgreSQL client version information  |
| `\conninfo`  | Display current connection information         |

## **7. Script Execution and File Operations**

| Meta-Command       | Description                                                     |
| ------------------ | --------------------------------------------------------------- |
| `\i FILE`          | Execute SQL commands from a file                                |
| `\ir FILE`         | Execute SQL commands from a file relative to the current script |
| `\o FILE`          | Write query output to a file                                    |
| `\echo TEXT`       | Print text to standard output                                   |
| `\! COMMAND`       | Execute a shell command                                         |
| `\set`             | Set a `psql` variable                                           |
| `\unset NAME`      | Unset a `psql` variable                                         |
| `\watch [SECONDS]` | Repeatedly execute the previous query at specified intervals    |
