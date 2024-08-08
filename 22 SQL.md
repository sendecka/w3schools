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

# 11. SQL NULL 
Pole z wartością NULL jest polem bez wartości.
Jeśli pole w tablei jest opcjonalne, możliwe jest wstawienie nowego rekordu bez dodawania wartości do tego pola. Następnie pole zostanie zapisane z wartością NULL.

Wartość NULL różni się od wartości zerowej lub pola zawierającego spację. Pole z NULL to pole, które zostało pozostawione puste podczas tworzenia rekordu.

Jak testować wartość NULL?
Nie można sprawdzić wartości NULL za pomocą operatorów posównania, takich jak =, <, <>. Zamiast tego będziemy musieli używać operatorów IS NULL i IS NOT NULL.
Składnia IS NULL:
```
SELECT column_names
FROM tabel_name
WHERE column_name IS NULL
```
Składnia IS NOT NULL:
```
SELECT column_names
FROM tabel_name
WHERE column_name IS NOT NULL
```

Operator IS NULL - służy do testowania pustych wartości (NULL).

Przykład: Wyświetl listę wszystkich klientów, którzy mają wartość NULL w polu adres.
```
SELECT customerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
```

Operator IS NOT NULL - służy do sprawdzania, czy wartości nie są puste.

Przykład: Wyświetl listę wszystkich klientów, których pole 'Address' ma wartość.
```
SELECT customerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```

# 12. SQL UPDATE
Służy do modyfikacji istniejących rekordów w tabeli.

Składnia:
```
UPDATE tabel_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
Jeśli pominiesz klauzurę WHERE to wszystkie rekordy w tabeli zostaną zaktualizowane.

Przykład: Zaktualizuj pierwszego klienta, przypisując mu nową osobę kontaktową i nowe miasto.
```
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City = 'Frankfurt'
WHERE CustomerID = 1;
```

# 13. SQL DELETE
Służy do usuwania istniejących rekordów w tabeli.
Składnia:
```
DELETE FROM tabel_name WHERE condition;
```
Zwróć uwagę na WHERE w DELETE, określa ona które rekordy powinny zostać usunięte. Jeśli ją pominiesz to wszystkie rekordy w tabeli zostaną usunięte.

Przykład: usuń klienta, Alfred Futterkiste z tabeli klienci
```
DELETE FROM Customers WHERE CustomerName = 'Alfred Futterkiste';
```
Można usunąć wszystkie rekordy z tabeli, oznacza to, że struktura tabeli atrybuty i indeksy pozostaną nienaruszone.
```
DELETE FROM tabel_name;
```
Usuń tabelę - aby całkowicie usunąć tabelę, należy użyć polecenia DROP TABEL.
Przykła: usuń tabelę klienci
```
DROP TABEL Customeers;
```

# 14. SQL TOP
SQL SELECT TOP - określa liczbę rekordów do zwrócenia, klauzura jest przydatna w przypadku dużych tabeli z tysiącami rekordów. Zwracanie dużej liczby rekordów może mieć wpływ na wydajność.
Przykład: wybieram tylko 3 pierwsze rekordy w tabeli klienci
```
SELECT TOP 3 * FROM Customers;
```
Nie wszystkie systemy baz danych obsługują klauzulę SELECT TOP. MySQL obsługuje LIMIT, podczas gdy Oracle używa FETCH FIRST n ROWS ONLY ROWS

# 15. SQL funkcje agregujące
Funkcje agregujące to funkcje, które wykonują obliczenia na zestawie wartości i zwracają pojedyńczą wartość.

Funkcje agregujące są często używane z GRUP BY instrukcją. GROUP BY dzieli zestaw wyników na grupy wartości, a funkcja agregująca może być używana do zwracania pojedyńczych wartości dla każdej grupy.

Najczęściej używanymi funkcjami agregującymi są:
- MIN() zwraca najmniejszą wartość w wybranej kolumnie,
- MAX() zwraca największąwartość w wybranej kolumnie,
- COUNT() zwraca liczbę wierszy w zakresie,
- SUM() zwraca całkowitą sumę kolumny liczbowej,
- AVG() zwraca średnią wartość kolumny liczbowej.

Funkcje agregujące ignorują wartość null (poza COUNT()).

# 16. SQL MIN() MAX()
- MIN() - zwraca najmniejszą wartość z wybranej kolumny.
Przykład: Znajdź najniższącenę.
```
SELECT MIN(Price)
FROM Product;
```
Składnia: SELECT MIN(column_name) FROM tabel_name WHERE condition;

- MAX() - zwraca największą wartość z wybranej kolumny.
Przykład: Znajdź najwyższąwartość w kolumnie Cena.
```
SELECT MAX(Price)
FROM Products;
```
Składnia: SELECT MAX(column_name) FROM tabel_name WHERE condition;

Ustaw nazwę kolumny (alias)
Gdy używasz MIN() lub MAX(), zwrócona kolumna nie będzie miała nazwy opisowej. Aby nadać kolumnie nazwę użyj AS.
Przykład:
```
SELECT MIN(Price) AS SmallestPrice
FROM Products;
```
Użyj MIN() z GROUP BY, aby zwrócić najniższą cenę dla każdej kategorii w tabeli Produkty.
```
Przykład:
SELECT MIN(Price) AS SmallestPrice, CategoryID
FROM Products
GROUP BY CategoryID;
```

# 17. SQL COUNT()
Zwraca liczbę wierszy spełniających określone kryteria.
Przykład: Znajdź całkowitą liczbę wierszy w Products tabeli.
```
SELECT COUNT(*)
FROM Products;
```
Składnia:
SELECT COUNT(column_name)
FROM tabel_name
WHERE condition;
Zamiast gwiazdki można podać nazwę kolumny, jeśli podasz nazwę kolumny zamiast *, wartość NULL nie będzie liczona.
Przykład: Znajdź liczbę produktów dla której wartość ProductName jest rózna od NULL>
```
SELECT COUNT(ProductName)
FROM Products;
```
Dodaj klauzulę WHERE aby dodać warunek.
Przykład: Znajdź liczbę produktów, gdzie Price jest większa niż 20.
```
SELECT COUNT(productID)
FROM Products
WHERE Price > 20;
```
