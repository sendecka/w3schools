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

