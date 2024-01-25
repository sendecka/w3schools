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

