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
