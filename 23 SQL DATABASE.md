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

# 6. ALTER TABLE
Polecenie ALTER TABLEto służy do dodawania, usuwania lub modyfikowania kolumn w istniejącej tabeli. Tego ALTER TABLEpolecenia używa się również do dodawania i usuwania różnych ograniczeń w istniejącej tabeli.

ALTER TABLE - DODAJ Kolumnę
Aby dodać kolumnę do tabeli, użyj następującej składni:
```
ALTER TABLE table_name
ADD column_name datatype;
```
Przykład: Poniższy kod SQL dodaje kolumnę „E-mail” do tabeli „Klienci”:
```
ALTER TABLE Customers
ADD Email varchar(255);
```
ALTER TABELĘ - USUŃ KOLUMNĘ
Aby usunąć kolumnę w tabeli, użyj następującej składni (należy pamiętać, że niektóre systemy baz danych nie pozwalają na usuwanie kolumn):
```
ALTER TABLE table_name
DROP COLUMN column_name;
```

Przykład: Poniższy kod SQL usuwa kolumnę „E-mail” z tabeli „Klienci”:
```
ALTER TABLE Customers
DROP COLUMN Email;
```
ALTER TABLE - ZMIEŃ NAZWĘ KOLUMNY
Aby zmienić nazwę kolumny w tabeli, użyj następującej składni:
```
ALTER TABLE table_name
RENAME COLUMN old_name to new_name;
```
ALTER TABLE - ZMIEŃ/MODYFIKUJ TYP DANYCH
Aby zmienić typ danych kolumny w tabeli, użyj następującej składni:

Serwer SQL / MS Access:
```
ALTER TABLE table_name
ALTER COLUMN column_name datatype;
```
Zmień przykład typu danych
Teraz chcemy zmienić typ danych kolumny o nazwie „DateOfBirth” w tabeli „Persons”.

Używamy następującego polecenia SQL:
```
ALTER TABLE Persons
ALTER COLUMN DateOfBirth year;
```
Należy zauważyć, że kolumna „DateOfBirth” jest teraz typu „year” i będzie zawierać rok w formacie dwu- lub czterocyfrowym.

Przykład DROP COLUMN
Następnie chcemy usunąć kolumnę o nazwie „DateOfBirth” w tabeli „Persons”.

Używamy następującego polecenia SQL:
```
ALTER TABLE Persons
DROP COLUMN DateOfBirth;
```

# 7. SQL Constraints
Ograniczenia SQL służą do określania reguł dla danych w tabeli.

Tworzenie ograniczeń SQL
Ograniczenia można określić podczas tworzenia tabeli za pomocą CREATE TABLEpolecenia lub po utworzeniu tabeli za pomocą ALTER TABLEpolecenia.

Składnia:
```
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
```

Ograniczenia SQL
Ograniczenia SQL służą do określania reguł dla danych w tabeli.

Ograniczenia służą do ograniczania typu danych, które mogą trafić do tabeli. Zapewnia to dokładność i niezawodność danych w tabeli. Jeśli istnieje jakiekolwiek naruszenie między ograniczeniem a działaniem danych, działanie jest przerywane.

Ograniczenia mogą być na poziomie kolumny lub tabeli. Ograniczenia na poziomie kolumny dotyczą kolumny, a ograniczenia na poziomie tabeli dotyczą całej tabeli.

W języku SQL powszechnie stosuje się następujące ograniczenia:

NOT NULL- Zapewnia, że ​​kolumna nie może mieć wartości NULL
UNIQUE- Zapewnia, że ​​wszystkie wartości w kolumnie są różne
PRIMARY KEY- Kombinacja a NOT NULLi UNIQUE. Unikalnie identyfikuje każdy wiersz w tabeli
FOREIGN KEY - Zapobiega działaniom, które mogłyby zniszczyć powiązania między tabelami
CHECK- Zapewnia, że ​​wartości w kolumnie spełniają określony warunek
DEFAULT- Ustawia wartość domyślną dla kolumny, jeśli nie określono żadnej wartości
CREATE INDEX- Służy do bardzo szybkiego tworzenia i pobierania danych z bazy danych

# 8. SQL NOT NULL
Domyślnie kolumna może przechowywać wartości NULL. Ograniczenie NOT NULLto wymusza, aby kolumna NIE akceptowała wartości NULL. Wymusza to, aby pole zawsze zawierało wartość, co oznacza, że ​​nie można wstawić nowego rekordu ani zaktualizować rekordu bez dodania wartości do tego pola.

SQL NOT NULL w CREATE TABLE
Poniższy kod SQL zapewnia, że ​​kolumny „ID”, „LastName” i „FirstName” NIE przyjmą wartości NULL podczas tworzenia tabeli „Persons”:
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

# 9. SQL UNIQUE ograniczenie 
Ograniczenie to UNIQUEzapewnia, że ​​wszystkie wartości w kolumnie są różne. Zarówno ograniczenia, UNIQUEjak i PRIMARY KEYzapewniają gwarancję unikatowości kolumny lub zestawu kolumn. Ograniczenie PRIMARY KEYautomatycznie ma UNIQUEograniczenie. Można jednak mieć wiele UNIQUEograniczeń na tabelę, ale tylko jedno PRIMARY KEYograniczenie na tabelę.

Ograniczenie SQL UNIQUE dla CREATE TABLE
Poniższy kod SQL tworzy UNIQUEograniczenie dla kolumny „ID” podczas tworzenia tabeli „Osoby”:
```
CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

# 10. PRIMARY KEY SQL 
Ograniczenie klucza podstawowego SQL - Ograniczenie PRIMARY KEYjednoznacznie identyfikuje każdy rekord w tabeli. Klucze podstawowe muszą zawierać wartości UNIQUE i nie mogą zawierać wartości NULL. Tabela może mieć tylko JEDEN klucz podstawowy. W tabeli klucz podstawowy może składać się z jednej lub wielu kolumn (pól).

Klucz podstawowy SQL w CREATE TABLE
Poniższy kod SQL tworzy PRIMARY KEYkolumnę „ID” podczas tworzenia tabeli „Osoby”:
MySQL:
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```
Serwer SQL / Oracle / MS Access:
```
CREATE TABLE Persons (
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```
Aby umożliwić nazwanie PRIMARY KEYograniczenia i zdefiniowanie PRIMARY KEYograniczenia dla wielu kolumn, należy użyć następującej składni SQL:

MySQL / SQL Server / Oracle / MS Access:
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```
Uwaga: W powyższym przykładzie jest tylko JEDEN PRIMARY KEY(PK_Person). Jednak WARTOŚĆ klucza podstawowego składa się z DWÓCH KOLUMN (ID + Nazwisko).
Klucz podstawowy SQL w ALTER TABLE
Aby utworzyć PRIMARY KEYograniczenie dla kolumny „ID”, gdy tabela jest już utworzona, należy użyć następującego polecenia SQL:
MySQL / SQL Server / Oracle / MS Access:
```
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```
Aby umożliwić nazwanie PRIMARY KEYograniczenia i zdefiniowanie PRIMARY KEYograniczenia dla wielu kolumn, należy użyć następującej składni SQL:

MySQL / SQL Server / Oracle / MS Access:
```
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```
Uwaga: Jeśli chcesz ALTER TABLEdodać klucz podstawowy, kolumna(y) klucza podstawowego musi zostać zadeklarowana w taki sposób, aby nie zawierała wartości NULL (podczas pierwszego tworzenia tabeli).
USUŃ ograniczenie klucza podstawowego
Aby usunąć PRIMARY KEYograniczenie, użyj następującego polecenia SQL:

MySQL:
```
ALTER TABLE Persons
DROP PRIMARY KEY;
```
Serwer SQL / Oracle / MS Access:
```
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```

# 12. SQL FOREIGN KEY
Ograniczenie FOREIGN KEYto służy zapobieganiu działaniom, które mogłyby zniszczyć powiązania między tabelami. A FOREIGN KEYto pole (lub zbiór pól) w jednej tabeli, które odwołuje się do pola PRIMARY KEYw innej tabeli.
Tabelę zawierającą klucz obcy nazywa się tabelą podrzędną, a tabelę zawierającą klucz podstawowy nazywa się tabelą referencyjną lub nadrzędną.
Klucz obcy SQL w CREATE TABLE
Poniższy kod SQL tworzy FOREIGN KEYkolumnę „PersonID” podczas tworzenia tabeli „Orders”:
MySQL:
```
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```
Serwer SQL / Oracle / MS Access:

```
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```
Aby umożliwić nazwanie FOREIGN KEYograniczenia i zdefiniowanie FOREIGN KEYograniczenia dla wielu kolumn, należy użyć następującej składni SQL:

MySQL / SQL Server / Oracle / MS Access:
```
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```
Klucz obcy SQL w ALTER TABLE
Aby utworzyć FOREIGN KEYograniczenie dla kolumny „PersonID”, gdy tabela „Orders” jest już utworzona, należy użyć następującego kodu SQL:

MySQL / SQL Server / Oracle / MS Access:
```
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```
Aby umożliwić nazwanie FOREIGN KEYograniczenia i zdefiniowanie FOREIGN KEYograniczenia dla wielu kolumn, należy użyć następującej składni SQL:

MySQL / SQL Server / Oracle / MS Access:
```
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```
USUŃ OGRANICZENIE KLUCZA OBCEGO
Aby usunąć FOREIGN KEYograniczenie, użyj następującego polecenia SQL:

MySQL:
```
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```
Serwer SQL / Oracle / MS Access:
```
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```
