# Tutorial: Accessing a relational database

https://go.dev/doc/tutorial/database-access

## Command History

```sh
# Create a module
$ mkdir data-access
$ cd data-access
$ go mod init example.com/data-access

# Ready Database
mysql> create database recordings;
mysql> use recordings;
mysql> source /path/to/create-tables.sql

# Write code

# Get dependencies
$ go get
go: downloading github.com/go-sql-driver/mysql v1.8.0
go: downloading filippo.io/edwards25519 v1.1.0
go: added filippo.io/edwards25519 v1.1.0
go: added github.com/go-sql-driver/mysql v1.8.0

# Run
$ export DBUSER=username
$ export DBPASS=password
$ go run .
```

## DB sql to start

```sql
DROP TABLE IF EXISTS album;
CREATE TABLE album (
  id         INT AUTO_INCREMENT NOT NULL,
  title      VARCHAR(128) NOT NULL,
  artist     VARCHAR(255) NOT NULL,
  price      DECIMAL(5,2) NOT NULL,
  PRIMARY KEY (`id`)
);

INSERT INTO album
  (title, artist, price)
VALUES
  ('Blue Train', 'John Coltrane', 56.99),
  ('Giant Steps', 'John Coltrane', 63.99),
  ('Jeru', 'Gerry Mulligan', 17.99),
  ('Sarah Vaughan', 'Sarah Vaughan', 34.98);
```
