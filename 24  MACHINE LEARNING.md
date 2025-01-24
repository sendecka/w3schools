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

Współczynnik
Współczynnik to czynnik opisujący związek ze zmienną nieznaną.

Przykład: jeśli xjest zmienną, to 2xjest xdwa razy. xjest nieznaną zmienną, a liczba 2jest współczynnikiem.

W tym przypadku możemy zapytać o wartość współczynnika wagi względem CO2 i objętości względem CO2. Odpowiedzi, które otrzymamy, mówią nam, co by się stało, gdybyśmy zwiększyli lub zmniejszyli jedną z niezależnych wartości.

Przykład
Wydrukuj wartości współczynników obiektu regresji:
```
import pandas
from sklearn import linear_model

df = pandas.read_csv("data.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

print(regr.coef_)
```

Wynik:
[0,00755095 0,00780526]

Wyjaśnienie wyniku
Tablica wyników przedstawia wartości współczynników wagi i objętości.

Waga: 0,00755095
Objętość: 0,00780526

Wartości te mówią nam, że wraz ze wzrostem masy o 1 kg emisja CO2 wzrasta o 0,00755095 g.

A jeżeli wielkość silnika (objętość) wzrośnie o 1 cm3 , emisja CO2 wzrośnie o 0,00780526 g.

Myślę, że to trafne przypuszczenie, ale sprawdźmy je!

Już przewidzieliśmy, że jeśli samochód z silnikiem o pojemności 1300 cm3 waży 2300 kg, to emisja CO2 wyniesie około 107 g.

A co jeśli zwiększymy ciężar o 1000 kg?

Przykład
Skopiuj przykład z poprzedniego, ale zmień wagę z 2300 na 3300:
```
import pandas
from sklearn import linear_model

df = pandas.read_csv("data.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

regr = linear_model.LinearRegression()
regr.fit(X, y)

predictedCO2 = regr.predict([[3300, 1300]])

print(predictedCO2)
```
Wynik:
[114.75968007]
Przewidywaliśmy, że samochód z silnikiem o pojemności 1,3 litra i masie 3300 kg będzie emitował około 115 gramów CO2 na każdy przejechany kilometr.

Co pokazuje, że współczynnik 0,00755095 jest poprawny:

107,2087328 + (1000 * 0,00755095) = 114,75968

# 11. Machine Learning - Scale
Funkcje skali
Gdy Twoje dane mają różne wartości, a nawet różne jednostki miary, porównanie ich może być trudne. Czym są kilogramy w porównaniu do metrów? Albo wysokość w porównaniu do czasu?

Odpowiedzią na ten problem jest skalowanie. Możemy skalować dane do nowych wartości, które są łatwiejsze do porównania.

Przyjrzyj się poniższej tabeli. Jest to ten sam zestaw danych, którego użyliśmy w rozdziale poświęconym regresji wielorakiej , ale tym razem kolumna objętości zawiera wartości w litrach, a nie cm3 ( 1,0 zamiast 1000).
Porównanie objętości 1,0 z wagą 790 może być trudne, ale jeśli przeskalujemy je do porównywalnych wartości, łatwo zobaczymy, jak bardzo jedna wartość ma się do drugiej.

Istnieją różne metody skalowania danych. W tym samouczku wykorzystamy metodę zwaną standaryzacją.

Metoda standaryzacji wykorzystuje następujący wzór:

z = (x - u) / s

Gdzie zjest nową wartością, xjest wartością oryginalną, ujest średnią, a sjest odchyleniem standardowym.

Jeśli weźmiemy kolumnę wagi z powyższego zestawu danych, pierwsza wartość to 790, a skalowana wartość będzie wynosić:

(790 - 1292.23) / 238.74 = -2.1
Jeśli weźmiemy kolumnę wolumenu z powyższego zestawu danych, pierwsza wartość to 1,0, a skalowana wartość będzie wynosić:

(1.0 - 1.61) / 0.38 = -1.59

Teraz możesz porównywać -2,1 z -1,59 zamiast porównywać 790 z 1,0.

Nie musisz tego robić ręcznie, moduł Python sklearn ma metodę StandardScaler() zwracającą obiekt Scaler z metodami do transformacji zestawów danych.

Przykład:
Skaluj wszystkie wartości w kolumnach Waga i Objętość:
```
import pandas
from sklearn import linear_model
from sklearn.preprocessing import StandardScaler
scale = StandardScaler()

df = pandas.read_csv("data.csv")

X = df[['Weight', 'Volume']]

scaledX = scale.fit_transform(X)

print(scaledX)
```
Wynik:
Należy zauważyć, że pierwsze dwie wartości to -2,1 i -1,59, co odpowiada naszym obliczeniom

Przewidywanie wartości CO2
Zadanie w rozdziale poświęconym regresji wielorakiej polegało na przewidzeniu emisji CO2 przez samochód, znając jedynie jego masę i objętość.

Gdy zbiór danych zostanie skalowany, będziesz musiał użyć skali podczas przewidywania wartości:

Przykład:
Przewiduj emisję CO2 z samochodu o pojemności 1,3 litra i wadze 2300 kilogramów:
```
import pandas
from sklearn import linear_model
from sklearn.preprocessing import StandardScaler
scale = StandardScaler()

df = pandas.read_csv("data.csv")

X = df[['Weight', 'Volume']]
y = df['CO2']

scaledX = scale.fit_transform(X)

regr = linear_model.LinearRegression()
regr.fit(scaledX, y)

scaled = scale.transform([[2300, 1.3]])

predictedCO2 = regr.predict([scaled[0]])
print(predictedCO2)
```
Wynik:
[107.2087328]

# 12. Machine Learning - Train/Test
Oceń swój model
W uczeniu maszynowym tworzymy modele, które pozwalają nam przewidywać wyniki pewnych zdarzeń, tak jak w poprzednim rozdziale, gdzie przewidywaliśmy emisję CO2 samochodu, gdy znaliśmy jego masę i pojemność silnika.

Aby sprawdzić, czy model jest wystarczająco dobry, możemy posłużyć się metodą Trenuj/Testuj.
Czym jest Train/Test
Trening/Test to metoda pomiaru dokładności modelu.

Ta metoda nazywa się „Trenuj/Testuj”, ponieważ dzieli zestaw danych na dwa zestawy: zestaw treningowy i zestaw testowy.

80% na szkolenia i 20% na testy.

Model jest trenowany za pomocą zestawu treningowego.

Testujesz model za pomocą zestawu testowego .

Trenowanie modelu oznacza tworzenie modelu.

Testowanie modelu oznacza testowanie dokładności modelu.
Zacznij od zestawu danych
Zacznij od zestawu danych, który chcesz przetestować.

Nasz zbiór danych przedstawia 100 klientów w sklepie i ich zwyczaje zakupowe.

Przykład:
```
import numpy
import matplotlib.pyplot as plt
numpy.random.seed(2)

x = numpy.random.normal(3, 1, 100)
y = numpy.random.normal(150, 40, 100) / x

plt.scatter(x, y)
plt.show()
```
Wynik:
Oś x przedstawia liczbę minut przed dokonaniem zakupu.

Oś Y przedstawia kwotę wydaną na zakup.

Podzielone na Trening/Test
Zbiór treningowy powinien być losowo wybranym zestawem 80% oryginalnych danych.

Zestaw testowy powinien obejmować pozostałe 20%.
```
train_x = x[:80]
train_y = y[:80]

test_x = x[80:]
test_y = y[80:]
```
Wyświetl zestaw treningowy
Wyświetl ten sam wykres punktowy z zestawem treningowym:

Przykład:
```
plt.scatter(train_x, train_y)
plt.show()
```
Wyświetl zestaw testowy
Aby mieć pewność, że zestaw testowy nie jest zupełnie inny, przyjrzymy się mu również.

Przykład:
```
plt.scatter(test_x, test_y)
plt.show()
```
Dopasuj zestaw danych
Jak wygląda zbiór danych? Moim zdaniem, myślę, że najlepszym rozwiązaniem byłaby regresja wielomianowa , więc narysujmy linię regresji wielomianowej.

Aby narysować linię przechodzącą przez punkty danych, używamy plot()metody modułu matplotlib:

Przykład
Narysuj linię regresji wielomianowej przechodzącą przez punkty danych:
```
import numpy
import matplotlib.pyplot as plt
numpy.random.seed(2)

x = numpy.random.normal(3, 1, 100)
y = numpy.random.normal(150, 40, 100) / x

train_x = x[:80]
train_y = y[:80]

test_x = x[80:]
test_y = y[80:]

mymodel = numpy.poly1d(numpy.polyfit(train_x, train_y, 4))

myline = numpy.linspace(0, 6, 100)

plt.scatter(train_x, train_y)
plt.plot(myline, mymodel(myline))
plt.show()
```
Wynik może poprzeć moją sugestię, że zbiór danych pasuje do regresji wielomianowej, nawet jeśli dałoby nam to dziwne wyniki, gdybyśmy próbowali przewidzieć wartości poza zbiorem danych. Przykład: linia wskazuje, że klient spędzający 6 minut w sklepie dokonałby zakupu o wartości 200. To prawdopodobnie oznaka nadmiernego dopasowania.

Ale co z wynikiem R-kwadrat? Wynik R-kwadrat jest dobrym wskaźnikiem tego, jak dobrze mój zestaw danych pasuje do modelu.

R2
Pamiętasz R2, znany również jako R-kwadrat?

Mierzy on związek pomiędzy osią x i osią y, a wartości mieszczą się w zakresie od 0 do 1, gdzie 0 oznacza brak związku, a 1 oznacza całkowity związek.

Moduł sklearn ma metodę r2_score() , która pomoże nam znaleźć tę zależność.

W tym przypadku chcielibyśmy zmierzyć zależność między liczbą minut spędzonych przez klienta w sklepie a kwotą pieniędzy, jaką wydaje.

Przykład:
Jak dobrze moje dane treningowe pasują do regresji wielomianowej?
```
import numpy
from sklearn.metrics import r2_score
numpy.random.seed(2)

x = numpy.random.normal(3, 1, 100)
y = numpy.random.normal(150, 40, 100) / x

train_x = x[:80]
train_y = y[:80]

test_x = x[80:]
test_y = y[80:]

mymodel = numpy.poly1d(numpy.polyfit(train_x, train_y, 4))

r2 = r2_score(train_y, mymodel(train_x))

print(r2)
```
Uwaga: Wynik 0,799 pokazuje, że istnieje prawidłowa relacja.

Wnieś zestaw testowy
Teraz stworzyliśmy model, który jest w porządku, przynajmniej jeśli chodzi o dane treningowe.

Teraz chcemy przetestować model również przy użyciu danych testowych i sprawdzić, czy da nam taki sam wynik.

Przykład
Znajdźmy wynik R2 przy użyciu danych testowych:
```
import numpy
from sklearn.metrics import r2_score
numpy.random.seed(2)

x = numpy.random.normal(3, 1, 100)
y = numpy.random.normal(150, 40, 100) / x

train_x = x[:80]
train_y = y[:80]

test_x = x[80:]
test_y = y[80:]

mymodel = numpy.poly1d(numpy.polyfit(train_x, train_y, 4))

r2 = r2_score(test_y, mymodel(test_x))

print(r2)
```
Uwaga: Wynik 0,809 pokazuje, że model jest zgodny również ze zbiorem testowym i jesteśmy pewni, że możemy go wykorzystać do przewidywania przyszłych wartości.

Przewidywanie wartości
Teraz, gdy ustaliliśmy, że nasz model jest prawidłowy, możemy zacząć przewidywać nowe wartości.
Przykład
Ile pieniędzy wyda klient, jeśli zostanie w sklepie 5 minut?
```
print(mymodel(5))
```
W przykładzie przewidziano, że klient wyda 22,88 dolarów, co wydaje się odpowiadać diagramowi:

# 13. Machine Learning - Decision Tree
Drzewo decyzyjne
W tym rozdziale pokażemy Ci, jak stworzyć „Drzewo decyzyjne”. Drzewo decyzyjne to diagram przepływu, który może pomóc Ci podejmować decyzje na podstawie wcześniejszych doświadczeń.

W tym przykładzie osoba będzie próbowała podjąć decyzję, czy powinna pójść na pokaz komediowy, czy nie.

Na szczęście nasza przykładowa osoba rejestrowała się za każdym razem, gdy w mieście odbywał się występ komediowy, a także zamieszczała informacje o komiku, a także informację, czy w nim uczestniczył, czy nie.
Jak to działa?
Najpierw odczytaj zbiór danych za pomocą pandas:

Przykład:
Odczytaj i wydrukuj zbiór danych:
```
import pandas

df = pandas.read_csv("data.csv")

print(df)
```
Aby stworzyć drzewo decyzyjne, wszystkie dane muszą mieć postać liczbową.

Musimy zamienić kolumny nie będące liczbami „Narodowość” i „Go” na wartości liczbowe.

Pandas ma map()metodę, która przyjmuje słownik zawierający informacje o tym, jak konwertować wartości.

{'UK': 0, 'USA': 1, 'N': 2}

Oznacza konwersję wartości „UK” na 0, „USA” na 1 i „N” na 2.

Przykład:
Zmień wartości łańcuchowe na wartości liczbowe:
```
d = {'UK': 0, 'USA': 1, 'N': 2}
df['Nationality'] = df['Nationality'].map(d)
d = {'YES': 1, 'NO': 0}
df['Go'] = df['Go'].map(d)

print(df)
```
Następnie musimy oddzielić kolumny funkcji od kolumny docelowej .

Kolumny funkcji to kolumny, na podstawie których próbujemy przewidzieć wartości , a kolumna docelowa to kolumna zawierająca wartości, które próbujemy przewidzieć.

Przykład
Xto kolumny funkcji, yto kolumna docelowa:
```
features = ['Age', 'Experience', 'Rank', 'Nationality']

X = df[features]
y = df['Go']

print(X)
print(y)
```
Teraz możemy stworzyć rzeczywiste drzewo decyzyjne, dopasować je do naszych szczegółów. Zacznijmy od zaimportowania potrzebnych nam modułów:

Przykład
Utwórz i wyświetl drzewo decyzyjne:
```
import pandas
from sklearn import tree
from sklearn.tree import DecisionTreeClassifier
import matplotlib.pyplot as plt

df = pandas.read_csv("data.csv")

d = {'UK': 0, 'USA': 1, 'N': 2}
df['Nationality'] = df['Nationality'].map(d)
d = {'YES': 1, 'NO': 0}
df['Go'] = df['Go'].map(d)

features = ['Age', 'Experience', 'Rank', 'Nationality']

X = df[features]
y = df['Go']

dtree = DecisionTreeClassifier()
dtree = dtree.fit(X, y)

tree.plot_tree(dtree, feature_names=features)
```
Wyjaśnienie wyniku
Drzewo decyzyjne wykorzystuje Twoje wcześniejsze decyzje, aby obliczyć prawdopodobieństwo, że będziesz chciał pójść na występ komika, czy nie.
Stopień
Rank <= 6.5oznacza, że ​​każdy komik o randze 6,5 lub niższej podąży za Truestrzałką (w lewo), a pozostali podążą za Falsestrzałką (w prawo).

gini = 0.497odnosi się do jakości podziału i zawsze jest liczbą pomiędzy 0,0 a 0,5, gdzie 0,0 oznacza, że ​​wszystkie próbki otrzymały ten sam wynik, a 0,5 oznacza, że ​​podział został wykonany dokładnie w połowie.

samples = 13oznacza, że ​​na tym etapie decyzji pozostało 13 komików, czyli wszyscy, ponieważ jest to pierwszy krok.

value = [6, 7]oznacza, że ​​z tych 13 komików, 6 otrzyma odpowiedź „NIE”, a 7 otrzyma odpowiedź „START”.

Gini
Istnieje wiele sposobów podziału próbek, w tym samouczku wykorzystamy metodę GINI.

Metoda Giniego wykorzystuje następujący wzór:

Gini = 1 - (x/n)2 - (y/n)2

Gdzie xjest liczbą pozytywnych odpowiedzi („GO”), njest liczbą próbek, a yjest liczbą negatywnych odpowiedzi („NO”), co daje nam następujące obliczenie:

1 - (7 / 13)2 - (6 / 13)2 = 0.497
Następny krok zawiera dwa pola: jedno pole dla komików z „Rangą” równą lub niższą niż 6,5 i jedno pole z pozostałymi.

Prawda - 5 komików kończy tutaj:
gini = 0.0oznacza, że ​​wszystkie próbki dały ten sam wynik.

samples = 5oznacza, że ​​w tej gałęzi pozostało 5 komików (5 komików z rangą 6,5 lub niższą).

value = [5, 0]oznacza, że ​​5 otrzyma odpowiedź „NIE”, a 0 otrzyma odpowiedź „GO”.

Fałsz - 8 komików kontynuuje:
Narodowość
Nationality <= 0.5oznacza, że ​​komicy, których wartość narodowości jest mniejsza niż 0,5, podążą za strzałką po lewej stronie (co oznacza wszystkich z Wielkiej Brytanii), a pozostali podążą za strzałką po prawej stronie.

gini = 0.219oznacza, że ​​około 22% próbek poszłoby w jednym kierunku.

samples = 8oznacza, że ​​w tej gałęzi pozostało 8 komików (8 komików z rangą wyższą niż 6,5).

value = [1, 7]oznacza, że ​​z tych 8 komików 1 otrzyma odpowiedź „NIE”, a 7 otrzyma odpowiedź „START”.
Prawda - 4 komików kontynuuje:
Wiek
Age <= 35.5oznacza, że ​​komicy w wieku 35,5 lat lub młodsi podążą za strzałką po lewej stronie, a pozostali – za strzałką po prawej stronie.

gini = 0.375oznacza, że ​​około 37,5% próbek poszłoby w jednym kierunku.

samples = 4oznacza, że ​​w tej branży pozostało 4 komików (4 komików z Wielkiej Brytanii).

value = [1, 3]oznacza, że ​​z tych 4 komików 1 otrzyma odpowiedź „NIE”, a 3 otrzyma odpowiedź „START”.

Fałsz - 4 komików kończy tutaj:
gini = 0.0oznacza, że ​​wszystkie próbki dały ten sam wynik.

samples = 4oznacza, że ​​w tej branży pozostało 4 komików (4 komików spoza Wielkiej Brytanii).

value = [0, 4]oznacza, że ​​spośród tych 4 komików 0 otrzyma odpowiedź „NIE”, a 4 otrzyma odpowiedź „START”.

Prawda - 2 komików kończy tutaj:
gini = 0.0oznacza, że ​​wszystkie próbki dały ten sam wynik.

samples = 2oznacza, że ​​w tej branży pozostało 2 komików (2 komików w wieku 35,5 lat lub młodszych).

value = [0, 2]oznacza, że ​​z tych 2 komików 0 otrzyma odpowiedź „NIE”, a 2 otrzyma odpowiedź „START”.

Fałsz - 2 komików kontynuuje:
Doświadczenie
Experience <= 9.5oznacza, że ​​komicy z 9,5-letnim lub krótszym stażem będą podążać za strzałką po lewej stronie, a pozostali – za strzałką po prawej stronie.

gini = 0.5oznacza, że ​​50% próbek podążałoby w jednym kierunku.

samples = 2oznacza, że ​​w tej gałęzi pozostało 2 komików (2 komików starszych niż 35,5 roku życia).

value = [1, 1]oznacza, że ​​z tych dwóch komików, 1 otrzyma odpowiedź „NIE”, a 1 otrzyma odpowiedź „START”.

Prawda - 1 Komik kończy tutaj:
gini = 0.0oznacza, że ​​wszystkie próbki dały ten sam wynik.

samples = 1oznacza, że ​​w tej branży pozostał 1 komik (1 komik ze stażem 9,5 roku lub mniejszym).

value = [0, 1]oznacza, że ​​0 otrzyma odpowiedź „NIE”, a 1 otrzyma odpowiedź „GO”.

Fałsz - 1 Komik kończy tutaj:
gini = 0.0oznacza, że ​​wszystkie próbki dały ten sam wynik.

samples = 1oznacza, że ​​w tej branży pozostał 1 komik (1 komik z doświadczeniem dłuższym niż 9,5 roku).

value = [1, 0]oznacza, że ​​1 otrzyma odpowiedź „NIE”, a 0 otrzyma odpowiedź „GO”.

Przewidywanie wartości
Za pomocą drzewa decyzyjnego możemy przewidywać nowe wartości.

Przykład: Czy powinienem wybrać się na przedstawienie, w którym występuje 40-letni amerykański komik z 10-letnim doświadczeniem i 7-punktową oceną w rankingu komediowym?
Przykład
Użyj metody predict(), aby przewidzieć nowe wartości:
```
print(dtree.predict([[40, 10, 7, 1]]))
```
Przykład
Jaka byłaby odpowiedź, gdyby ocena komedii wynosiła 6?
```
print(dtree.predict([[40, 10, 6, 1]]))
```
Różne wyniki
Zobaczysz, że Drzewo Decyzyjne daje różne wyniki, jeśli uruchomisz je wystarczająco dużo razy, nawet jeśli wprowadzisz do niego te same dane.

Dzieje się tak, ponieważ Drzewo Decyzyjne nie daje nam 100% pewnej odpowiedzi. Opiera się na prawdopodobieństwie wyniku, a odpowiedź będzie się różnić.

# 13. Machine Learning - Confusion Matrix
Czym jest macierz pomyłek?
Jest to tabela używana w problemach klasyfikacyjnych do oceny, gdzie w modelu popełniono błędy.

Wiersze przedstawiają rzeczywiste klasy, w których powinny być wyniki. Kolumny przedstawiają nasze przewidywania. Używając tej tabeli łatwo zobaczyć, które przewidywania są błędne.

Tworzenie macierzy pomyłek
Macierze pomyłek można tworzyć w oparciu o przewidywania uzyskane za pomocą regresji logistycznej.

Na razie wygenerujemy rzeczywiste i przewidywane wartości wykorzystując NumPy:
```
import numpy
```
Następnie musimy wygenerować liczby dla wartości „rzeczywistych” i „przewidywanych”.
```
actual = numpy.random.binomial(1, 0.9, size = 1000)
predicted = numpy.random.binomial(1, 0.9, size = 1000)
```
Aby utworzyć macierz pomyłek musimy zaimportować metryki z modułu sklearn.
```
from sklearn import metrics
```
Po zaimportowaniu danych możemy zastosować funkcję macierzy pomyłek do wartości rzeczywistych i prognozowanych.
```
confusion_matrix = metrics.confusion_matrix(actual, predicted)
```
Aby utworzyć łatwiejszą do zinterpretowania prezentację wizualną, musimy przekształcić tabelę w macierz pomyłek.
```
cm_display = metrics.ConfusionMatrixDisplay(confusion_matrix = confusion_matrix, display_labels = [0, 1])
```
Aby wyświetlić obraz, musimy zaimportować pyplot z matplotlib.
```
import matplotlib.pyplot as plt
```
Na koniec, aby wyświetlić wykres możemy skorzystać z funkcji plot() i show() z pyplot.
```
cm_display.plot()
plt.show()
```
Zobacz cały przykład w akcji:
PrzykładZdobądź własny serwer Python
```
import matplotlib.pyplot as plt
import numpy
from sklearn import metrics

actual = numpy.random.binomial(1,.9,size = 1000)
predicted = numpy.random.binomial(1,.9,size = 1000)

confusion_matrix = metrics.confusion_matrix(actual, predicted)

cm_display = metrics.ConfusionMatrixDisplay(confusion_matrix = confusion_matrix, display_labels = [0, 1])

cm_display.plot()

plt.show()
```
Wyjaśnienie wyników
Stworzona Macierz Pomyłek składa się z czterech różnych kwadrantów:

Prawdziwie negatywne (lewy górny kwadrant)
Fałszywie pozytywne (prawy górny kwadrant)
Fałszywie negatywne (lewy dolny kwadrant)
Prawdziwie pozytywne (prawy dolny kwadrant)

Prawda oznacza, że ​​wartości zostały dokładnie przewidziane. Fałsz oznacza, że ​​wystąpił błąd lub przewidywanie było błędne.

Teraz, gdy stworzyliśmy macierz pomyłek, możemy obliczyć różne miary, aby określić jakość modelu. Najpierw przyjrzyjmy się dokładności.

 # 14. Machine Learning Confusion Matrix 
macierz pomyłek
Czym jest macierz pomyłek?
Jest to tabela używana w problemach klasyfikacyjnych do oceny, gdzie w modelu popełniono błędy.

Wiersze przedstawiają rzeczywiste klasy, w których powinny być wyniki. Kolumny przedstawiają nasze przewidywania. Używając tej tabeli łatwo zobaczyć, które przewidywania są błędne.

Tworzenie macierzy pomyłek
Macierze pomyłek można tworzyć w oparciu o przewidywania uzyskane za pomocą regresji logistycznej.

Na razie wygenerujemy rzeczywiste i przewidywane wartości wykorzystując NumPy:
```
import numpy
```
Następnie musimy wygenerować liczby dla wartości „rzeczywistych” i „przewidywanych”.
```
actual = numpy.random.binomial(1, 0.9, size = 1000)
predicted = numpy.random.binomial(1, 0.9, size = 1000)
```
Aby utworzyć macierz pomyłek musimy zaimportować metryki z modułu sklearn.
```
from sklearn import metrics
```
Po zaimportowaniu danych możemy zastosować funkcję macierzy pomyłek do wartości rzeczywistych i prognozowanych.
```
confusion_matrix = metrics.confusion_matrix(actual, predicted)
```
Aby utworzyć łatwiejszą do zinterpretowania prezentację wizualną, musimy przekształcić tabelę w macierz pomyłek.
```
cm_display = metrics.ConfusionMatrixDisplay(confusion_matrix = confusion_matrix, display_labels = [0, 1])
```
Aby wyświetlić obraz, musimy zaimportować pyplot z matplotlib.
```
import matplotlib.pyplot as plt
```
Na koniec, aby wyświetlić wykres możemy skorzystać z funkcji plot() i show() z pyplot.
```
cm_display.plot()
plt.show()
```
Zobacz cały przykład w akcji:
Przykład:
```
import matplotlib.pyplot as plt
import numpy
from sklearn import metrics

actual = numpy.random.binomial(1,.9,size = 1000)
predicted = numpy.random.binomial(1,.9,size = 1000)

confusion_matrix = metrics.confusion_matrix(actual, predicted)

cm_display = metrics.ConfusionMatrixDisplay(confusion_matrix = confusion_matrix, display_labels = [0, 1])

cm_display.plot()
plt.show()
```
Wyjaśnienie wyników
Stworzona Macierz Pomyłek składa się z czterech różnych kwadrantów:

Prawdziwie negatywne (lewy górny kwadrant)
Fałszywie pozytywne (prawy górny kwadrant)
Fałszywie negatywne (lewy dolny kwadrant)
Prawdziwie pozytywne (prawy dolny kwadrant)

Prawda oznacza, że ​​wartości zostały dokładnie przewidziane. Fałsz oznacza, że ​​wystąpił błąd lub przewidywanie było błędne.

Teraz, gdy stworzyliśmy macierz pomyłek, możemy obliczyć różne miary, aby określić jakość modelu. Najpierw przyjrzyjmy się dokładności.
Utworzone metryki
Macierz dostarcza nam wielu przydatnych wskaźników, które pomagają nam ocenić nasz model klasyfikacji.

Różne pomiary obejmują: dokładność, precyzję, czułość (odwołanie), swoistość i wynik F, wyjaśnione poniżej.

Dokładność
Dokładność mierzy, jak często model jest poprawny.

Jak obliczyć
(Prawdziwie pozytywne + prawdziwie negatywne) / Całkowita liczba przewidywań

Przykład
```
Accuracy = metrics.accuracy_score(actual, predicted)
```
Precyzja
Jaki procent spośród przewidywanych wyników pozytywnych jest rzeczywiście pozytywny?

Jak obliczyć
Prawdziwie pozytywny / (Prawdziwie pozytywny + Fałszywie pozytywny)

Precyzja nie ocenia prawidłowo przewidzianych przypadków negatywnych:

Przykład
```
Precision = metrics.precision_score(actual, predicted)
```
Wrażliwość (przypomnienie)
Jaki procent wszystkich przypadków pozytywnych przewiduje się jako pozytywny?

Czułość (nazywana czasami Recall) mierzy skuteczność modelu w przewidywaniu zdarzeń pozytywnych.

Oznacza to, że analizuje wyniki prawdziwie dodatnie i fałszywie ujemne (czyli wyniki dodatnie, które zostały błędnie przewidziane jako ujemne).

Jak obliczyć
Prawdziwie pozytywny / (Prawdziwie pozytywny + Fałszywie negatywny)

Wrażliwość pozwala zrozumieć, na ile dobrze model przewiduje, że coś jest pozytywne:
Przykład:
```
Sensitivity_recall = metrics.recall_score(actual, predicted)
```
Specyficzność
Jak dobrze model przewiduje negatywne rezultaty?

Swoistość jest pojęciem podobnym do wrażliwości, ale rozpatruje się ją z perspektywy wyników negatywnych.

Jak obliczyć
Prawdziwy Negatywny / (Prawdziwy Negatywny + Fałszywy Pozytywny)

Ponieważ jest to dokładne przeciwieństwo funkcji Recall, używamy funkcji recall_score, przyjmując etykietę pozycji przeciwnej:

Przykład:
```
Specificity = metrics.recall_score(actual, predicted, pos_label=0)
```
Wynik F
Wynik F to „średnia harmoniczna” precyzji i czułości.

Rozważa zarówno przypadki fałszywie dodatnie, jak i fałszywie ujemne i sprawdza się w przypadku niezrównoważonych zbiorów danych.

Jak obliczyć
2 * ((Precyzja * Czułość) / (Precyzja + Czułość))

Wynik ten nie uwzględnia wartości prawdziwie ujemnych:

Przykład:
```
F1_score = metrics.f1_score(actual, predicted)
```
Wszystkie obliczenia w jednym:

Przykład
#metrics
```
print({"Accuracy":Accuracy,"Precision":Precision,"Sensitivity_recall":Sensitivity_recall,"Specificity":Specificity,"F1_score":F1_score})
```

# 15. Machine Learning - Hierarchical Clustering
Klastrowanie hierarchiczne
Klastrowanie hierarchiczne to metoda uczenia się bez nadzoru do grupowania punktów danych. Algorytm buduje klastry, mierząc różnice między danymi. Uczenie się bez nadzoru oznacza, że ​​model nie musi być trenowany i nie potrzebujemy zmiennej „docelowej”. Tę metodę można stosować do dowolnych danych w celu wizualizacji i interpretacji relacji między poszczególnymi punktami danych.

W tym artykule wykorzystamy klasterowanie hierarchiczne do grupowania punktów danych i wizualizacji klastrów przy użyciu dendrogramu i wykresu punktowego.

Jak to działa?
Użyjemy aglomeracyjnego klastrowania, typu hierarchicznego klastrowania, które podąża za podejściem oddolnym. Zaczynamy od traktowania każdego punktu danych jako osobnego klastra. Następnie łączymy klastry, które mają najkrótszą odległość między nimi, aby utworzyć większe klastry. Ten krok jest powtarzany, aż powstanie jeden duży klaster zawierający wszystkie punkty danych.

Klastrowanie hierarchiczne wymaga od nas podjęcia decyzji zarówno o odległości, jak i metodzie łączenia. Użyjemy odległości euklidesowej i metody łączenia Warda, która próbuje zminimalizować wariancję między klastrami.

Przykład:
Zacznij od wizualizacji kilku punktów danych:
```
import numpy as np
import matplotlib.pyplot as plt

x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

plt.scatter(x, y)
plt.show()
```
Teraz obliczamy sprzężenie Warda, korzystając z odległości euklidesowej i wizualizujemy je za pomocą dendrogramu:
Przykład:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage

x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

data = list(zip(x, y))

linkage_data = linkage(data, method='ward', metric='euclidean')
dendrogram(linkage_data)

plt.show()
```
Tutaj robimy to samo z biblioteką Pythona scikit-learn. Następnie wizualizujemy na dwuwymiarowym wykresie:
```
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import AgglomerativeClustering

x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

data = list(zip(x, y))

hierarchical_cluster = AgglomerativeClustering(n_clusters=2, affinity='euclidean', linkage='ward')
labels = hierarchical_cluster.fit_predict(data)

plt.scatter(x, y, c=labels)
plt.show()
```
Przykład wyjaśniony
Zaimportuj potrzebne moduły.
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage
from sklearn.cluster import AgglomerativeClustering
```
Więcej informacji na temat modułu Matplotlib znajdziesz w naszym „Samouczku Matplotlib” .

Więcej informacji na temat modułu SciPy znajdziesz w naszym samouczku SciPy .

NumPy to biblioteka do pracy z tablicami i macierzami w Pythonie. Więcej informacji na temat modułu NumPy znajdziesz w naszym samouczku NumPy .

scikit-learn to popularna biblioteka do uczenia maszynowego.

Utwórz tablice przypominające dwie zmienne w zestawie danych. Zwróć uwagę, że chociaż tutaj używamy tylko dwóch zmiennych, ta metoda będzie działać z dowolną liczbą zmiennych:
```
x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]
```
Przekształć dane w zbiór punktów:
```
data = list(zip(x, y))
print(data)
```
Wynik:
```
[(4, 21), (5, 19), (10, 24), (4, 17), (3, 16), (11, 25), (14, 24), (6, 22), (10, 21), (12, 21)]
```
Oblicz powiązanie między wszystkimi różnymi punktami. Tutaj używamy prostej miary odległości euklidesowej i powiązania Warda, które ma na celu zminimalizowanie wariancji między klastrami.
```
linkage_data = linkage(data, method='ward', metric='euclidean')
```
Na koniec nanieś wyniki na dendrogram. Ten wykres pokaże nam hierarchię klastrów od dołu (poszczególne punkty) do góry (pojedynczy klaster składający się ze wszystkich punktów danych).
```
plt.show()pozwala nam zwizualizować dendrogram zamiast samych surowych danych sprzężenia.

dendrogram(linkage_data)
plt.show()
```
Biblioteka scikit-learn pozwala nam używać hierarchicznego klastrowania w inny sposób. Najpierw inicjujemy AgglomerativeClusteringklasę 2 klastrami, używając tej samej odległości euklidesowej i wiązania Warda.
```
hierarchical_cluster = AgglomerativeClustering(n_clusters=2, affinity='euclidean', linkage='ward')
```
Tę .fit_predictmetodę można wywołać dla naszych danych, aby obliczyć klastry, używając zdefiniowanych parametrów w wybranej liczbie klastrów.
```
labels = hierarchical_cluster.fit_predict(data) print(labels)
```
Wynik:
```
[0 0 1 0 0 1 1 0 1 1]
```
Na koniec, jeśli naniesiemy te same dane na wykres i pokolorujemy punkty, używając etykiet przypisanych do każdego indeksu metodą hierarchicznego grupowania, możemy zobaczyć klaster, do którego przypisano każdy punkt:
```
plt.scatter(x, y, c=labels)
plt.show()
```

# 16. Machine Learning - Logistic Regression
Regresja logistyczna
Regresja logistyczna ma na celu rozwiązanie problemów klasyfikacyjnych. Robi to poprzez przewidywanie wyników kategorycznych, w przeciwieństwie do regresji liniowej, która przewiduje wynik ciągły.

W najprostszym przypadku istnieją dwa wyniki, które nazywane są dwumianowymi, a przykładem tego jest przewidywanie, czy guz jest złośliwy czy łagodny. Inne przypadki mają więcej niż dwa wyniki do sklasyfikowania, w tym przypadku nazywa się to wielomianowym. Typowym przykładem wielomianowej regresji logistycznej byłoby przewidywanie klasy kwiatu irysa między 3 różnymi gatunkami.

Tutaj będziemy używać podstawowej regresji logistycznej do przewidywania zmiennej dwumianowej. Oznacza to, że ma ona tylko dwa możliwe wyniki.
Jak to działa?
W Pythonie mamy moduły, które wykonają pracę za nas. Zacznij od zaimportowania modułu NumPy.
```
import numpy
```
Przechowuj zmienne niezależne w X.

Zapisz zmienną zależną w y.

Poniżej znajduje się przykładowy zestaw danych:
```
#X represents the size of a tumor in centimeters.
X = numpy.array([3.78, 2.44, 2.09, 0.14, 1.72, 1.65, 4.92, 4.37, 4.96, 4.52, 3.69, 5.88]).reshape(-1,1)

#Note: X has to be reshaped into a column from a row for the LogisticRegression() function to work.
#y represents whether or not the tumor is cancerous (0 for "No", 1 for "Yes").
y = numpy.array([0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1])
```
Wykorzystamy metodę z modułu sklearn, więc będziemy musieli zaimportować również ten moduł:
```
from sklearn import linear_model
```
Z modułu sklearn użyjemy metody LogisticRegression() w celu utworzenia obiektu regresji logistycznej.

Ten obiekt ma metodę o nazwie fit(), która przyjmuje wartości niezależne i zależne jako parametry i wypełnia obiekt regresji danymi opisującymi relację:
```
logr = linear_model.LogisticRegression()
logr.fit(X,y)
```
Teraz mamy obiekt regresji logistycznej, który jest gotowy do określenia, czy guz jest rakowy na podstawie jego rozmiaru:
```
#predict if tumor is cancerous where the size is 3.46mm:
predicted = logr.predict(numpy.array([3.46]).reshape(-1,1))
```
Przykład:
Zobacz cały przykład w akcji:
```
import numpy
from sklearn import linear_model

#Reshaped for Logistic function.
X = numpy.array([3.78, 2.44, 2.09, 0.14, 1.72, 1.65, 4.92, 4.37, 4.96, 4.52, 3.69, 5.88]).reshape(-1,1)
y = numpy.array([0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1])

logr = linear_model.LogisticRegression()
logr.fit(X,y)

#predict if tumor is cancerous where the size is 3.46mm:
predicted = logr.predict(numpy.array([3.46]).reshape(-1,1))
print(predicted)
```
Wynik
```
 [0]
```
Przewidywaliśmy, że guz o wielkości 3,46 mm nie będzie nowotworem złośliwym.

Współczynnik
W regresji logistycznej współczynnik jest oczekiwaną zmianą logarytmu szansy na zmianę wyniku na jednostkę w X.

Nie jest to zbyt intuicyjne, więc wykorzystajmy to, aby stworzyć coś, co będzie miało więcej sensu, szanse.

Przykład:
Zobacz cały przykład w akcji:
```
import numpy
from sklearn import linear_model

#Reshaped for Logistic function.
X = numpy.array([3.78, 2.44, 2.09, 0.14, 1.72, 1.65, 4.92, 4.37, 4.96, 4.52, 3.69, 5.88]).reshape(-1,1)
y = numpy.array([0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1])

logr = linear_model.LogisticRegression()
logr.fit(X,y)

log_odds = logr.coef_
odds = numpy.exp(log_odds)

print(odds)
```
Wynik
```
 [4.03541657]
```
Oznacza to, że wraz ze wzrostem wielkości guza o 1 mm prawdopodobieństwo, że jest to nowotwór złośliwy, wzrasta czterokrotnie.

Prawdopodobieństwo
Wartości współczynnika i punktu przecięcia można wykorzystać do określenia prawdopodobieństwa, że ​​każdy guz jest nowotworem złośliwym.

Utwórz funkcję, która używa współczynnika modelu i wartości przecięcia, aby zwrócić nową wartość. Ta nowa wartość reprezentuje prawdopodobieństwo, że dana obserwacja jest guzem:

```
def logit2prob(logr,x):
  log_odds = logr.coef_ * x + logr.intercept_
  odds = numpy.exp(log_odds)
  probability = odds / (1 + odds)
  return(probability)
```
Wyjaśnienie funkcji
Aby znaleźć logarytm szans dla każdej obserwacji, musimy najpierw utworzyć wzór podobny do wzoru regresji liniowej, wyodrębniając współczynnik i przecięcie.
```
log_odds = logr.coef_ * x + logr.intercept_
```
Aby następnie zamienić logarytmiczne szanse na szanse, musimy je wynieść do postaci wykładniczej.
```
odds = numpy.exp(log_odds)
```
Teraz, gdy znamy już szanse, możemy zamienić je na prawdopodobieństwo, dzieląc je przez 1 i dodając szanse.
```
probability = odds / (1 + odds)
```
Wykorzystajmy teraz funkcję z tym, czego się dowiedzieliśmy, aby obliczyć prawdopodobieństwo, że każdy guz jest złośliwy.

Przykład:
Zobacz cały przykład w akcji:
```
import numpy
from sklearn import linear_model

X = numpy.array([3.78, 2.44, 2.09, 0.14, 1.72, 1.65, 4.92, 4.37, 4.96, 4.52, 3.69, 5.88]).reshape(-1,1)
y = numpy.array([0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1])

logr = linear_model.LogisticRegression()
logr.fit(X,y)

def logit2prob(logr, X):
  log_odds = logr.coef_ * X + logr.intercept_
  odds = numpy.exp(log_odds)
  probability = odds / (1 + odds)
  return(probability)

print(logit2prob(logr, X))
```
Wynik
```
  [[0,60749955]
   [0,19268876]
   [0,12775886]
   [0,00955221]
   [0,08038616]
   [0,07345637]
   [0,88362743]
   [0,77901378]
   [0,88924409]
   [0,81293497]
   [0,57719129]
   [0,96664243]]
   ```
Wyjaśnienie wyników:


3,78 0,61 Prawdopodobieństwo, że guz o wielkości 3,78 cm jest nowotworem złośliwym wynosi 61%.

2,44 0,19 Prawdopodobieństwo, że guz o wielkości 2,44 cm jest nowotworem złośliwym wynosi 19%.

2,09 0,13 Prawdopodobieństwo, że guz o wielkości 2,09 cm jest nowotworem złośliwym wynosi 13%.

# 17 Machine Learning - Grid Search
Wyszukiwanie w siatce
Większość modeli uczenia maszynowego zawiera parametry, które można dostosować, aby zmienić sposób uczenia się modelu. Na przykład model regresji logistycznej z sklearn, ma parametr C, który kontroluje regularizację, co wpływa na złożoność modelu.

Jak wybrać najlepszą wartość dla C? Najlepsza wartość zależy od danych użytych do trenowania modelu.

Jak to działa?
Jedną z metod jest wypróbowanie różnych wartości, a następnie wybranie wartości, która daje najlepszy wynik. Ta technika jest znana jako wyszukiwanie siatki . Gdybyśmy musieli wybrać wartości dla dwóch lub więcej parametrów, ocenilibyśmy wszystkie kombinacje zestawów wartości, tworząc w ten sposób siatkę wartości.

Zanim przejdziemy do przykładu, dobrze jest wiedzieć, co robi parametr, który zmieniamy. Wyższe wartości mówią Cmodelowi, że dane treningowe przypominają informacje ze świata rzeczywistego, kładą większy nacisk na dane treningowe. Podczas gdy niższe wartości Crobią odwrotnie.

Korzystanie z domyślnych parametrów
Najpierw sprawdźmy, jakie wyniki możemy wygenerować bez przeszukiwania siatki, wykorzystując jedynie parametry bazowe.

Aby rozpocząć, musimy najpierw załadować zestaw danych, z którym będziemy pracować.
```
from sklearn import datasets
iris = datasets.load_iris()
```
Następnie, aby utworzyć model, musimy mieć zbiór zmiennych niezależnych X i zmienną zależną y.
```
X = iris['data']
y = iris['target']
```
Teraz załadujemy model logistyczny do klasyfikacji kwiatów irysów.
```
from sklearn.linear_model import LogisticRegression
```
Tworzenie modelu i ustawienie parametru max_iter na wyższą wartość w celu zapewnienia znalezienia wyniku przez model.

Należy pamiętać, że domyślna wartość Cw modelu regresji logistycznej wynosi 1, porównamy ją później.

W poniższym przykładzie przyjrzymy się zestawowi danych tęczówki i spróbujemy wytrenować model przy użyciu różnych wartości Cw regresji logistycznej.
```
logit = LogisticRegression(max_iter = 10000)
```
Po utworzeniu modelu musimy dopasować go do danych.
```
print(logit.fit(X,y))
```
Aby ocenić model stosujemy metodę punktacji.
```
print(logit.score(X,y))
```
Przykład:
```
from sklearn import datasets
from sklearn.linear_model import LogisticRegression

iris = datasets.load_iris()

X = iris['data']
y = iris['target']

logit = LogisticRegression(max_iter = 10000)

print(logit.fit(X,y))
```

print(logit.score(X,y))
Przy ustawieniu domyślnym C = 1uzyskaliśmy wynik 0.973.

Sprawdźmy, czy możemy uzyskać lepsze wyniki, stosując przeszukiwanie siatki z wartościami różnicy wynoszącymi 0,973.

Implementacja wyszukiwania siatki
Powtórzymy te same kroki, co poprzednio, z tą różnicą, że tym razem ustawimy zakres wartości dla C.

Aby określić, jakie wartości należy ustawić dla wyszukiwanych parametrów, potrzebna jest wiedza specjalistyczna i praktyka.

Ponieważ wartością domyślną Cjest 1, ustawimy zakres wartości ją otaczających.
```
C = [0.25, 0.5, 0.75, 1, 1.25, 1.5, 1.75, 2]
```
Następnie utworzymy pętlę for, aby zmieniać wartości Cmodelu i oceniać je po każdej zmianie.

Najpierw utworzymy pustą listę, w której zapiszemy wynik.
```
scores = []
```
Aby zmienić wartości, Cmusimy przejść pętlą przez zakres wartości i za każdym razem aktualizować parametr.
```
for choice in C:
  logit.set_params(C=choice)
  logit.fit(X, y)
  scores.append(logit.score(X, y))
```
Mając wyniki zapisane na liście, możemy ocenić, który wybór Cjest najlepszy.
```
print(scores)
```
Przykład
```
from sklearn import datasets
from sklearn.linear_model import LogisticRegression

iris = datasets.load_iris()

X = iris['data']
y = iris['target']

logit = LogisticRegression(max_iter = 10000)

C = [0.25, 0.5, 0.75, 1, 1.25, 1.5, 1.75, 2]

scores = []

for choice in C:
  logit.set_params(C=choice)
  logit.fit(X, y)
  scores.append(logit.score(X, y))

print(scores)
```
Wyjaśnienie wyników
Możemy zobaczyć, że niższe wartości Cdawały gorsze wyniki niż parametr bazowy 1. Jednak wraz ze wzrostem wartości , Cmodel 1.75doświadczył zwiększonej dokładności.

Wydaje się, że zwiększenie wartości Cponad tę wartość nie przyczynia się do zwiększenia dokładności modelu.

Uwaga dotycząca najlepszych praktyk
Oceniliśmy nasz model regresji logistycznej, używając tych samych danych, które zostały użyte do jego wytrenowania. Jeśli model odpowiada zbyt ściśle tym danym, może nie być świetny w przewidywaniu niewidzianych danych. Ten błąd statystyczny jest znany jako nadmierne dopasowanie .

Aby uniknąć wprowadzenia w błąd przez wyniki danych treningowych, możemy odłożyć część naszych danych i użyć ich specjalnie do testowania modelu. Zapoznaj się z wykładem na temat podziału tren/test, aby uniknąć wprowadzenia w błąd i nadmiernego dopasowania.

# 18. Preprocessing - Categorical Data

Na tej stronie W3schools.com współpracuje z NYC Data Science Academy w celu dostarczania naszym uczniom cyfrowych treści szkoleniowych.

Dane kategoryczne
Jeśli Twoje dane zawierają kategorie reprezentowane przez ciągi znaków, trudno będzie ich użyć do trenowania modeli uczenia maszynowego, które często akceptują wyłącznie dane liczbowe.

Zamiast ignorować dane kategoryczne i wykluczać informacje z naszego modelu, możesz przekształcić dane tak, aby możliwe było ich wykorzystanie w Twoich modelach.

Przyjrzyj się poniższej tabeli. Jest to ten sam zestaw danych, którego użyliśmy w rozdziale poświęconym regresji wielorakiej .
Przykład:
```
import pandas as pd

cars = pd.read_csv('data.csv')
print(cars.to_string())
```
Wynik
```
  Model samochodu Objętość Waga CO2
  0 Toyota Aygo 1000 790 99
  1 Mitsubishi Space Star 1200 1160 95
  2 Skoda Citigo 1000 929 95
  3 Fiata 500 900 865 90
  4 Mini Cooper 1500 1140 105
  5 VW Up! 1000 929 105
  6 Skoda Fabia 1400 1109 90
```
W rozdziale poświęconym regresji wielorakiej próbowaliśmy przewidzieć ilość emitowanego CO2 na podstawie objętości silnika i masy samochodu, ale pominęliśmy informacje o marce i modelu samochodu.

Informacje o marce lub modelu samochodu mogą pomóc nam lepiej przewidzieć ilość emitowanego CO2.

Jedno gorące kodowanie
Nie możemy wykorzystać kolumny Car lub Model w naszych danych, ponieważ nie są one numeryczne. Nie można ustalić liniowej zależności między zmienną kategoryjną Car lub Model a zmienną numeryczną CO2.

Aby rozwiązać ten problem, musimy mieć numeryczną reprezentację zmiennej kategorycznej. Jednym ze sposobów, aby to zrobić, jest posiadanie kolumny reprezentującej każdą grupę w kategorii.

Dla każdej kolumny wartości będą wynosić 1 lub 0, gdzie 1 oznacza włączenie grupy, a 0 oznacza wykluczenie. Ta transformacja jest nazywana kodowaniem one hot.

Nie musisz tego robić ręcznie, moduł Python Pandas ma funkcję, get_dummies()która wykonuje jedno gorące kodowanie.

Dowiedz się więcej o module Pandas w naszym samouczku Pandas .
Przykład
Jedna kolumna „Kodowanie na gorąco” w samochodzie:
```
import pandas as pd

cars = pd.read_csv('data.csv')
ohe_cars = pd.get_dummies(cars[['Car']])

print(ohe_cars.to_string())
```
Wyniki
Dla każdej marki samochodu w kolumnie Samochód utworzono kolumnę.

Przewidywanie CO2
Możemy wykorzystać te dodatkowe informacje wraz z objętością i wagą do przewidywania stężenia CO2

Aby połączyć informacje, możemy skorzystać z concat()funkcji z pakietu pandas.

Najpierw musimy zaimportować kilka modułów.

Zaczniemy od zaimportowania Pand.
```
import pandas
```
Moduł pandas umożliwia nam odczyt plików csv i manipulowanie obiektami DataFrame:
```
cars = pandas.read_csv("data.csv")
```
Umożliwia nam to również tworzenie zmiennych fikcyjnych:
```
ohe_cars = pandas.get_dummies(cars[['Car']])
```
Następnie musimy wybrać zmienne niezależne (X) i dodać zmienne fikcyjne kolumnowo.

Przechowuj również zmienną zależną w y.
```
X = pandas.concat([cars[['Volume', 'Weight']], ohe_cars], axis=1)
y = cars['CO2']
```
Musimy również zaimportować metodę ze sklearn, aby utworzyć model liniowy

Dowiedz się więcej o regresji liniowej .

from sklearn import linear_model

Teraz możemy dopasować dane do regresji liniowej:
```
regr = linear_model.LinearRegression()
regr.fit(X,y)
```
Wreszcie możemy przewidzieć emisję CO2 na podstawie masy samochodu, jego objętości i producenta.
```
##predict the CO2 emission of a VW where the weight is 2300kg, and the volume is 1300cm3:
predictedCO2 = regr.predict([[2300, 1300,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0]])
```
Przykład
```
import pandas
from sklearn import linear_model

cars = pandas.read_csv("data.csv")
ohe_cars = pandas.get_dummies(cars[['Car']])

X = pandas.concat([cars[['Volume', 'Weight']], ohe_cars], axis=1)
y = cars['CO2']

regr = linear_model.LinearRegression()
regr.fit(X,y)

##predict the CO2 emission of a VW where the weight is 2300kg, and the volume is 1300cm3:
predictedCO2 = regr.predict([[2300, 1300,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0]])

print(predictedCO2)
```
Wynik
```
[122.45153299]
```

Mamy teraz współczynnik dla objętości, wagi i każdej marki samochodu w zestawie danych

Udawanie
Nie jest konieczne tworzenie jednej kolumny dla każdej grupy w Twojej kategorii. Informacje mogą być przechowywane przy użyciu 1 kolumny mniej niż liczba grup, które posiadasz.

Na przykład masz kolumnę reprezentującą kolory, a w tej kolumnie masz dwa kolory: czerwony i niebieski.

Przykład
```
import pandas as pd

colors = pd.DataFrame({'color': ['blue', 'red']})

print(colors)
```
Wynik
```
    kolor
  0 niebieski
  1 czerwony
```
Możesz utworzyć 1 kolumnę o nazwie czerwony, gdzie 1 oznacza kolor czerwony, a 0 oznacza kolor nie-czerwony, czyli niebieski.

Aby to zrobić, możemy użyć tej samej funkcji, której użyliśmy do kodowania one hot, get_dummies, a następnie usunąć jedną z kolumn. Istnieje argument drop_first, który pozwala nam wykluczyć pierwszą kolumnę z wynikowej tabeli.

Przykład:
```
import pandas as pd

colors = pd.DataFrame({'color': ['blue', 'red']})
dummies = pd.get_dummies(colors, drop_first=True)

print(dummies)
```
Wynik
```
     kolor_czerwony
  0 0
  1 1
```
Co jeśli masz więcej niż 2 grupy? Jak można przedstawić wiele grup za pomocą 1 kolumny mniej?

Załóżmy, że tym razem mamy trzy kolory: czerwony, niebieski i zielony. Kiedy get_dummies podczas usuwania pierwszej kolumny, otrzymamy następującą tabelę.

Przykład:
```
import pandas as pd

colors = pd.DataFrame({'color': ['blue', 'red', 'green']})
dummies = pd.get_dummies(colors, drop_first=True)
dummies['color'] = colors['color']

print(dummies)
```
Wynik
```
     kolor_zielony kolor_czerwony kolor
  0 0 0 niebieski
  1 0 1 czerwony
```
  2 1 0 zielony

# 19. Machine Learning - K-means

K-oznacza
K-means to nienadzorowana metoda uczenia się do grupowania punktów danych. Algorytm iteracyjnie dzieli punkty danych na K klastrów, minimalizując wariancję w każdym klastrze.

Pokażemy tutaj, jak oszacować najlepszą wartość K, stosując metodę łokcia, a następnie jak użyć klasteryzacji K-średnich, aby pogrupować punkty danych w klastry.

Jak to działa?
Najpierw każdy punkt danych jest losowo przypisywany do jednego z K klastrów. Następnie obliczamy centroid (funkcjonalnie środek) każdego klastra i ponownie przypisujemy każdy punkt danych do klastra z najbliższym centroidem. Powtarzamy ten proces, aż przypisania klastrów dla każdego punktu danych przestaną się zmieniać.

Klastrowanie metodą K-means wymaga od nas wybrania K, liczby klastrów, w które chcemy grupować dane. Metoda łokcia pozwala nam wykreślić bezwładność (metrykę opartą na odległości) i zwizualizować punkt, w którym zaczyna ona maleć liniowo. Ten punkt jest nazywany „łokciem” i jest dobrym szacunkiem najlepszej wartości dla K na podstawie naszych danych.

Przykład:

Zacznij od wizualizacji kilku punktów danych:
```
import matplotlib.pyplot as plt

x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

plt.scatter(x, y)
plt.show()
```
Teraz wykorzystamy metodę łokciową do wizualizacji bezwładności dla różnych wartości K:

Przykład:
```
from sklearn.cluster import KMeans

data = list(zip(x, y))
inertias = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i)
    kmeans.fit(data)
    inertias.append(kmeans.inertia_)

plt.plot(range(1,11), inertias, marker='o')
plt.title('Elbow method')
plt.xlabel('Number of clusters')
plt.ylabel('Inertia')
plt.show()
```
Metoda łokcia pokazuje, że 2 jest dobrą wartością K, więc ponownie uczymy i wizualizujemy wynik:

Przykład:
```
kmeans = KMeans(n_clusters=2)
kmeans.fit(data)

plt.scatter(x, y, c=kmeans.labels_)
plt.show()
```
Przykład wyjaśniony
Zaimportuj potrzebne moduły.
```
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
```
Więcej informacji na temat modułu Matplotlib znajdziesz w naszym „Samouczku Matplotlib” .
```
scikit-learn to popularna biblioteka do uczenia maszynowego.
```
Utwórz tablice przypominające dwie zmienne w zestawie danych. Zwróć uwagę, że chociaż tutaj używamy tylko dwóch zmiennych, ta metoda będzie działać z dowolną liczbą zmiennych:
```
x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]
```
Przekształć dane w zbiór punktów:
```
data = list(zip(x, y))
print(data)
```
Wynik:
```
[(4, 21), (5, 19), (10, 24), (4, 17), (3, 16), (11, 25), (14, 24), (6, 22), (10, 21), (12, 21)]
```
Aby znaleźć najlepszą wartość dla K, musimy uruchomić K-means w naszych danych dla zakresu możliwych wartości. Mamy tylko 10 punktów danych, więc maksymalna liczba klastrów wynosi 10. Więc dla każdej wartości K w zakresie (1,11) trenujemy model K-means i kreślimy intertia dla tej liczby klastrów:
```
inertias = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i)
    kmeans.fit(data)
    inertias.append(kmeans.inertia_)

plt.plot(range(1,11), inertias, marker='o')
plt.title('Elbow method')
plt.xlabel('Number of clusters')
plt.ylabel('Inertia')
plt.show()
```
Możemy zobaczyć, że „łokieć” na powyższym wykresie (gdzie interakcja staje się bardziej liniowa) znajduje się przy K=2. Następnie możemy dopasować nasz algorytm K-means jeszcze raz i narysować różne klastry przypisane do danych:
```
kmeans = KMeans(n_clusters=2)
kmeans.fit(data)

plt.scatter(x, y, c=kmeans.labels_)
plt.show()
```
# 20. Machine Learning - Bootstrap Aggregation (Bagging)

Metody takie jak drzewa decyzyjne mogą być podatne na nadmierne dopasowanie do zbioru treningowego, co może prowadzić do błędnych prognoz na podstawie nowych danych.

Agregacja Bootstrap (bagging) to metoda ensemblingu, która próbuje rozwiązać problem nadmiernego dopasowania w przypadku problemów klasyfikacji lub regresji. Bagging ma na celu poprawę dokładności i wydajności algorytmów uczenia maszynowego. Robi to poprzez losowe podzbiory oryginalnego zestawu danych z zamianą i dopasowuje klasyfikator (w przypadku klasyfikacji) lub regresor (w przypadku regresji) do każdego podzbioru. Następnie prognozy dla każdego podzbioru są agregowane poprzez głosowanie większościowe w przypadku klasyfikacji lub uśrednianie w przypadku regresji, co zwiększa dokładność prognoz.
Ocena klasyfikatora bazowego

Aby zobaczyć, jak bagging może poprawić wydajność modelu, musimy zacząć od oceny, jak klasyfikator bazowy działa w zestawie danych. Jeśli nie wiesz, czym są drzewa decyzyjne, przejrzyj lekcję o drzewach decyzyjnych, zanim przejdziesz dalej, ponieważ bagging jest kontynuacją tej koncepcji.

Będziemy chcieli zidentyfikować różne klasy win znajdujące się w zbiorze danych o winach Sklearn.

Zacznijmy od zaimportowania niezbędnych modułów.
```
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.tree import DecisionTreeClassifier
```
Następnie musimy załadować dane i zapisać je w X (cechy wejściowe) i y (cecha docelowa). Parametr as_frame jest ustawiony na True, więc nie tracimy nazw cech podczas ładowania danych. ( sklearnwersja starsza niż 0.23 musi pominąć as_frameargument, ponieważ nie jest obsługiwany)
```
data = datasets.load_wine(as_frame = True)

X = data.data
y = data.target
```
Aby właściwie ocenić nasz model na podstawie niewidzianych danych, musimy podzielić X i y na zestawy treningowe i testowe. Aby uzyskać informacje na temat dzielenia danych, zobacz lekcję Trenuj/Testuj.
```
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.25, random_state = 22)
```
Mając przygotowane dane, możemy teraz utworzyć instancję klasyfikatora bazowego i dopasować go do danych treningowych.
```
dtree = DecisionTreeClassifier(random_state = 22)
dtree.fit(X_train,y_train)
```
Wynik:
```
DecisionTreeClassifier(random_state=22)
```
Teraz możemy przewidzieć klasę wina na podstawie niewidzianego zestawu testowego i ocenić wydajność modelu.
```
y_pred = dtree.predict(X_test)

print("Train data accuracy:",accuracy_score(y_true = y_train, y_pred = dtree.predict(X_train)))
print("Test data accuracy:",accuracy_score(y_true = y_test, y_pred = y_pred))
```
Wynik:
```
Train data accuracy: 1.0
Test data accuracy: 0.8222222222222222
```
Przykład: Zaimportuj niezbędne dane i oceń wydajność klasyfikatora podstawowego.
```
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.tree import DecisionTreeClassifier

data = datasets.load_wine(as_frame = True)

X = data.data
y = data.target

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.25, random_state = 22)

dtree = DecisionTreeClassifier(random_state = 22)
dtree.fit(X_train,y_train)

y_pred = dtree.predict(X_test)

print("Train data accuracy:",accuracy_score(y_true = y_train, y_pred = dtree.predict(X_train)))
print("Test data accuracy:",accuracy_score(y_true = y_test, y_pred = y_pred))
```
Podstawowy klasyfikator działa całkiem dobrze na zbiorze danych, osiągając 82% dokładności w zbiorze danych testowych przy użyciu bieżących parametrów (jeśli nie ustawiono random_stateparametrów, mogą wystąpić odmienne wyniki).

Mając teraz dokładność bazową dla zestawu danych testowych, możemy sprawdzić, jak klasyfikator Bagging przewyższa pojedynczy klasyfikator drzewa decyzyjnego.

Tworzenie klasyfikatora Bagging
W celu przeprowadzenia operacji bagging musimy ustawić parametr n_estimators. Jest to liczba klasyfikatorów bazowych, które nasz model będzie agregował.

W przypadku tego przykładowego zestawu danych liczba estymatorów jest stosunkowo niska, często zdarza się, że eksplorowane są znacznie większe zakresy. Strojenie hiperparametrów jest zwykle wykonywane za pomocą wyszukiwania siatki , ale na razie użyjemy wybranego zestawu wartości dla liczby estymatorów.

Zaczynamy od zaimportowania niezbędnego modelu.
```
from sklearn.ensemble import BaggingClassifier
```
Teraz utwórzmy zakres wartości reprezentujący liczbę estymatorów, których chcemy użyć w każdym zespole.
```
estimator_range = [2,4,6,8,10,12,14,16]
```
Aby zobaczyć, jak klasyfikator Bagging Classifier działa z różnymi wartościami n_estimators, potrzebujemy sposobu na iterację w zakresie wartości i przechowywanie wyników z każdego zespołu. W tym celu utworzymy pętlę for, przechowując modele i wyniki na oddzielnych listach do późniejszych wizualizacji.

Uwaga: Domyślnym parametrem dla klasyfikatora bazowego BaggingClassifierjest , DicisionTreeClassifierdlatego nie musimy go ustawiać podczas tworzenia instancji modelu bagging.
```
models = []
scores = []

for n_estimators in estimator_range:

    # Create bagging classifier
    clf = BaggingClassifier(n_estimators = n_estimators, random_state = 22)

    # Fit the model
    clf.fit(X_train, y_train)

    # Append the model and score to their respective list
    models.append(clf)
    scores.append(accuracy_score(y_true = y_test, y_pred = clf.predict(X_test)))
```
Po zapisaniu modeli i wyników możemy teraz zwizualizować poprawę wydajności modelu.
```
import matplotlib.pyplot as plt

# Generate the plot of scores against number of estimators
plt.figure(figsize=(9,6))
plt.plot(estimator_range, scores)

# Adjust labels and font (to make visable)
plt.xlabel("n_estimators", fontsize = 18)
plt.ylabel("score", fontsize = 18)
plt.tick_params(labelsize = 16)

# Visualize plot
plt.show()
```
Przykład
Zaimportuj niezbędne dane i oceń BaggingClassifierwydajność.
```
import matplotlib.pyplot as plt
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.ensemble import BaggingClassifier

data = datasets.load_wine(as_frame = True)

X = data.data
y = data.target

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.25, random_state = 22)

estimator_range = [2,4,6,8,10,12,14,16]

models = []
scores = []

for n_estimators in estimator_range:

    # Create bagging classifier
    clf = BaggingClassifier(n_estimators = n_estimators, random_state = 22)

    # Fit the model
    clf.fit(X_train, y_train)

    # Append the model and score to their respective list
    models.append(clf)
    scores.append(accuracy_score(y_true = y_test, y_pred = clf.predict(X_test)))

# Generate the plot of scores against number of estimators
plt.figure(figsize=(9,6))
plt.plot(estimator_range, scores)

# Adjust labels and font (to make visable)
plt.xlabel("n_estimators", fontsize = 18)
plt.ylabel("score", fontsize = 18)
plt.tick_params(labelsize = 16)

# Visualize plot
plt.show()
```
Wyjaśnienie wyników
Poprzez iterację przez różne wartości dla liczby estymatorów możemy zobaczyć wzrost wydajności modelu z 82,2% do 95,5%. Po 14 estymatorach dokładność zaczyna spadać, ponownie, jeśli ustawisz inną wartość, random_statewartości, które zobaczysz, będą się różnić. Dlatego najlepszą praktyką jest stosowanie walidacji krzyżowej w celu zapewnienia stabilnych wyników.

W tym przypadku widzimy 13,3% wzrost dokładności identyfikacji rodzaju wina.

Inna forma oceny
Ponieważ bootstrapping wybiera losowe podzbiory obserwacji w celu utworzenia klasyfikatorów, istnieją obserwacje, które są pomijane w procesie selekcji. Te obserwacje „out-of-bag” można następnie wykorzystać do oceny modelu, podobnie jak w przypadku zestawu testowego. Należy pamiętać, że estymacja out-of-bag może przeszacować błąd w problemach klasyfikacji binarnej i powinna być stosowana wyłącznie jako uzupełnienie innych metryk.

W poprzednim ćwiczeniu widzieliśmy, że 12 estymatorów dało najwyższą dokładność, więc wykorzystamy to do stworzenia naszego modelu. Tym razem ustawiając parametr oob_scorena true, aby ocenić model z wynikiem out-of-bag.

Przykład
Utwórz model z metryką out-of-bag.
```
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.ensemble import BaggingClassifier

data = datasets.load_wine(as_frame = True)

X = data.data
y = data.target

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.25, random_state = 22)

oob_model = BaggingClassifier(n_estimators = 12, oob_score = True,random_state = 22)

oob_model.fit(X_train, y_train)

print(oob_model.oob_score_)
```
Ponieważ próbki użyte w OOB i zestawie testowym są różne, a zbiór danych jest stosunkowo mały, istnieje różnica w dokładności. Rzadko się zdarza, aby były dokładnie takie same, ponownie OOB powinno być używane jako szybki sposób szacowania błędu, ale nie jest to jedyna metryka oceny.

Generowanie drzew decyzyjnych z klasyfikatora Bagging
Jak widać w lekcji Drzewo decyzyjne , możliwe jest przedstawienie graficzne drzewa decyzyjnego utworzonego przez model. Możliwe jest również zobaczenie poszczególnych drzew decyzyjnych, które trafiły do ​​zagregowanego klasyfikatora. Pomaga nam to uzyskać bardziej intuicyjne zrozumienie tego, w jaki sposób model baggingu dochodzi do swoich przewidywań.

Uwaga: Ta metoda działa tylko w przypadku mniejszych zbiorów danych, w których drzewa są stosunkowo płytkie i wąskie, co ułatwia ich wizualizację.

Będziemy musieli zaimportować plot_treefunkcję z sklearn.tree. Różne drzewa mogą być wykreślone poprzez zmianę estymatora, który chcesz zwizualizować.

Przykład
Generuj drzewa decyzyjne z klasyfikatora Bagging
```
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.ensemble import BaggingClassifier
from sklearn.tree import plot_tree

X = data.data
y = data.target

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.25, random_state = 22)

clf = BaggingClassifier(n_estimators = 12, oob_score = True,random_state = 22)

clf.fit(X_train, y_train)

plt.figure(figsize=(30, 20))

plot_tree(clf.estimators_[0], feature_names = X.columns)
```
Tutaj możemy zobaczyć tylko pierwsze drzewo decyzyjne, które zostało użyte do głosowania nad ostateczną prognozą. Ponownie, zmieniając indeks klasyfikatora, możesz zobaczyć każde z drzew, które zostały zagregowane.

# 21. Machine Learning - Cross Validation
Walidacja krzyżowa
Podczas dostosowywania modeli dążymy do zwiększenia ogólnej wydajności modelu na niewidzianych danych. Strojenie hiperparametrów może prowadzić do znacznie lepszej wydajności na zestawach testowych. Jednak optymalizacja parametrów zestawu testowego może prowadzić do wycieku informacji, powodując, że model będzie działał gorzej na niewidzianych danych. Aby to skorygować, możemy przeprowadzić walidację krzyżową.

Aby lepiej zrozumieć CV, będziemy wykonywać różne metody na zbiorze danych iris. Najpierw załadujmy i oddzielmy dane.
```
from sklearn import datasets

X, y = datasets.load_iris(return_X_y=True)
```
Istnieje wiele metod walidacji krzyżowej, zaczniemy od omówienia k-krotnej walidacji krzyżowej.
K -Skład
Dane treningowe używane w modelu są dzielone na k mniejszych zestawów, które mają być użyte do walidacji modelu. Następnie model jest trenowany na k-1 fałdach zestawu treningowego. Pozostały fałd jest następnie używany jako zestaw walidacyjny do oceny modelu.

Ponieważ będziemy próbować klasyfikować różne gatunki kwiatów irysa, będziemy musieli zaimportować model klasyfikatora. W tym ćwiczeniu użyjemy pliku DecisionTreeClassifier. Będziemy również musieli zaimportować moduły CV z pliku sklearn.
```
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import KFold, cross_val_score
```
Po załadowaniu danych możemy teraz utworzyć i dopasować model do oceny.
```
clf = DecisionTreeClassifier(random_state=42)
```
Teraz przeanalizujmy nasz model i sprawdźmy, jak działa dla każdego k -foldu.
```
k_folds = KFold(n_splits = 5)

scores = cross_val_score(clf, X, y, cv = k_folds)
```
Dobrą praktyką jest również sprawdzenie, jak CV wypadło ogólnie, poprzez uśrednienie wyników dla wszystkich fałd.

Przykład: Uruchom k-fold CV:
```
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import KFold, cross_val_score

X, y = datasets.load_iris(return_X_y=True)

clf = DecisionTreeClassifier(random_state=42)

k_folds = KFold(n_splits = 5)

scores = cross_val_score(clf, X, y, cv = k_folds)

print("Cross Validation Scores: ", scores)
print("Average CV Score: ", scores.mean())
print("Number of CV Scores used in Average: ", len(scores))
```
Warstwowy K-Fold
W przypadkach, gdy klasy są niezrównoważone, potrzebujemy sposobu na uwzględnienie braku równowagi zarówno w zestawach treningowych, jak i walidacyjnych. Aby to zrobić, możemy stratyfikować klasy docelowe, co oznacza, że ​​oba zestawy będą miały równą proporcję wszystkich klas.

Przykład
```
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import StratifiedKFold, cross_val_score

X, y = datasets.load_iris(return_X_y=True)

clf = DecisionTreeClassifier(random_state=42)

sk_folds = StratifiedKFold(n_splits = 5)

scores = cross_val_score(clf, X, y, cv = sk_folds)

print("Cross Validation Scores: ", scores)
print("Average CV Score: ", scores.mean())
print("Number of CV Scores used in Average: ", len(scores))
```
Podczas gdy liczba fałdów jest taka sama, średni współczynnik CV wzrasta od podstawowego k-fałdu, gdy upewnimy się, że istnieją klasy stratyfikowane.

Zostaw-Jedną-Na Zewnątrz (LOO)
Zamiast wybierać liczbę podziałów w zestawie danych treningowych, jak k-fold LeaveOneOut, wykorzystaj 1 obserwację do walidacji i n-1 obserwacji do trenowania. Ta metoda jest techniką wyczerpującą.

Przykład
Uruchom LOO CV:
```
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import LeaveOneOut, cross_val_score

X, y = datasets.load_iris(return_X_y=True)

clf = DecisionTreeClassifier(random_state=42)

loo = LeaveOneOut()

scores = cross_val_score(clf, X, y, cv = loo)

print("Cross Validation Scores: ", scores)
print("Average CV Score: ", scores.mean())
print("Number of CV Scores used in Average: ", len(scores))
```
Możemy zauważyć, że liczba wykonanych wyników walidacji krzyżowej jest równa liczbie obserwacji w zestawie danych. W tym przypadku w zestawie danych iris znajduje się 150 obserwacji.

Średni wynik CV wynosi 94%.

Pozostaw-P-Out (LPO)
Leave-P-Out to po prostu niuansowa różnica w stosunku do idei Leave-One-Out, polegająca na tym, że możemy wybrać liczbę p, które mają zostać użyte w zestawie walidacyjnym.

Przykład
Uruchom CV LPO:
```
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import LeavePOut, cross_val_score

X, y = datasets.load_iris(return_X_y=True)

clf = DecisionTreeClassifier(random_state=42)

lpo = LeavePOut(p=2)

scores = cross_val_score(clf, X, y, cv = lpo)

print("Cross Validation Scores: ", scores)
print("Average CV Score: ", scores.mean())
print("Number of CV Scores used in Average: ", len(scores))
```

Jak widać, jest to wyczerpująca metoda, która pozwala obliczyć znacznie więcej wyników niż Leave-One-Out, nawet przy ap = 2, a mimo to pozwala uzyskać mniej więcej taki sam średni wynik CV.

Shuffle Split
W przeciwieństwie do KFold, ShuffleSplitpomija procent danych, które nie będą używane w zestawach pociągowych lub walidacyjnych. Aby to zrobić, musimy zdecydować, jakie są rozmiary pociągu i testu, a także liczba podziałów.

Przykład
Uruchom Shuffle Split CV:
```
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import ShuffleSplit, cross_val_score

X, y = datasets.load_iris(return_X_y=True)

clf = DecisionTreeClassifier(random_state=42)

ss = ShuffleSplit(train_size=0.6, test_size=0.3, n_splits = 5)

scores = cross_val_score(clf, X, y, cv = ss)

print("Cross Validation Scores: ", scores)
print("Average CV Score: ", scores.mean())
print("Number of CV Scores used in Average: ", len(scores))
```
Uwagi końcowe
To tylko kilka metod CV, które można stosować do modeli. Istnieje wiele innych klas walidacji krzyżowej, przy czym większość modeli ma własną klasę. Sprawdź skearns cross validation, aby uzyskać więcej opcji CV.

# 22. Machine Learning - AUC - ROC Curve
AUC-krzywa ROC
W klasyfikacji istnieje wiele różnych metryk oceny. Najpopularniejszą jest dokładność , która mierzy, jak często model jest poprawny. Jest to świetna metryka, ponieważ jest łatwa do zrozumienia, a uzyskanie jak największej liczby prawidłowych zgadywań jest często pożądane. Istnieją przypadki, w których możesz rozważyć użycie innej metryki oceny.

Innym powszechnym wskaźnikiem jest AUC , obszar pod krzywą charakterystyki operacyjnej odbiornika ( ROC ). Krzywa charakterystyki operacyjnej odbiornika przedstawia współczynnik prawdziwie dodatnich ( TP ) w porównaniu ze współczynnikiem fałszywie dodatnich ( FP ) przy różnych progach klasyfikacji. Progi to różne odcięcia prawdopodobieństwa, które oddzielają dwie klasy w klasyfikacji binarnej. Wykorzystuje prawdopodobieństwo, aby powiedzieć nam, jak dobrze model oddziela klasy.

Niezrównoważone dane
Załóżmy, że mamy niezrównoważony zestaw danych, w którym większość naszych danych ma jedną wartość. Możemy uzyskać wysoką dokładność dla modelu, przewidując klasę większościową.

Przykład:
```
import numpy as np
from sklearn.metrics import accuracy_score, confusion_matrix, roc_auc_score, roc_curve

n = 10000
ratio = .95
n_0 = int((1-ratio) * n)
n_1 = int(ratio * n)

y = np.array([0] * n_0 + [1] * n_1)
# below are the probabilities obtained from a hypothetical model that always predicts the majority class
# probability of predicting class 1 is going to be 100%
y_proba = np.array([1]*n)
y_pred = y_proba > .5

print(f'accuracy score: {accuracy_score(y, y_pred)}')
cf_mat = confusion_matrix(y, y_pred)
print('Confusion matrix')
print(cf_mat)
print(f'class 0 accuracy: {cf_mat[0][0]/n_0}')
print(f'class 1 accuracy: {cf_mat[1][1]/n_1}')
```
Chociaż uzyskujemy bardzo wysoką dokładność, model nie dostarcza żadnych informacji o danych, więc nie jest przydatny. Dokładnie przewidujemy klasę 1 w 100% przypadków, podczas gdy nieprawidłowo przewidujemy klasę 0 w 0% przypadków. Kosztem dokładności lepiej byłoby mieć model, który może w pewnym stopniu oddzielić te dwie klasy.

Przykład:
```
# below are the probabilities obtained from a hypothetical model that doesn't always predict the mode
y_proba_2 = np.array(
    np.random.uniform(0, .7, n_0).tolist() +
    np.random.uniform(.3, 1, n_1).tolist()
)
y_pred_2 = y_proba_2 > .5

print(f'accuracy score: {accuracy_score(y, y_pred_2)}')
cf_mat = confusion_matrix(y, y_pred_2)
print('Confusion matrix')
print(cf_mat)
print(f'class 0 accuracy: {cf_mat[0][0]/n_0}')
print(f'class 1 accuracy: {cf_mat[1][1]/n_1}')
```

W przypadku drugiego zestawu prognoz nie mamy tak wysokiej oceny dokładności jak w przypadku pierwszego, ale dokładność dla każdej klasy jest bardziej zrównoważona. Używając dokładności jako metryki oceny ocenilibyśmy pierwszy model wyżej niż drugi, mimo że nie mówi nam on nic o danych.

W takich przypadkach lepszym rozwiązaniem byłoby zastosowanie innego wskaźnika oceny, np. AUC.
```
import matplotlib.pyplot as plt

def plot_roc_curve(true_y, y_prob):
    """
    plots the roc curve based of the probabilities
    """

    fpr, tpr, thresholds = roc_curve(true_y, y_prob)
    plt.plot(fpr, tpr)
    plt.xlabel('False Positive Rate')
    plt.ylabel('True Positive Rate')
```
Przykład
Model 1:
```
plot_roc_curve(y, y_proba)
print(f'model 1 AUC score: {roc_auc_score(y, y_proba)}')
```
Przykład
Model 2:
```
plot_roc_curve(y, y_proba_2)
print(f'model 2 AUC score: {roc_auc_score(y, y_proba_2)}')
```
Wynik AUC wynoszący około 0,5 oznaczałby, że model nie jest w stanie rozróżnić dwóch klas i krzywa wyglądałaby jak linia o nachyleniu 1. Wynik AUC bliższy 1 oznacza, że ​​model jest w stanie oddzielić dwie klasy i krzywa znalazłaby się bliżej lewego górnego rogu wykresu.

Prawdopodobieństwa
Ponieważ AUC jest metryką wykorzystującą prawdopodobieństwo przewidywań klas, możemy być bardziej pewni modelu o wyższym wyniku AUC niż modelu o niższym wyniku, nawet jeśli mają podobną dokładność.

W poniższych danych mamy dwa zestawy prawdopodobieństw z hipotetycznych modeli. Pierwszy ma prawdopodobieństwa, które nie są tak „pewne” przy przewidywaniu dwóch klas (prawdopodobieństwa są bliskie 0,5). Drugi ma prawdopodobieństwa, które są bardziej „pewne” przy przewidywaniu dwóch klas (prawdopodobieństwa są bliskie ekstremów 0 lub 1).

Przykład:
```
import numpy as np

n = 10000
y = np.array([0] * n + [1] * n)
#
y_prob_1 = np.array(
    np.random.uniform(.25, .5, n//2).tolist() +
    np.random.uniform(.3, .7, n).tolist() +
    np.random.uniform(.5, .75, n//2).tolist()
)
y_prob_2 = np.array(
    np.random.uniform(0, .4, n//2).tolist() +
    np.random.uniform(.3, .7, n).tolist() +
    np.random.uniform(.6, 1, n//2).tolist()
)

print(f'model 1 accuracy score: {accuracy_score(y, y_prob_1>.5)}')
print(f'model 2 accuracy score: {accuracy_score(y, y_prob_2>.5)}')

print(f'model 1 AUC score: {roc_auc_score(y, y_prob_1)}')
print(f'model 2 AUC score: {roc_auc_score(y, y_prob_2)}')
```
Przykład
Model fabuły 1:
```
plot_roc_curve(y, y_prob_1)
```
Przykład
Model fabuły 2:
```
fpr, tpr, thresholds = roc_curve(y, y_prob_2)
plt.plot(fpr, tpr)
```
Mimo że dokładność obu modeli jest podobna, model z wyższym wynikiem AUC będzie bardziej niezawodny, ponieważ uwzględnia przewidywane prawdopodobieństwo. Bardziej prawdopodobne jest, że zapewni Ci on większą dokładność podczas przewidywania przyszłych danych.

# 23. Machine Learning - K-nearest neighbors (KNN)
KNN
KNN to prosty, nadzorowany algorytm uczenia maszynowego (ML), który można wykorzystać do zadań klasyfikacji lub regresji — a także jest często używany w imputacji wartości brakujących. Opiera się na idei, że obserwacje najbliższe danemu punktowi danych są najbardziej „podobnymi” obserwacjami w zestawie danych, dlatego możemy klasyfikować nieprzewidziane punkty na podstawie wartości najbliższych istniejących punktów. Wybierając K , użytkownik może wybrać liczbę pobliskich obserwacji do wykorzystania w algorytmie.

Pokażemy tutaj, jak wdrożyć algorytm KNN do klasyfikacji i jak różne wartości K wpływają na wyniki.

Jak to działa?
K to liczba najbliższych sąsiadów do wykorzystania. Do klasyfikacji, głosowanie większościowe jest używane do określenia, do której klasy należy nowa obserwacja. Większe wartości K są często bardziej odporne na wartości odstające i dają bardziej stabilne granice decyzyjne niż bardzo małe wartości ( K=3 byłoby lepsze niż K=1 , co mogłoby dawać niepożądane rezultaty).

Przykład:
Zacznij od wizualizacji kilku punktów danych:
```
import matplotlib.pyplot as plt

x = [4, 5, 10, 4, 3, 11, 14 , 8, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]
classes = [0, 0, 1, 0, 0, 1, 1, 0, 1, 1]

plt.scatter(x, y, c=classes)
plt.show()
```
Teraz dopasowujemy algorytm KNN z K=1:
```
from sklearn.neighbors import KNeighborsClassifier

data = list(zip(x, y))
knn = KNeighborsClassifier(n_neighbors=1)

knn.fit(data, classes)
```
I użyj go do sklasyfikowania nowego punktu danych:
Przykład
```
new_x = 8
new_y = 21
new_point = [(new_x, new_y)]

prediction = knn.predict(new_point)

plt.scatter(x + [new_x], y + [new_y], c=classes + [prediction[0]])
plt.text(x=new_x-1.7, y=new_y-0.7, s=f"new point, class: {prediction[0]}")
plt.show()
```
Teraz robimy to samo, ale z wyższą wartością K, co zmienia prognozę:

Przykład
```
knn = KNeighborsClassifier(n_neighbors=5)

knn.fit(data, classes)

prediction = knn.predict(new_point)

plt.scatter(x + [new_x], y + [new_y], c=classes + [prediction[0]])
plt.text(x=new_x-1.7, y=new_y-0.7, s=f"new point, class: {prediction[0]}")
plt.show()
```
Przykład wyjaśniony
Zaimportuj potrzebne moduły.

Więcej informacji na temat modułu Matplotlib znajdziesz w naszym „Samouczku Matplotlib” .

scikit-learn to popularna biblioteka do uczenia maszynowego w Pythonie.
```
import matplotlib.pyplot as plt
from sklearn.neighbors import KNeighborsClassifier
```
Utwórz tablice przypominające zmienne w zestawie danych. Mamy dwie cechy wejściowe ( xi y), a następnie klasę docelową ( class). Cechy wejściowe, które są wstępnie oznaczone naszą klasą docelową, zostaną użyte do przewidywania klasy nowych danych. Należy zauważyć, że chociaż tutaj używamy tylko dwóch cech wejściowych, ta metoda będzie działać z dowolną liczbą zmiennych:
```
x = [4, 5, 10, 4, 3, 11, 14 , 8, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]
classes = [0, 0, 1, 0, 0, 1, 1, 0, 1, 1]
```
Przekształć cechy wejściowe w zbiór punktów:
```
data = list(zip(x, y))
print(data)
```
Wynik:
```
[(4, 21), (5, 19), (10, 24), (4, 17), (3, 16), (11, 25), (14, 24), (8, 22), (10, 21), (12, 21)]
```
Wykorzystując cechy wejściowe i klasę docelową, dopasowujemy model KNN do modelu, używając 1 najbliższego sąsiada:
```
knn = KNeighborsClassifier(n_neighbors=1)
knn.fit(data, classes)
```
Następnie możemy użyć tego samego obiektu KNN, aby przewidzieć klasę nowych, nieprzewidzianych punktów danych. Najpierw tworzymy nowe funkcje x i y, a następnie wywołujemy knn.predict()nowy punkt danych, aby uzyskać klasę 0 lub 1:
```
new_x = 8
new_y = 21
new_point = [(new_x, new_y)]
prediction = knn.predict(new_point)
print(prediction)
```
Wynik:
```
[0]
```
Gdy naniesiemy wszystkie dane wraz z nowym punktem i klasą, możemy zobaczyć, że zostały oznaczone na niebiesko wraz z klasą 1. Adnotacja tekstowa służy jedynie do wyróżnienia lokalizacji nowego punktu:
```
plt.scatter(x + [new_x], y + [new_y], c=classes + [prediction[0]])
plt.text(x=new_x-1.7, y=new_y-0.7, s=f"new point, class: {prediction[0]}")
plt.show()
```
Jednak gdy zmienimy liczbę sąsiadów na 5, liczba punktów użytych do klasyfikowania naszego nowego punktu ulega zmianie. W rezultacie zmienia się również klasyfikacja nowego punktu:
```
knn = KNeighborsClassifier(n_neighbors=5)
knn.fit(data, classes)
prediction = knn.predict(new_point)
print(prediction)
```
Wynik:
```
[1]
```
Gdy nanosimy klasę nowego punktu na starsze punkty, zauważamy, że kolor zmienił się na podstawie powiązanej etykiety klasy:
```
plt.scatter(x + [new_x], y + [new_y], c=classes + [prediction[0]])
plt.text(x=new_x-1.7, y=new_y-0.7, s=f"new point, class: {prediction[0]}")
plt.show()
```
