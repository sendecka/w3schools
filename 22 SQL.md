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
Ignoruj duplikaty stosując DISTINCT w COUNT(). W takim przypadku wiersze o tej samej wartości dla określonej kolumny będą liczone jako jeden wiersz.
Przykład: Ile różnych cen jest w Products?
```
SELECT COUNT(DISTINCT Price)
FROM Products;
```
Użyj aliasu - nadaj nazwę kolumnie, w której przeprowadzisz obliczenia używając AS.
Przykład: Nadaj kolumnie nazwę liczba rrekordów.
```
SELECT COUNT(*) AS [Number of recerds]
FROM Products;
```
Użyj COUNT() z GROUP BY()
Możemy użyć COUNT() z GROUP BY(), aby zwrócić liczbę rekordów dla każdej kategorii w tabeli Produkty.
```
SELECT COUNT (*) AS [Number of products], CategoryID
FROM Products
GROUP BY CategoryID;
```

# 18. SQL SUM()
Zwraca sumę całkowitą kolumny liczbowej.
Przykład: Zwróć sumę wszystkich Quality pól w OrderDetails tabeli.
```
SELECT SUM(Quantity)
FROM OrderDetails;
```
Składnia:
```
SELECT SUM(column_name)
FROM tabel_name
WHERE condition
```
Dodaj klauzulę WHERE określającą warunek.
Przykład: Zwróć sumę pola Quantity dla produktu z ProductsID 11
```
SELECT SUM(Quantity)
FROM OrderDetails
WHERE ProductID = 11;
```
Użyj aliasu aby nadać kolumnie nazwę, używając AS.

SUM() z wyrażeniem - parametr wewnątrz funkcji SUM() może być również wyrażeniem.
Jeżeli przyjmujemy, że każdy produkt w kolumnie OrderDetails kosztuje 10 dolarów, możemy obliczyć całkowity przychód w dolarach, mnożąc każdą wartość przez 10.

Przykład: Urzyj wyrażenia wewnątrz SUM() funkcji.
```
SELECT SUM(Quantity * 10)
FROM Order Details
```

Możemy również połączyć OrderDetails tabelą z Product , aby poznać rzeczywistą kwoę, zamiast zakładać, że jest to 10 dolarów.

Przykład: Połącz OrderDetails z Products i użyj SUM() aby znaleźć kwotę całkowitą. 
```
SELECT SUM(Price * Quantity)
FROM OrderDetails
LEFT JOIN Products ON OrderDetails.ProductsID = Product.ProductID;
```

# 19. SQL AVG() 
Zwraca średnią wartość kolumny liczbowej.

Przykład: Znajdź średnią cenę wszystkich produktów.
```
SELECT AVG(Price)
FROM Products;
```
Wartość NULL są ignorowane.
Dodaj nową klauzulę WHERE określającą warunek.

Przykład: Zwróć średnią cenę produktów w kategorii 1.
```
SELECT AVG(Price)
FROM Products
WHERE CategoryID = 1;
```
Użyj aliasu - nadaj kolumnie AVG nazwę, używając AS słowa kluczowego.

Przykład: Nadaj kolumnie nazwę średnia cena.
```
SELECT AVG(Price) AS [averange price]
FROM Products;
```
Wyższy niż średnia - aby wyświetlić wszystkie rekordy z ceną wyższą od średniej, możemy użyć AVG() funkcji w podzapytaniu.

Przykład: Zwróć wszystkie produkty z ceną wyższą niż średnią.
```
SELECT * FROM Products
WHERE price > (SELECT AVG(price) FROM Products);
```
Użyj AVG() z GROUP BY - aby zwrócić średnią cenę dla każdej kategorii w tabeli Produkty.

Przykład:
```
SELECT AVG(Price) AS AverangePrice, CategoryID
FROM Products
GROUP BY CATEGORYID;
```

# 20. SQL LIKE Operator

Operator LIKE jest używany w WHERE klauzuli w celu wyszukiwania określonego wzorca w kolumnie.

W powiązaniu z operatorem często stosuje się dwa symbole wieloznaczne LIKE:
- znak procentu % oznacza zero, jeden lub wiele znaków.
- znak podkreślenia _ oznacza jeden pojedyńczy znak.

Przykład: Zaznacz wszystkich klientów, których nazwa zaczyna się na literę "a".
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';
```

Składnia: 
```
SELECT column1, column2, ...
FROM tabel_name
WHERE column LIKE pattern;
```

Symbol _ wieloznaczny reprezentuje pojedyńczy znak. Może to być dowolny znak lub cyfra, ale każdy _ reprezentuje jeden i tylko jeden znak.

Przykład: Zwróć wszystkich klientów z miast, którego nazwa zaczyna się od 'L', po którym następuje jeden symbol wieloznaczny, następnie 'nd' i dwa symbole wieloznaczne. 
```
SELECT * FROM Customers
WHERE city LIKE 'L_nd_';
```
Symbol % wieloznaczny może zawierać dowolną liczbę znaków, nawet zero znaków.
Przykład: Zwróć wszystkich klientów z miasta zawierającego literę 'L'
```
SELECT * FROM CUstomers
WHERE City LIKE '%L%';
```
Aby zwrócić rekordy zaczynające się od określonej liczby lub frz należy dodać % na końcu litery lub frazy.
Przykład: Zwróć wszystkich klientów, których nazwa zaczyna się od 'La', 
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'La%';
```
Możesz również łączyć dowolną liczbę warunków za pomocą operatorów AND lub OR.
Przykład: Zwróć wszystkich klientów, których nazwa zaczyna się od 'a' lub zaczyna się od 'b'
```
SELECT * FROM Customers
WHERE CUstomerName LIKE 'a%' OR CustomerName LIKE 'b%';
```
Aby zwrócić rekordy kończące się na określoną literę lub frazę, należy dodać % na początku litery lub frazy.
Przykład: Zwróć wszystkich klientów, których nazwa kończy się na 'a'
```
SELECT * FROM Customers
WHERE CUstomerName LIKE '%a';
```
Możesz również łączyć "zaczyna się na' i 'kończy się na'.
Przykład: Zwróć wszystkich klientów, których nazwiska zaczynają się na 'b' i kończą na 's'.
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'b%s';
```

Aby zwrócić rekordy zawierające określoną literę lub frazę, należy dodać % zarówno przed jak i po literze lub frazie.
Przykład: Zwróć wszystkich klientów zawierających frazę 'lub'
```
SELECT * FROM Customers
WHERE CustomerName LIKE '%or%';
```
Połącz symbole wieloznaczne - każdy symbol wieloznaczny toki jak % lub _ może być używany w połączeniu z innymi symbolami wieloznacznymi.
Przykład: Zwróć wszystkich klientów, których nazwa zaczyna się od 'a' i ma co najmniej 3 znaki długości.
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a_%';
```
Jeśli nie określono symbolu wieloznacznego fraza musi być dokładnie dopasowana, aby zwrócić wynik.
Przykład: Zwróć wszystkich klientów z Hiszpanii.
```
SELECT * FROM Customers
WHERE Country LIKE 'Spain';
```

# 21. SQL Symbole wieloznaczne - służą do zastąpienia jednego lub więcej zanków w ciągu. Znaki wieloznaczne są używane z operatorami. Operator jest używany w klauzuli w celu wyszukania określonego wzorca w kolumnie LIKE WHERE.
Przykład: Zwróć wszystkich klientów, których nazwisko zaczyna się na literę 'a'.
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';
```

Znaki wieloznaczne:
- % reprezentuje zero lub więcej znaków,
- _ Reprezentuje pojedyńczy znak
- [] Reprezentuje wolny pojedyńczy znak w nawiasach,
- ^ Reprezentuje dowolny znak nie znajdujący się w nawiasach,
- - Reprezentuje dowolny pojedyńczy znak w określonym zbiorze,
- {} Reprezentuje dowolny znak ucieczki.

Korzystanie z symbolu wieloznacznego % - może on zawierać dowolną ilość znaków.

Przykład: Zwróć wszystkich klientów, których nazwa kończy się na 'es'.
```
SELECT * FROM Customers
WHERE CustomerName LIKE '%es';
```
Korzystanie z symbolu wieloznacznego _ reprezentuje on pojedyńczy znak. Może to być dowolny znak lub cyfra. Każdy _ reprezentuje jeden i tylko jeden znak.

Przykład: Zwróć wszystkich klientów zaczynających "City' od dowolnego znaku, po którym następuje 'ondon'.
```
SELECT * FROM Customers
WHERE City LIKE '_ondon';
```
Używanie symbolu wieloznacznego [] zwraca on wynik jeśli którykolwiek ze znaków wewnątrz niego zostanie dopasowany.
Przykład: Zwróć wszystkich klientów zaczynających sięna 'b', 's', 'p'.
```
SELECT * FROM Customers
WHERE CustomerName LIKE '[bsp]%';
```
Korzystanie z symbolu wieloznacznego _, umożliwia on określenie zakresu znaków wewnątrz [].
Przykład: Zwróć wszystkich klientów zaczynających się na litery 'a', 'b', 'c', 'd', 'e' lub 'f'.
```
SELECT * FROM Customers
WHERE CustomerName LIKE '[a-f]%;
```
Połącz symbole wieloznaczne - każdy symbol wieloznaczny, może być używany z innymi symbolami wieloznacznymi.
Przykład: Zwróć wszystkich klientów, których nazwa zaczyna się od 'a' i ma co najmniej 3 znaki długości.
```
SELECT * FROM Customers
WHERE CustomerName LIKE 'a___%';
```
Bez symbolu wieloznacznego - fraza musi mieć dokładnie dopasowanie aby zwrócić wynik.
Przykład: Zwróć dla wszystkich klientów z Hiszpanii
```
SELECT * FROM Customers
WHERE Country LIKE 'Spain';
```

# 22. SQL IN operator 
Umożliwia określenie wielu wartości w WHERE. Operator IN jest skrótem oznaczającym wiele OR warunków.

Przykład: Zwróć wszystkich klientów z 'Niemiec', 'Francji', 'UK'
```
SELECT * FROM Customers
WHERE Country IN ('Germany', France', 'UK');
```

Składnia:
```
SELECT column_name(s)
FROM tabel_name
WHERE column_name IN (value1, value2..)
```
NOT IN - zwróci wszystkie rekordy które nie są żadną z wartości na liście.

Przykład: Zwróć wszystkich klientów, którzy nie pochodzą z 'Niemiec', 'Francji', 'UK'
```
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

IN (SELECT) - można również używać IN z zapytaniem w WHERE klauzuli. Za pomocą zapytania można zwrócić wszystkie rekordy z zapytania głównego, które znajdują się w wyniku pod zapytaniem.

Przykład: Zwróć wszystkich klientów, którzy mają zamówienie w tabeli zamówienia.
```
SELECT * FROM Customers
WHERE CustomerID IN (SELECT CustomerID FROM Orders);
```

# 23. SQL BETWEEN
- Wybiera wartości w danym zakresie. Wartości mogą być liczbami, tekstem lub datami,
- Jest inkluzywny uwzględnia wartość początkową i końcową.

Przykład: Wybierz wszystkie produkty o cenie od 10 do 20.
```
SELECT * FRMO Products
WHERE Price BETWEEN 10 AND 20;
```

Składnia:
```
SELECT column_name
FROM tabel_name
WHERE column_name BETWEEN value1, AND value2
```

NOT BETWEEN - aby wyświetlić produktty spoza zakresu podanego w poprzednim przykładzie, użyj NOT BETWEEN.

Przykład: Pokaż produkty które nie są pomiędzy 10 i 20.
```
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

BETWEEn z IN - wybiera wszystkie produkty o cenie pomiędzy 10 a 20. Ponadto CategoryID musi wynosić 1,2 lub 3.

Przykład:
```
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID IN (1,2,3);
```
BETWEEN z wartościami tekstowymi

Przykład: Wybierz wszystkie produkty o nazwie ProductName w kolejności alfabetycznej pomiędzy Carnavvon Tigiers i Mozzarella di Giovanni.
```
SELECT * FROM Products
WHERE ProductName BETWEEN 'Carnavvon Tigiers' AND 'Mozzarella di Giovorni'
ORDER BY ProductName;
```

BETWEEN z datami
Przytkład: Wybierz wszystkie zamówienia z datą pomiędzy 01. lipca 1996, a 31 lipca 1996
```
SELECT * FROM Orders
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
```

# 24. SQL Aliasy
- Aliasy służą do nadawania tabeli lub kolumnie tymczasowej nazwy
- Aliasy sączęsto używane w celu zwiększenia czytelności nazw kolumn
- Aliasy istnieją tylko przez czas trwania danego zapytania
- Aliasy tworzy sięza pomocą słowa kluczowego AS.

Przykład:
```
SELECT CustomerID AS ID
FROM Customers;
```
AS jest opcjonalne, można go pominąć i uzyska się ten sam wynik.

Składnia: gdy alias jest używany w kolumnie
```
SELECT column_name AS alias_name
FROM tabel_name
```

Składnia: gdy alias jest używany w tabeli
```
SELECT column_name
FROM tabel_name AS alias_name;
```

Alias dla kilku kolumn - można stworzyć dwa aliasy, jeden dla kolumny CustomerID i jeden dla kolumny CustomerName.
Przykład:
```
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```
Używanie Aliasów ze znakiem spacji - jeśli chcesz aby Twój alias zawierał jedną lub więcej spacji np. 'my great products', umieść go w nawiasach kwadratowych lub cudzysłowach.

Przykład:
```
SELECT ProductName AS [My Great Products]
FROM Products;
```
Połącz kolumny - poniższy zapis tworzy alias o nazwie 'Adres', który łączy cztery kolumny (Adres, kod pocztowy, Miasto, Kraj)

Przykład:
```
SELECT CustomerName, Address +', '+ PostalCode +' '+ City +' '+ Country'
AS Address
FROM Customers;
```
Alias dla tabel - te same zasady obowiązują, gdy chcesz użyć aliasu dla tabel.

Przykład: Zamiast tego odnoś się do tabeli klienci jako do Osób
```
SELECT * FROM Customers AS Person;
```
Aliasy mogą być przydatne gdy:
- W zapytaniu bierze udział więcej niż jedna tabela
- funkcje sąużywane w zapytaniu
- nazwy kolumn są duże lub moło czytelne
- łączy się dwie lub więcej kolumn

# 25. SQL JOINS
Klauzula JOINS służy do łączenia wierszy z dwóch lub więcej tabeli na podstawie powiązanej między nimi kolumny.
Polecenie INNER JOIN - wybiera rekordy mające pasujące wartości w obu tabelach.
Przykład: 
```
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```
Różne typy połączeń SQL JOIN:
- (INNER) JOIN: Zwraca rekordy, które mają posujące wartości w obu tabelacz,
- LEFT (OUTER) JOIN: zwraca wszystkie rekordy z lewej tabeli i dopasowywuje rekordy z prawej,
- RIGHT (OUTER) JOIN: zwraca wszystkie rekordy z prawej tabeli i dopasowywuje rekordy z lewej,
- FULL (OUTER) JOIN: Zwraca wszystkie rekordy, jeśli istnieje dopasowanie w lewej lub prawej tabeli,

# 26. SQL INNER JOIN
Wybiera rekordy, które mają pasujące wartości w obu tabelach.
Przykład: Połącz produkty i kategorie
```
SELECT ProductID, ProductName, CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID
```
INNER JOIN zwraca tylko wiersze z dopasowaniem w obu tabelach. Oznacza to, że jeśli masz produkty bez CategoryID lub z CategoryID którego nie ma w tabeli Categories, ten rekord nie zostanie zwrócony w wyniku.

Składnia: 
```
SELECT column_name(s)
FROM tabel1
INNER JOIN tabel2
On table1.column_name = tabel2.column_name
```
Nadawanie nazw kolumnom - dobrą praktyką jest uwzgędnienie nazwy tabeli podczas określania kolumn w poleceniu SQL.
Przykład:
```
SELECT Products.ProductsID, Products.ProductsName, Categories.CategoryID;
FROM Products
INNER JOIN Categories ON Products.CategoriesID = Categories.CategoryID;
```
Powyższy przykład działa bez określania nazw tabeli, ponieważ żadna z określonych nazw kolumn, nie występuje w obu tabelach. Jeżeli spróbujesz uwzględnić CategoryID w SELECT poleceniu, otrzymasz błąd jeśli nie określisz nazwy tabeli (ponieważ CategoryID występuje w obu tabelach)

JOIN : INNER JOIN zwróci ten sam wynik. INNER jest domyślnym typem łączenia dla JOIN więc gdy piszesz JOIN fraza ta faktycznie zapisuje INNER JOIN.

Przykład: JOIN jest tym samym co INNER JOIN:
```
SELECT Products.ProductsID, Products.ProductsName, Categories.CategoryName
FROM Products
JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

JOIN three tables - poniższe polecenie SQL wybiera wszystnie zamówienia zawierające informacje o klientach i spedytorze.
Przykład: 
```
SELECT Orders.OrderID, CustomersCustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShippersID = Shippers.ShippersID);
```




