# 1. Wstęp
Uczenie maszynowe polega na tym, że komputer uczy się na podstawie analizy danych i statystyk. Uczenie maszynowe to krok w kierunku sztucznej inteligencji (AI). Uczenie maszynowe to program, który analizuje dane i uczy się przewidywać wyniki.

Od czego zacząć?
W tym samouczku wrócimy do matematyki i zdobędziemy wiedzę na temat statystyki, a także nauczymy się obliczać ważne liczby w oparciu o zbiory danych. Nauczymy się również, jak używać różnych modułów Pythona, aby uzyskać potrzebne nam odpowiedzi. Nauczymy się także, jak tworzyć funkcje, które będą w stanie przewidzieć wynik na podstawie zdobytej wiedzy.

Zbiór danych:
W umyśle komputera zestaw danych to dowolny zbiór danych. Może to być cokolwiek, od tablicy do kompletnej bazy danych.

Przykład tablicy:
```
[99,86,87,88,111,86,103,87,94,78,77,85,86]
```
Patrząc na tablicę, możemy założyć, że średnia wartość wynosi prawdopodobnie około 80 lub 90, a także jesteśmy w stanie określić najwyższą i najniższą wartość, ale co jeszcze możemy zrobić? Patrząc na bazę danych, możemy zauważyć, że najpopularniejszym kolorem jest biały, a najstarszy samochód ma 17 lat, ale co by było, gdybyśmy mogli przewidzieć, czy samochód ma AutoPass, patrząc tylko na inne wartości? D o tego służy Machine Learning! Analizowanie danych i przewidywanie wyników!

W uczeniu maszynowym praca z bardzo dużymi zestawami danych jest powszechna. W tym samouczku postaramy się jak najbardziej ułatwić zrozumienie różnych koncepcji uczenia maszynowego i będziemy pracować z małymi, łatwymi do zrozumienia zestawami danych.

### Typy danych
Aby móc analizować dane, należy wiedzieć, z jakim typem danych mamy do czynienia.

Typy danych możemy podzielić na trzy główne kategorie:

- Liczbowy
- Kategoryczny
- Porządkowy
  
Dane liczbowe to liczby, które można podzielić na dwie kategorie liczbowe:

Dane dyskretne
- zliczane dane, które są ograniczone do liczb całkowitych. Przykład: Liczba przejeżdżających samochodów.
Dane ciągłe
- dane pomiarowe, które mogą być dowolną liczbą. Przykład: cena przedmiotu lub rozmiar przedmiotu
Dane kategoryczne to wartości, których nie można porównywać ze sobą. Przykład: wartość koloru lub dowolne wartości tak/nie.

Dane porządkowe są podobne do danych kategorycznych, ale można je porównywać ze sobą. Przykład: oceny szkolne, w których A jest lepsze od B itd.

Znając typ danych w źródle danych, będziesz w stanie określić, jaką technikę zastosować podczas ich analizy.

Więcej na temat statystyki i analizy danych dowiesz się w kolejnych rozdziałach.
