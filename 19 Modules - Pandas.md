# Pandas Tutorial
- Pandas to biblioteka pythona
- Służy do analizy danych

## Pandas Wprowadzenie
- Pandas to biblioteka Pythona używana do pracy ze zbiorami danych,
- Posiada funkcję analizowania, czyszczenia, eksplorowania i manipulacji danych,
- Została stworzona w 2008r przez Wesa McKinneya.

## Dlaczego warto używać pandas?
- Pozwala nam analizować duże zbiory danych i wyciągać wnioski w oparciu o teorie statystyczne,
- Może czyścić niechlujnie zestawy danych i sprawić, że będą czytelne i istotne,
- Odpowiednie dane są ważne w nauce danych.

## Co potrafi Pandas?
- Sprawdza czy istnieje koleracja między dwiema lub większą liczbą kolumn,
- Sprawdza jaka jest wartość średnia,
- Sprawdza jaka jest maksymalna wartość,
- Sprawdza wartość minimalną,
- Oczyszcza dane.

## Instalacja Pandas
Jeżeli masz zainstalowany Python i PIP w systemie, instalacja Pandas jest łatwa. Zainstaluj Pandas według tego polecenia:
```
C:\Users\Your Name\pip install pandas
```
Po zainstalowaniu Pandas zaimportuj go do swojej aplikacji
```
import pandas
```
Pandas jest zazwyczaj importowane jako pd (jako alians)
```
import pandas as pd
```
Teraz pakiet można używać jako pd zamiast Pandas.
Sprawdzenie wersjii pd 
```
print(pd.__version__)
```
Pandas Series - przypomina kolumnę w tabeli, jest to jednowymiarowa tablica przechowująca dane dowolnego typu.
```
import pandas as pd
a = [1, 7, 2]
myvar = pd.Series(a)
print(myvar)
```
Etykiety - jeśli nieokreślono inaczej, wartości są oznaczone numerem indeksu. Pierwsza wartość ma numer 0. Za pomocą tej etykiety można uzyskać dostęp do określonej wartości.
```
print(myvar[0])
```


