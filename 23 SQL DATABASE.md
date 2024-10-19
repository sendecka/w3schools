SQL DATABASE

# 1. SQL CREATE DATABASE 

Służy do utworzenia nowej bazy danych SQL.

Składnia:
```
CREATE DATABASE databasename;
```
Przykład: Utwórz bazę danych o nazwie 'testDB'.
```
CREATE DATABASE testDB;
```
Upewnij się, że masz uprawnienia administratora przed utworzeniem jakiejkolwiek bazy danych. Po jej utworzeniu możesz sprawdzić ją na liście baz danych za pomocą polecenia: SHOW DATABASE.

# 2. SQL DROP DATABASE

Służy do usówania istniejącej bazy danych SQL.

Składnia:
```
DROP DATABASE databasename;
```
Przykład: Usuń baze danych 'testDB'
```
DROP Database testDB;
```

# 3. SQL BACKUP DATABASE - służy do utworzenia pełnej kopii zapasowej istniejącej bazy danych SQL>

Składnia:
```
BACKUP DATABASE databasename
TO DISK = 'filepath';
```
Instrukcja SQL BACKUP DATABASE WITH DIFFERENTIAL - kopia zapasowa różnicowa obejmuje tylko te części bazy danych, które uległy zmianie od czasu ostatniej pełnej kopii zapasowej.
Składnia:
```
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL;
```
Przykład: Stwórz pełną kopię zapasową istniejącej bazy danych testDB.
```
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak';
```

# 4. Instrukcja SQL CREATE TABLE - służy do tworzenia nowej tabeli w bazie danych.

Składnia:
```
CREATE TABLE tabel_name (
  column1 datatype,
  column2 datatype,
  column3 datatype,
  ...
);
```

Parametry kolumny określają nazwy kolumn tabeli. Parametr datatype określa typ danych, jakie może przechowywać kolumna.

Przykład:  Stwórz tabelę o nazwie „Osoby” zawierającą pięć kolumn: PersonID, LastName, FirstName, Address i City
```
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

Kolumna PersonID jest typu int i przechowuje liczbę całkowitą. Kolumny LastName, FirstName, Address i City są typu varchar i mogą zawierać znaki, a maksymalna długość tych pól wynosi 255 znaków.

Utwórz tabelę używając innej tabeli.
Kopię istniejącej tabeli można również utworzyć za pomocą polecenia CREATE TABLE. Nowa tabela otrzymuje te same definicje kolumn. Można wybrać wszystkie kolumny lub określone kolumny.
Jeśli utworzysz nową tabelę, używając istniejącej tabeli, nowa tabela zostanie wypełniona istniejącymi wartościami ze starej tabeli.

Składnia:
```
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ....;
```
Przykład: Poniższy kod SQL tworzy nową tabelę o nazwie „TestTable” (która jest kopią tabeli „Customers”): 
```
CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;
```

# 5. SQL DROP TABLE

Polecenie DROP TABLEsłuży do usuwania istniejącej tabeli z bazy danych.
Składnia:
```
DROP TABLE table_name;
```
Przykład: Poniższe polecenie SQL usuwa istniejącą tabelę „Shippers”:
```
DROP TABLE Shippers;
```

TABELA ODCINANIA SQL - Polecenie TRUNCATE TABLEto służy do usuwania danych z tabeli, ale nie samej tabeli.
```
TRUNCATE TABLE table_name;
```
