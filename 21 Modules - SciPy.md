# SciPy Tutorial
- SciPy to naukowa biblioteka obliczeniowa, która wykorzystuje Numpy pod spodem,
- SciPy oznacza naukowy Python

# SciPy Introduction
Zapewnia więcej funkcji użytkowych do optymalizacji, statystyki i przetwarzania. Jest open source, został stworzony przez Trawisa Olliphanta.

# SciPy Getting Started
Jeśli masz już zainstalowany Python i pip w systemie, instalacja SciPy jest prosta. Zainstaluj go za pomocą polecenia:
```
C:\Users\Your Name>pip install scipy
```
Jeśli te polecenie się nie powiedzie, użyj dystrybucji Python, w której jest już zainstalowany SciPy.  Po zainstalowaniu SciPy zaimportuj moduł SciPy, który chcesz używać w swoich aplikacjach dodając instrukcję: from SciPy import moule.
```
from scipy import constants
```
Teraz zaimportowaliśmy modył i aplikacja jest gotowa do użycia.
```
# Przykład: Ile metrów sześciennych mieści się w jednym litrze?
from scipy import constants

print(constants.liter)
```

Sprawdzenie wersji SciPy ciąg wersji jest przechowywany pod atrybutem __version__
```
import scipy
print(scipy.__version__)
```

# SciPy Constans - stałe - ponieważ SciPy jest bardziej skupiony na wdrożeniach naukowych, zapewnia wiele wbudowanych stałych naukowych. Te stałe mogą być pomocne podczas pracy z Data Science.
```
Przykład: wydrukuj stałą wartość Pi

from scipy import constants
print(constants.pi)
```

Jednostki stałe - listę wszystkich jednostek w module stałych można wyświetlić za pomocą funkcji div().
```
Przykład: lista wszystkich stałych.
from scipy import constants
print(dir(constants))
```
Kategorie jednostek - jednostki są umieszczone w kategoriach:
- Metryczny,
- Dwujkowy,
- Masa,
- Kąt,
- Czas,
- Długość,
- Ciśnienie,
- Volumen,
- Prędkość,
- Temperatura,
- Energia,
- Moc,
- Siła.

Przedrostki metryczne (SI) - zwracają określoną jednostkę w metrach.
Przedrostki binarne - zwracają określoną jednostkę w bajtach.
Masa - zwróci określoną jednostkę w kg.
Kąt - zwróci określoną jednostkę w radianach.
Czas - zwróci określoną jednostkę w sekundach.
Długość - zwraca określoną jednostkę w metrach.
Ciśnienie - zwraca określoną jednostkę w paskalach.
Obszar - zwróci określoną jednostkę w metrach kwadratowych.
Volumen - zwróci określoną jednostkę w metrach sześciennych.
Prędkość - zwraca jednostkę w metrach na sekundę.
Temperatura - zwraca określoną jednostkę w Kelwinach.
Energia - zwraca określonąjednostkę w dżulach.
Moc - zwraca określoną jednostkę w watach.
Siła - zwraca określoną jednoctkę w niutonach.

# SciPy Optimizers
Optymalizatory - to zestaw procedur zdefiniowanych w SciPy, które albo znajdują minimalną wartość funkcji albo pierwiadtek danych.
Zasadniczo wszystkie algorytmy w uczeniu maszynowym to nic innego jak złożone równanie, które należy zminimalizować za pomocą danych.
Pierwiastki równania - Numpy jest w stanie znaleźć pierwiastek wielomianów i równań liniowych, ale nie może znaleźć pierwiastków równań nieliniowych, takich jak to: x + cos(x). W tym celu możesz użyć funkcji optimze.root. Funkcja ta przyjmuje dwa wymagane argumenty: fun - funkcja reprezentjąca równanie, x0 - wstępne przypuszczenie dotyczące korzenia. Funkcja zwraca obiekt z informacją o rozwiązaniu. Rzeczywiste rozwiązanie jest podane pod atrybutem x zwracanego obiektu.
```
# Przykład: Znajdź pierwiastek równania x + cos(x):
from scipy.optimize import root
from math import cos

def eqn(x):
  return x + cos(x)
myroot = root(eqn, 0)
print(myroot.x)
```
Uwaga: Zwrócony obiekt zawiera znacznie więcej informacji o rozwiązaniu.
```
# Przykład: Wydrukuj wszystkie informacje o rozwiązaniu (nie tylko xo katalogu głównym)
print(myroot)
```
Minimalizowanie funkcji - Funkcja w tym kontekście reprezentuje krzywą, krzywe mają najwyższe i najniższe punkty. Wysokie punkty nazywane są maksimami. Niskie punkty nazywane są minimami. Najwyższy punkt całej krzywej nazywany jest maksimem globalnym, pozostałe zaś maksimami lokalnymi. Najniższy punkt całej krzywej nazywany jest minimem globalnym  pozostałe zaś minimami lokalnymi.

Znalezienie minimów - Możemy użyć scipy.optimize.minimize()funkcji, aby zminimalizować funkcję. Funkcja minimize()przyjmuje następujące argumenty:
zabawa - funkcja reprezentująca równanie.
x0 – wstępne przypuszczenie dotyczące korzenia.
metoda - nazwa metody, która ma zostać użyta. Wartości prawne:
    'CG'
    'BFGS'
    'Newton-CG'
    'L-BFGS-B'
    'TNC'
    'COBYLA'
    'SLSQP'
callback - funkcja wywoływana po każdej iteracji optymalizacji.
opcje - słownik definiujący dodatkowe parametry:
```
{
     "disp": boolean - print detailed description
     "gtol": number - the tolerance of the error
  }
```
```
# Przykład: Zminimalizuj funkcję x^2 + x + 2za pomocą BFGS:
from scipy.optimize import minimize

def eqn(x):
  return x**2 + x + 2
mymin = minimize(eqn, 0, method='BFGS')
print(mymin)
```

# SciPy Sparse Data
Co to są rzadkie dane? Dane rzadkie to dane, które zawierają w większości niewykorzystane elementy (elementy, które nie niosą żadnych informacji).
Może to być tablica taka jak ta:
```
[1, 0, 2, 0, 0, 3, 0, 0, 0, 0, 0, 0]
```
Dane rzadkie: to zbiór danych, w którym większość wartości pozycji wynosi zero.
Dense Array: jest przeciwieństwem rzadkiej tablicy: większość wartości nie wynosi zero.

Jak pracować z rzadkimi danymi? SciPy posiada moduł scipy.sparse udostępniający funkcje radzenia sobie z rzadkimi danymi. Istnieją przede wszystkim dwa typy rzadkich macierzy, których używamy:

CSC – skompresowana rzadka kolumna. Do wydajnej arytmetyki i szybkiego dzielenia kolumn.
CSR — skompresowany rzadki wiersz. Do szybkiego krojenia rzędów, szybsze produkty wektorów macierzowych
W tym samouczku użyjemy macierzy CSR.

Matryca CSR - Możemy utworzyć macierz CSR, przekazując tablicę do funkcji scipy.sparse.csr_matrix().
```
# Przykład: Utwórz macierz CSR z tablicy:
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([0, 0, 0, 0, 0, 1, 1, 0, 2])

print(csr_matrix(arr))
```
Z wyniku widzimy, że istnieją 3 elementy posiadające wartość.
Element 1. znajduje się na 0pozycji wiersza 5i ma wartość 1.
Pozycja 2. znajduje się na 0pozycji wiersza 6i ma wartość 1.
Pozycja 3. znajduje się na 0pozycji wiersza 8i ma wartość 2.

Metody macierzy rzadkich - Przeglądanie przechowywanych danych (nie pozycji zerowych) za pomocą datawłaściwości:
```
# Przykład:
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([[0, 0, 0], [0, 0, 1], [1, 0, 2]])

print(csr_matrix(arr).data)
```
Liczenie niezerowych metodą count_nonzero():
```
# Przykład:
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([[0, 0, 0], [0, 0, 1], [1, 0, 2]])

print(csr_matrix(arr).count_nonzero())
```
Usuwanie wpisów zerowych z macierzy metodą eliminate_zeros():
```
# przykład:
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([[0, 0, 0], [0, 0, 1], [1, 0, 2]])

mat = csr_matrix(arr)
mat.eliminate_zeros()

print(mat)
```
Eliminacja duplikatów wpisów metodą sum_duplicates():
```
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([[0, 0, 0], [0, 0, 1], [1, 0, 2]])

mat = csr_matrix(arr)
mat.sum_duplicates()

print(mat)
```
Konwersja z csr na csc metodą tocsc():
```
import numpy as np
from scipy.sparse import csr_matrix

arr = np.array([[0, 0, 0], [0, 0, 1], [1, 0, 2]])

newarr = csr_matrix(arr).tocsc()

print(newarr)
```
Oprócz wspomnianych rzadkich operacji specyficznych, rzadkie macierze obsługują wszystkie operacje, które obsługują normalne macierze, np. przekształcanie, sumowanie, arytmetykę, nadawanie itp.

# SciPy Graphs
Praca z wykresami - Wykresy są istotną strukturą danych. SciPy udostępnia nam moduł scipy.sparse.csgraphdo pracy z takimi strukturami danych.
Macierz sąsiedztwa - Macierz sąsiedztwa to nxnmacierz, w której n jest liczba elementów grafu. A wartości reprezentują połączenie między elementami.
Dla takiego wykresu, z elementami A, B i C, połączenia są następujące:
A i B są powiązane z wagą 1.
A i C są połączone z wagą 2.
C i B nie są podłączone.
Macierz przylegania wyglądałaby następująco:
```
      ABC 
   A:[0 1 2]   
   B:[1 0 0] 
   C:[2 0 0]
```

Poniżej przedstawiono niektóre z najczęściej używanych metod pracy z macierzami sąsiedztwa.
Połączone komponenty - Znajdź wszystkie połączone komponenty za pomocą connected_components()metody.
```
import numpy as np
from scipy.sparse.csgraph import connected_components
from scipy.sparse import csr_matrix

arr = np.array([
  [0, 1, 2],
  [1, 0, 0],
  [2, 0, 0]
])

newarr = csr_matrix(arr)

print(connected_components(newarr))
```

Dijkstra - Użyj tej dijkstrametody, aby znaleźć najkrótszą ścieżkę na grafie od jednego elementu do drugiego.
Przyjmuje następujące argumenty:
return_predecessors: boolean (prawda, aby zwrócić całą ścieżkę przejścia, w przeciwnym razie fałsz).
indeksy: indeks elementu, który zwraca wszystkie ścieżki tylko z tego elementu.
limit: maksymalna waga ścieżki.
```
# Przykład: Znajdź najkrótszą ścieżkę od elementu 1 do 2:
import numpy as np
from scipy.sparse.csgraph import dijkstra
from scipy.sparse import csr_matrix

arr = np.array([
  [0, 1, 2],
  [1, 0, 0],
  [2, 0, 0]
])

newarr = csr_matrix(arr)

print(dijkstra(newarr, return_predecessors=True, indices=0))
```
