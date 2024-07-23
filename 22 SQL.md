# SQL TUTORIAL

# 1. Wprowadzenie do SQL
SQL to standardowy język służący do uzyskiwania dostępu do baz danych i manipulowania nimi. Czym jest SQL? 
- to skrót od Structured Query Language (język zapytań strukturalnych),
- umożliwia dostęp do bazy danych i manipulowanie nimi.

Co potrafi SQL?
- może wykonywać zapytania do bazy danych,
- może pobierać dane z bazy danych,
- może wstawiać rekordy do bazy danych,
- może aktualizowa rekordy w bazie danych,
- może usuwać rekordy w bazie danych,
- może tworzyć nowe bazy danych,
- może tworzyć nowe tabele w bazie danych,
- może tworzyć procedury składowane w bazie danych,
- może tworzyć widoki w bazie danych,
- może ustawić uprawnienia do tabeli, procedur i widoków.

# 2. Składnia SQL
Instrukcje SQL - większość działań, które należy wykonać na bazie danych, wykonuje się za pomocą poleceń SQL. Instrukcje SQL składają się ze słów kluczowych, które są łatwe do zrozumienia.
```
SELECT * FROM Customers;
```

# 3. SQL SELECT
Słóży do wybierania danych z bazy danych. 
```
SELECT customerName, City
FROM Customers;
```
Składnia:
SELECT column1, column2, ...
FROM teabel_name;
Wybierz wszystkie kolumny
```
SELECT * FROM Customers;
```

# 4. SQL SELECT DISTINCT 
Zwraca wyłącznie różne wartości.
```
SELECT DISTINCT country FROM Customers;
```
Kolumna tabeli często zawiera wiele powtarzających się wartości, a czesem trzeba wyświetlić tylko różne (odrębne) wartości.
Składnia:
SELECT DISTINCT column1, column2...
FROM tabel_name;

Liczba odrębnych - używając DISTINCT w funkcji o nazwie COUNT, możemy zwrócić liczbę różnych krajów.
```
SELECT COUNT(DISTINCT Country) FROM Customer;
```

# 5. SQL WHERE 
Służy do filtrowania rekordów.
```
SELECT * FROM Customer WHERE Country = "Mexico";
```
Składnia:
SELECT column1, column2, ...
FROM tebel_name
WHERE condition
Do filtrowania wyszukiwania możesz używać także innych operatorów.
= Równe
> Większe
< Mniejsze
>= Większe lub równe
<= Mniejsze lub równe
<> Nie równe !=
BETWEEN Pomiędzy pewnymi zakresami
LIKE Wyszukaj wzór
IN Aby określić wiele możliwych wartości dla kolumn

# 6. SQL ORDER BY
Służy do sortowania w kolejności rosnącej lub malejącej.
```
SELECT * FROM Products OREDE BY Price;
```
Składnia:
SELECT column1, column2, ...
FROM tabel_name
ORDER BY column1, column2, ... ASC/DESC

# 7. SQL AND
Operator and służy do filtrowania rekordów na podstawie więcej niż jednego warónku.
```
SELECT *
FROM Customers
WHERE Country = 'Spain' AND 'Customer Name LIKE 'G%';
```
Składnia: SELECT column1, column2
FROM tabel_name
WHERE Condition1 AND condition2 ...

# 8. SQL OR
Operator OR służy do filtrowania rekordów na podstawie więcej niż jednego warunku.
```
SELECT *
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
```
Składnia: 
SELECT column1, column2, ...
FROM tebel_name
WHERE condition1 OR condition2

# 9. SQL NOT
Operator jest używany z innymi operatorami w celu uzyskania wyniku przeciwnego, zwanego ujemnym.
```
SELECT * FROM Customers
WHERE NOT Country = 'Spain';
```
Składnia: 
SELECT column1, column2, ...
FROM tabel_name
WHERE NOT condition

# 10. INSERT INTO SQL
Służy do wstawiania nowych rekordów do tabeli.
INSERT INTO można zapisać na dwa sposoby:
- Określ nazwę kolumny i wartości, które mają zostać wstawione:
```
INSERT INTO tabel_name (column1, column2...)
VALUES (value1, value2,...)
```
- Jeśli dostajesz wartość dla wszystkich kolumn w tabeli, nie musisz określać nazw kolumn w zapytaniu SQL.
```
INSERT INTO tabel_name
VALUES (value1, value2, ...)
```
