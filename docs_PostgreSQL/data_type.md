# PostgreSQL Data Types

## **1. Numeric Types**

| Data Type          | Description                                            | Example        |
| ------------------ | ------------------------------------------------------ | -------------- |
| `SMALLINT`         | 2-byte signed integer                                  | `100`          |
| `INTEGER` / `INT`  | 4-byte signed integer                                  | `10000`        |
| `BIGINT`           | 8-byte signed integer                                  | `1000000000`   |
| `DECIMAL(p,s)`     | Exact numeric value with specified precision and scale | `123.45`       |
| `NUMERIC(p,s)`     | Equivalent to `DECIMAL`                                | `123.45`       |
| `REAL`             | 4-byte floating-point number                           | `3.14`         |
| `DOUBLE PRECISION` | 8-byte floating-point number                           | `3.1415926535` |
| `SERIAL`           | Auto-incrementing 4-byte integer                       | `1`            |
| `BIGSERIAL`        | Auto-incrementing 8-byte integer                       | `1`            |

## **2. Character Types**

| Data Type    | Description                                                      | Example         |
| ------------ | ---------------------------------------------------------------- | --------------- |
| `CHAR(n)`    | Fixed-length character string                                    | `'ABC'`         |
| `VARCHAR(n)` | Variable-length character string with a maximum length           | `'Hello'`       |
| `TEXT`       | Variable-length character string without a declared length limit | `'Hello World'` |

## **3. Date and Time Types**

| Data Type             | Description                     | Example                    |
| --------------------- | ------------------------------- | -------------------------- |
| `DATE`                | Calendar date                   | `'2026-11-23'`             |
| `TIME`                | Time of day without time zone   | `'14:30:00'`               |
| `TIME WITH TIME ZONE` | Time of day with time zone      | `'14:30:00+09'`            |
| `TIMESTAMP`           | Date and time without time zone | `'2026-11-23 14:30:00'`    |
| `TIMESTAMPTZ`         | Date and time with time zone    | `'2026-11-23 14:30:00+09'` |
| `INTERVAL`            | Time interval or duration       | `'2 days'`                 |

## **4. Boolean Type**

| Data Type | Description                   | Example         |
| --------- | ----------------------------- | --------------- |
| `BOOLEAN` | Logical value (true or false) | `TRUE`, `FALSE` |

## **5. UUID Type**

| Data Type | Description                                        | Example                                  |
| --------- | -------------------------------------------------- | ---------------------------------------- |
| `UUID`    | Universally Unique Identifier (128-bit identifier) | `'550e8400-e29b-41d4-a716-446655440000'` |

## **6. Binary Types**

| Data Type | Description                 | Example     |
| --------- | --------------------------- | ----------- |
| `BYTEA`   | Variable-length binary data | Binary data |

## **7. JSON Types**

| Data Type | Description                                                                           | Example             |
| --------- | ------------------------------------------------------------------------------------- | ------------------- |
| `JSON`    | JSON data stored as text, preserving the original input representation                | `'{"name":"John"}'` |
| `JSONB`   | JSON data stored in a decomposed binary format, optimized for processing and indexing | `'{"name":"John"}'` |

## **8. Other Useful Types**

| Data Type  | Description                           | Example                   |
| ---------- | ------------------------------------- | ------------------------- |
| `INET`     | IPv4 or IPv6 host address             | `'192.168.1.1'`           |
| `CIDR`     | IPv4 or IPv6 network address          | `'192.168.1.0/24'`        |
| `MACADDR`  | MAC address                           | `'08:00:2b:01:02:03'`     |
| `XML`      | XML data                              | `'<name>John</name>'`     |
| `TSVECTOR` | Text search document representation   | Used for full-text search |
| `TSQUERY`  | Full-text search query representation | Used for full-text search |
