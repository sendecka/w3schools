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

# 2. Machine Learning - Mean Median Mode
Czego możemy się dowiedzieć, analizując grupę liczb?

W uczeniu maszynowym (i w matematyce) często interesują nas trzy wartości:

- Średnia - wartość średnia
- Mediana – wartość środkowa
- Moda - najczęstsza wartość

Przykład: Zarejestrowaliśmy prędkość 13 samochodów:
```
speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]
```
Jaka jest średnia, średnia lub najczęściej występująca wartość prędkości?

Wartość średnia jest wartością przeciętną.

Aby obliczyć średnią, należy obliczyć sumę wszystkich wartości i podzielić sumę przez liczbę wartości:
```
(99+86+87+88+111+86+103+87+94+78+77+85+86) / 13 = 89.77
```
Moduł NumPy ma na to metodę. Dowiedz się więcej o module NumPy w naszym NumPy Tutorial .

PrzykładZdobądź własny serwer Python
Użyj metody NumPy, mean()aby znaleźć średnią prędkość:
```
import numpy

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = numpy.mean(speed)

print(x)
```
Mediana
Wartość medianowa to wartość znajdująca się w środku, po posortowaniu wszystkich wartości:
```
77, 78, 85, 86, 86, 86, 87, 87, 88, 94, 99, 103, 111
```
Ważne jest, aby posortować liczby przed znalezieniem mediany.

Moduł NumPy ma metodę na to:

Przykład:

Użyj metody NumPy, median()aby znaleźć wartość środkową:
```
import numpy

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = numpy.median(speed)

print(x)
```
Tryb
Wartość mody to wartość, która pojawia się najwięcej razy:
```
99, 86, 87, 88, 111, 86, 103, 87, 94, 78, 77, 85, 86 = 86
```
Moduł SciPy ma na to metodę. Dowiedz się więcej o module SciPy w naszym samouczku SciPy .

Przykład
Za pomocą metody SciPy mode()znajdź liczbę, która pojawia się najczęściej:
```
from scipy import stats

speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]

x = stats.mode(speed)

print(x)
```
Podsumowanie rozdziału
Średnia, mediana i moda to techniki często stosowane w uczeniu maszynowym, dlatego ważne jest zrozumienie koncepcji, na których się opierają.
