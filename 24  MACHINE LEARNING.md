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

# 8. Machine Learning - Linear Regression
Regresja
Termin regresja jest używany, gdy próbujesz znaleźć związek pomiędzy zmiennymi.

W uczeniu maszynowym i modelowaniu statystycznym zależność ta jest wykorzystywana do przewidywania wyników przyszłych zdarzeń.

Regresja liniowa
Regresja liniowa wykorzystuje relacje pomiędzy punktami danych, aby poprowadzić linię prostą przechodzącą przez wszystkie punkty.

Za pomocą tego wiersza można przewidywać przyszłe wartości.
W uczeniu maszynowym przewidywanie przyszłości jest bardzo istotne.

Jak to działa?
Python ma metody znajdowania relacji między punktami danych i rysowania linii regresji liniowej. Pokażemy Ci, jak używać tych metod zamiast przechodzić przez wzór matematyczny.

W poniższym przykładzie oś x przedstawia wiek, a oś y przedstawia prędkość. Zarejestrowaliśmy wiek i prędkość 13 samochodów, gdy mijały bramkę poboru opłat. Sprawdźmy, czy zebrane dane można wykorzystać w regresji liniowej:
Przykład:

Zacznij od narysowania wykresu punktowego:
```
import matplotlib.pyplot as plt

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

plt.scatter(x, y)
plt.show()
```
Przykład
Zaimportuj scipyi narysuj linię regresji liniowej:
```
import matplotlib.pyplot as plt
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()
```
Przykład wyjaśniony
Zaimportuj potrzebne moduły.

Więcej informacji na temat modułu Matplotlib znajdziesz w naszym samouczku Matplotlib .

Więcej informacji na temat modułu SciPy znajdziesz w naszym samouczku SciPy .
```
import matplotlib.pyplot as plt
from scipy import stats
```
Utwórz tablice reprezentujące wartości osi x i y:
```
x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]
```
Wykonaj metodę zwracającą pewne ważne wartości kluczowe regresji liniowej:
```
slope, intercept, r, p, std_err = stats.linregress(x, y)
```
Utwórz funkcję, która używa wartości slopei interceptdo zwracania nowej wartości. Ta nowa wartość reprezentuje miejsce na osi y, w którym zostanie umieszczona odpowiadająca jej wartość x:
```
def myfunc(x):
  return slope * x + intercept
```
Przeprowadź każdą wartość tablicy x przez funkcję. Spowoduje to utworzenie nowej tablicy z nowymi wartościami dla osi y:
```
mymodel = list(map(myfunc, x))
```
Narysuj oryginalny wykres punktowy:
```
plt.scatter(x, y)
```
Narysuj linię regresji liniowej:
```
plt.plot(x, mymodel)
```
Wyświetl diagram:
```
plt.show()
```
R jak związek
Ważne jest, aby znać zależność pomiędzy wartościami na osi x i wartościami na osi y, ponieważ jeśli nie ma zależności, regresji liniowej nie można użyć do przewidywania czegokolwiek.

Tę zależność, zwaną współczynnikiem korelacji, nazywamy r.

Wartości rmieszczą się w przedziale od -1 do 1, gdzie 0 oznacza brak związku, a 1 (i -1) oznaczają 100% związku.

Python i moduł Scipy obliczą tę wartość za Ciebie, jedyne co musisz zrobić to podać wartości x i y.

Przykład
Jak dobrze moje dane pasują do regresji liniowej?
```
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

print(r)
```
Uwaga: Wynik -0,76 pokazuje, że istnieje związek, nie jest on idealny, ale wskazuje, że w przyszłych przewidywaniach możemy zastosować regresję liniową.

Przewidywanie przyszłych wartości
Teraz możemy wykorzystać zebrane informacje do przewidywania przyszłych wartości.

Przykład: Spróbujmy przewidzieć prędkość 10-letniego samochodu.

Aby to zrobić, potrzebujemy tej samej myfunc()funkcji, co w przykładzie powyżej:
```
def myfunc(x):
  return slope * x + intercept
```
Przykład
Przewiduj prędkość 10-letniego samochodu:
```
from scipy import stats

x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
y = [99,86,87,88,111,86,103,87,94,78,77,85,86]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

speed = myfunc(10)

print(speed)
```
Źle dopasowane?
Stwórzmy przykład, w którym regresja liniowa nie będzie najlepszą metodą przewidywania przyszłych wartości.

Przykład
Te wartości dla osi x i y powinny skutkować bardzo złym dopasowaniem do regresji liniowej:
```
import matplotlib.pyplot as plt
from scipy import stats

x = [89,43,36,36,95,10,66,34,38,20,26,29,48,64,6,5,36,66,72,40]
y = [21,46,3,35,67,95,53,72,58,10,26,34,90,33,38,20,56,2,47,15]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
  return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.show()
```
A co rz związkiem?

Przykład
Powinieneś otrzymać bardzo niską rwartość.
```
import numpy
from scipy import stats

x = [89,43,36,36,95,10,66,34,38,20,26,29,48,64,6,5,36,66,72,40]
y = [21,46,3,35,67,95,53,72,58,10,26,34,90,33,38,20,56,2,47,15]

slope, intercept, r, p, std_err = stats.linregress(x, y)

print(r)
```
Wynik: 0,013 wskazuje na bardzo złą zależność i mówi nam, że ten zestaw danych nie nadaje się do regresji liniowej.

# 9. Machine Learning - Polynomial Regression
Regresja wielomianowa
Jeśli Twoje punkty danych wyraźnie nie pasują do regresji liniowej (linia prosta przechodząca przez wszystkie punkty danych), mogą okazać się idealnym rozwiązaniem w przypadku regresji wielomianowej.

Regresja wielomianowa, podobnie jak regresja liniowa, wykorzystuje związek między zmiennymi x i y, aby znaleźć najlepszy sposób na przeprowadzenie linii przez punkty danych.

Jak to działa?
Python ma metody znajdowania relacji między punktami danych i rysowania linii regresji wielomianowej. Pokażemy Ci, jak używać tych metod zamiast przechodzić przez wzór matematyczny.

W poniższym przykładzie zarejestrowaliśmy 18 samochodów przejeżdżających przez określoną bramkę poboru opłat.

Zarejestrowaliśmy prędkość samochodu oraz porę dnia (godzinę), w której nastąpiło wyprzedzanie.

Oś x przedstawia godziny dnia, a oś y przedstawia prędkość:
Przykład:
Zacznij od narysowania wykresu punktowego:
```
import matplotlib.pyplot as plt

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

plt.scatter(x, y)
plt.show()
```
Przykład
Zaimportuj numpyi matplotlibnarysuj linię regresji wielomianowej:
```
import numpy
import matplotlib.pyplot as plt

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

myline = numpy.linspace(1, 22, 100)

plt.scatter(x, y)
plt.plot(myline, mymodel(myline))
plt.show()
```
Przykład wyjaśniony
Zaimportuj potrzebne moduły.

Więcej informacji na temat modułu NumPy znajdziesz w naszym samouczku NumPy .

Więcej informacji na temat modułu SciPy znajdziesz w naszym samouczku SciPy .
```
import numpy
import matplotlib.pyplot as plt
```
Utwórz tablice reprezentujące wartości osi x i y:
```
x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]
```
NumPy ma metodę umożliwiającą utworzenie modelu wielomianowego:
```
mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))
```
Następnie określ, jak będzie wyświetlana linia. Zaczynamy od pozycji 1 i kończymy na pozycji 22:
```
myline = numpy.linspace(1, 22, 100)
```
Narysuj oryginalny wykres punktowy:
```
plt.scatter(x, y)
```
Narysuj linię regresji wielomianowej:
```
plt.plot(myline, mymodel(myline))
```
Wyświetl diagram:
```
plt.show()
```
R-kwadrat
Ważne jest, aby wiedzieć, jak silna jest zależność pomiędzy wartościami osi x i y, ponieważ jeśli nie ma takiej zależności, regresji wielomianowej nie można wykorzystać do przewidywania czegokolwiek.

Miarą tego związku jest wartość zwana r-kwadrat.

Wartość r-kwadrat przyjmuje wartości od 0 do 1, gdzie 0 oznacza brak związku, a 1 oznacza 100% związku.

Python i moduł Sklearn obliczą tę wartość za Ciebie, jedyne co musisz zrobić to wprowadzić tablice x i y:

Przykład
Jak dobrze moje dane pasują do regresji wielomianowej?
```
import numpy
from sklearn.metrics import r2_score

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

print(r2_score(y, mymodel(x)))
```
Uwaga: Wynik 0,94 pokazuje, że istnieje bardzo dobra zależność i że w przyszłych przewidywaniach możemy stosować regresję wielomianową.

Przewidywanie przyszłych wartości
Teraz możemy wykorzystać zebrane informacje do przewidywania przyszłych wartości.

Przykład: Spróbujmy przewidzieć prędkość samochodu, który przejeżdża obok punktu poboru opłat około godziny 17:00:

Aby to zrobić, potrzebujemy tej samej mymodeltablicy, co w przykładzie powyżej:
```
mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))
```
Przykład
Przewiduj prędkość samochodu przejeżdżającego o godzinie 17:00:
```
import numpy
from sklearn.metrics import r2_score

x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

speed = mymodel(17)
print(speed)
```
W przykładzie przewidziano prędkość 88,87, co mogliśmy również odczytać z diagramu:

Źle dopasowane?
Stwórzmy przykład, w którym regresja wielomianowa nie będzie najlepszą metodą przewidywania przyszłych wartości.

Przykład
Te wartości dla osi x i y powinny skutkować bardzo złym dopasowaniem do regresji wielomianowej:
```
import numpy
import matplotlib.pyplot as plt

x = [89,43,36,36,95,10,66,34,38,20,26,29,48,64,6,5,36,66,72,40]
y = [21,46,3,35,67,95,53,72,58,10,26,34,90,33,38,20,56,2,47,15]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

myline = numpy.linspace(2, 95, 100)

plt.scatter(x, y)
plt.plot(myline, mymodel(myline))
plt.show()
```
A wartość r-kwadrat?

Przykład
Powinieneś otrzymać bardzo niską wartość r-kwadrat.
```
import numpy
from sklearn.metrics import r2_score

x = [89,43,36,36,95,10,66,34,38,20,26,29,48,64,6,5,36,66,72,40]
y = [21,46,3,35,67,95,53,72,58,10,26,34,90,33,38,20,56,2,47,15]

mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))

print(r2_score(y, mymodel(x)))
```
Wynik: 0,00995 wskazuje na bardzo złą zależność i mówi nam, że ten zestaw danych nie nadaje się do regresji wielomianowej.

# 10. Machine Learning - Multiple Regression
Multiple Regression
Regresja wielokrotna
Regresja wieloraka jest podobna do regresji liniowej , ale posiada więcej niż jedną niezależną wartość, co oznacza, że ​​staramy się przewidzieć wartość na podstawie dwóch lub więcej zmiennych.

Jak to działa?
W Pythonie mamy moduły, które wykonają pracę za nas. Zacznij od zaimportowania modułu Pandas.
```
import pandas
```
Dowiedz się więcej o module Pandas w naszym samouczku Pandas .

Moduł Pandas umożliwia odczyt plików csv i zwracanie obiektu DataFrame.

Plik jest przeznaczony wyłącznie do celów testowych, można go pobrać stąd: data.csv
```
df = pandas.read_csv("data.csv")
```
Następnie utwórz listę niezależnych wartości i nazwij tę zmienną X.

Umieść wartości zależne w zmiennej o nazwie y.
```
X = df[['Weight', 'Volume']]
y = df['CO2']
```
Wskazówka: Nazwę listy wartości niezależnych określa się wielką literą X, a listę wartości zależnych małą literą y.

Wykorzystamy niektóre metody z modułu sklearn, dlatego będziemy musieli zaimportować również ten moduł:

from sklearn import linear_model

Z modułu sklearn wykorzystamy LinearRegression()metodę służącą do utworzenia obiektu regresji liniowej.

Ten obiekt ma metodę o nazwie fit(), która przyjmuje wartości niezależne i zależne jako parametry i wypełnia obiekt regresji danymi opisującymi relację:
```
regr = linear_model.LinearRegression()
regr.fit(X, y)
```
Teraz mamy obiekt regresji, który jest gotowy do przewidywania wartości CO2 na podstawie masy i objętości samochodu:
```
#predict the CO2 emission of a car where the weight is 2300kg, and the volume is 1300cm3:
predictedCO2 = regr.predict([[2300, 1300]])
```
Przykład:
Zobacz cały przykład w akcji:
```
import pandas
from sklearn import linear_model

df = pandas.read_csv("data.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

#predict the CO2 emission of a car where the weight is 2300kg, and the volume is 1300cm3:
predictedCO2 = regr.predict([[2300, 1300]])

print(predictedCO2)
```
[107.2087328]
Przewidywaliśmy, że samochód z silnikiem o pojemności 1,3 litra i masie 2300 kg będzie emitował około 107 gramów CO2 na każdy przejechany kilometr.
