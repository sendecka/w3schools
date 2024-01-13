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
Utwórz etykietę - za pomocą argumentu index możesz nazwać własne etykiety.
```
import pandas as pd
a = [1, 7, 2]
myvar - pd.Series(a, index = ["x", "y", "z"])
print(myvar)
```
Po utworzeniu etykiety można odwołaś cię do elementu za pomocą etykiety.
```
print(myvar["y"]
```
Obiekty kluczowe \ wartościowe jako serie - podczas tworzenia serii możesz także użyć obiektu klucza \ wartości, takiego jak słownik.
```
import pandas as pd
calories = {"day1": 420, "day2": 390}
myvar = pd.Series(calories)
print(myvar)
```
Aby wybrać tylko część pozycji ze słownika, użyj index argumentu i określ tylko te pozycje, które chcesz uwzględnić w serii.
```
myvar = pd.Series(calories, index=["day1", "day2"]
```
Ramki danych - zestawy danych w Pandas to zazwyczaj wielowymiarowe tabele, zwane DataFrame. Seria jest jak kolumna, DataFrame jak cała tabela.
```
import pandas as pd
data = {
    "calories": [420, 380, 390]
    "duration": [50, 40, 45]
}
myvar = pd.DataFrame(data)
print(myvar)
```

## Pandas DataFrame
Pandas DataFrames to dwuwymiarowa struktura danych, podobna do dwuwymiarowej tablicy lub tabeli z wierszami i kolumnami.
```
import pandas as pd
data = {
    "calories": [420, 380, 390]
    "duration": [50, 40, 45]
}
df = pd.DataFrame(data)
print(df)
```
Znajdź wiersz - jak widać z powyższego wyniku, DataFrame przypomina tabelę z wierszami i kolumnami. Pandas używa atrybut loc, aby zwrócić jeden lub więcej określonych wierszy.
```
print(df.loc[0])
```


