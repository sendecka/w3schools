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

#. 3 Machine Learning - Standard Deviation
Czym jest odchylenie standardowe?
Odchylenie standardowe to liczba opisująca rozrzut wartości.

Niskie odchylenie standardowe oznacza, że ​​większość liczb jest bliska wartości średniej.

Duże odchylenie standardowe oznacza, że ​​wartości rozłożone są w szerszym zakresie.

Przykład: Tym razem zarejestrowaliśmy prędkość 7 samochodów:
```
speed = [86,87,88,86,87,85,86]
```
Odchylenie standardowe wynosi:
```
0.9
```
Oznacza to, że większość wartości mieści się w przedziale 0,9 od wartości średniej wynoszącej 86,4.

Zróbmy to samo z wyborem liczb o szerszym zakresie:
```
speed = [32,111,138,28,59,77,97]
```
Odchylenie standardowe wynosi:
```
37.85
```
Oznacza to, że większość wartości mieści się w przedziale 37,85 od wartości średniej, która wynosi 77,4.

Jak widać, większe odchylenie standardowe oznacza, że ​​wartości są rozłożone w szerszym zakresie.

Moduł NumPy posiada metodę obliczania odchylenia standardowego:

Przykład: Użyj metody NumPy, std()aby znaleźć odchylenie standardowe:
```
import numpy

speed = [86,87,88,86,87,85,86]

x = numpy.std(speed)

print(x)
```
```
import numpy

speed = [32,111,138,28,59,77,97]

x = numpy.std(speed)

print(x)
```
Zmienność
Wariancja to kolejna liczba wskazująca, jak bardzo rozproszone są wartości.

W rzeczywistości, jeśli wyciągniesz pierwiastek kwadratowy z wariancji, otrzymasz odchylenie standardowe!

Albo odwrotnie – jeśli pomnożysz odchylenie standardowe przez siebie, otrzymasz wariancję!

Aby obliczyć wariancję należy wykonać następujące czynności:

1. Znajdź średnią:
```
(32+111+138+28+59+77+97) / 7 = 77.4
```
2. Dla każdej wartości: znajdź różnicę od średniej:
```
 32 - 77.4 = -45.4
111 - 77.4 =  33.6
138 - 77.4 =  60.6
 28 - 77.4 = -49.4
 59 - 77.4 = -18.4
 77 - 77.4 = - 0.4
 97 - 77.4 =  19.6
```
3. Dla każdej różnicy: znajdź wartość kwadratu:
```
(-45.4)2 = 2061.16
 (33.6)2 = 1128.96
 (60.6)2 = 3672.36
(-49.4)2 = 2440.36
(-18.4)2 =  338.56
(- 0.4)2 =    0.16
 (19.6)2 =  384.16
```
4. Wariancja jest średnią liczbą kwadratów tych różnic:
```
(2061.16+1128.96+3672.36+2440.36+338.56+0.16+384.16) / 7 = 1432.2
```
Na szczęście NumPy posiada metodę obliczania wariancji:

Przykład
Użyj metody NumPy, var()aby znaleźć wariancję:
```
import numpy

speed = [32,111,138,28,59,77,97]

x = numpy.var(speed)

print(x)
```
Odchylenie standardowe
Jak się dowiedzieliśmy, wzór na odchylenie standardowe to pierwiastek kwadratowy wariancji:
```
√1432.25 = 37.85
```
Lub, jak w przykładzie powyżej, użyj NumPy do obliczenia odchylenia standardowego:

Przykład
Użyj metody NumPy, std()aby znaleźć odchylenie standardowe:
```
import numpy

speed = [32,111,138,28,59,77,97]

x = numpy.std(speed)

print(x)
```
Symbolika

Odchylenie standardowe jest często oznaczane symbolem Sigma: σ

Wariancję często oznacza się symbolem sigma squared: σ 2

Podsumowanie rozdziału
Odchylenie standardowe i wariancja to terminy często używane w uczeniu maszynowym, dlatego ważne jest, aby zrozumieć, jak je uzyskać, a także jaka jest koncepcja, która się za nimi kryje.

# 4. Machine Learning - Percentiles
Czym są percentyle?
Percentyle są stosowane w statystyce w celu przedstawienia wartości, od której dany procent wartości jest niższy.

Przykład: Załóżmy, że mamy tablicę zawierającą wiek wszystkich osób mieszkających na danej ulicy.
```
ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]
```
Jaki jest 75. percentyl? Odpowiedź to 43, co oznacza, że ​​75% ludzi ma 43 lata lub mniej.

Moduł NumPy ma metodę znajdowania określonego percentyla:
Przykład:
Użyj metody NumPy, percentile()aby znaleźć percentyle:
```
import numpy

ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]

x = numpy.percentile(ages, 75)

print(x)

```
Przykład
W jakim wieku jest 90% ludzi?
```
import numpy

ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]

x = numpy.percentile(ages, 90)

print(x)
```

# 5. Machine Learning - Data Distribution

Dystrybucja danych
Na początku tego samouczka pracowaliśmy w naszych przykładach na bardzo małej ilości danych, aby zrozumieć różne koncepcje.

W świecie rzeczywistym zbiory danych są o wiele większe, ale zebranie rzeczywistych danych może być trudne, przynajmniej na wczesnym etapie projektu.

Jak możemy uzyskać duże zbiory danych?
Aby utworzyć duże zbiory danych na potrzeby testów, korzystamy z modułu Pythona o nazwie NumPy, który udostępnia szereg metod umożliwiających tworzenie losowych zbiorów danych dowolnej wielkości.

Przykład:
Utwórz tablicę zawierającą 250 losowych liczb zmiennoprzecinkowych pomiędzy 0 i 5:
```
import numpy

x = numpy.random.uniform(0.0, 5.0, 250)

print(x)
```
Histogram
Aby zwizualizować zbiór danych, możemy narysować histogram zawierający zebrane dane.

Do narysowania histogramu wykorzystamy moduł Pythona Matplotlib.

Dowiedz się więcej o module Matplotlib w naszym samouczku Matplotlib .

Przykład
Narysuj histogram:
```
import numpy
import matplotlib.pyplot as plt

x = numpy.random.uniform(0.0, 5.0, 250)

plt.hist(x, 5)
plt.show()
```
Wyjaśnienie histogramu
Używamy tablicy z powyższego przykładu, aby narysować histogram z 5 słupkami.

Pierwszy pasek przedstawia liczbę wartości w tablicy mieszczących się w przedziale od 0 do 1.

Drugi pasek przedstawia liczbę wartości pomiędzy 1 i 2.

Itp.

Co daje nam taki wynik:

- 52 wartości mieszczą się w przedziale od 0 do 1
- 48 wartości mieści się w przedziale od 1 do 2
- 49 wartości mieści się pomiędzy 2 a 3
- 51 wartości mieści się w przedziale od 3 do 4
- 50 wartości mieści się w przedziale od 4 do 5

Uwaga: Wartości tablicy są liczbami losowymi i nie pokażą dokładnie tego samego wyniku na Twoim komputerze.

Dystrybucje Big Data
Tablica zawierająca 250 wartości nie jest uważana za bardzo dużą, ale teraz wiesz, jak utworzyć losowy zestaw wartości, a zmieniając parametry, możesz utworzyć zestaw danych tak duży, jak chcesz.

Przykład: Utwórz tablicę zawierającą 100000 liczb losowych i wyświetl je za pomocą histogramu ze 100 słupkami:
```
import numpy
import matplotlib.pyplot as plt

x = numpy.random.uniform(0.0, 5.0, 100000)

plt.hist(x, 100)
plt.show()
```

# 6. Machine Learning - Normal Data Distribution
Normalny rozkład danych
W poprzednim rozdziale dowiedzieliśmy się, jak utworzyć całkowicie losową tablicę o zadanym rozmiarze i zawierającą dwie zadane wartości.

W tym rozdziale nauczymy się, jak utworzyć tablicę, w której wartości będą skoncentrowane wokół danej wartości.

W teorii prawdopodobieństwa ten rodzaj rozkładu danych nazywany jest normalnym rozkładem danych lub rozkładem danych Gaussa , na cześć matematyka Carla Friedricha Gaussa, który opracował wzór tego rozkładu danych.

Przykład:
Typowy rozkład normalny danych:
```
import numpy
import matplotlib.pyplot as plt

x = numpy.random.normal(5.0, 1.0, 100000)

plt.hist(x, 100)
plt.show()
```

Uwaga: Wykres rozkładu normalnego nazywany jest także krzywą dzwonową ze względu na charakterystyczny kształt dzwonu.

Wyjaśnienie histogramu
Używamy tablicy z numpy.random.normal() metody zawierającej 100000 wartości, aby narysować histogram ze 100 słupkami.

Określamy, że średnia wartość wynosi 5,0, a odchylenie standardowe wynosi 1,0.

Oznacza to, że wartości powinny koncentrować się wokół wartości 5,0 i rzadko odbiegać od średniej bardziej niż o 1,0.

Jak widać na histogramie, większość wartości mieści się w przedziale od 4,0 do 6,0, przy czym najwyższa wartość wynosi około 5,0.

# 7. Machine Learning - Scatter Plot
Wykres punktowy
Wykres punktowy to diagram, na którym każda wartość w zestawie danych jest reprezentowana przez kropkę.
Moduł Matplotlib ma metodę rysowania wykresów punktowych. Wymaga dwóch tablic o tej samej długości: jednej dla wartości osi x i jednej dla wartości osi y:
```
x = [5,7,8,7,2,17,2,9,4,11,12,9,6]

y = [99,86,87,88,111,86,103,87,94,78,77,85,86]
```
Tablica xreprezentuje wiek każdego samochodu.

Tablica yprzedstawia prędkość każdego samochodu.

Przykład:
Użyj poniższej scatter()metody, aby narysować diagram punktowy:
```
import matplotlib.pyplot as plt

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

plt.scatter(x, y)
plt.show()
```
Wyjaśnienie wykresu punktowego
Oś x przedstawia wiek, a oś y przedstawia prędkość.

Z diagramu możemy wyczytać, że dwa najszybsze samochody miały 2 lata, a najwolniejszy miał 12 lat.

Uwaga: Wygląda na to, że im nowszy samochód, tym szybciej jeździ, ale to może być przypadek, wszak zarejestrowaliśmy tylko 13 samochodów.

Losowe rozkłady danych
W uczeniu maszynowym zbiory danych mogą zawierać tysiące, a nawet miliony wartości.

Podczas testowania algorytmu może się zdarzyć, że nie będziesz mieć dostępu do rzeczywistych danych i będziesz musiał użyć losowo wygenerowanych wartości.

Jak dowiedzieliśmy się w poprzednim rozdziale, moduł NumPy może nam w tym pomóc!

Utwórzmy dwie tablice wypełnione po 1000 liczb losowych z rozkładu normalnego.

Pierwsza tablica będzie miała średnią ustawioną na 5,0 i odchylenie standardowe wynoszące 1,0.

Druga tablica będzie miała średnią ustawioną na 10,0 i odchylenie standardowe wynoszące 2,0:

Przykład:
Wykres punktowy z 1000 punktów:
```
import numpy
import matplotlib.pyplot as plt

x = numpy.random.normal(5.0, 1.0, 1000)
y = numpy.random.normal(10.0, 2.0, 1000)

plt.scatter(x, y)
plt.show()
```

Wyjaśnienie wykresu punktowego
Widzimy, że kropki koncentrują się wokół wartości 5 na osi x i 10 na osi y.

Możemy również zauważyć, że rozrzut jest większy na osi Y niż na osi X.
