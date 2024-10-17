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
