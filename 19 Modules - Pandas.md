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
Nazwane indeksy - za pomocą argumentu index możesz nazwać własne indeksy.
```
import pandas as pd
data = {
    "calories": [420, 380, 390]
    "duration": [50, 40, 45]
}
df = df.DataFrame(data, index=["day1", "day2", "day3"])
print(df)
```
Znajdź nazwane indeksy - użyj atrybutu loc, aby zwrócić określone wiersze.
```
print(df.loc["day2"])
```
Załaduj plik do DataFrame - jeśli twoje dane są przechowywane w pliku, możesz je załadować jako DataFrame.
```
import pandas as pd
df = pd.read_csv("data.csv")
```

## Pandas Read CSV
Czytanie plików csv - prostym sposobem na przechowywanie dużych zbiorów danych są pliki csv. Zawierają one zwykły tekst i są dobrze znanym formatem, który może odczytać każdy.
Załaduj pliki scv do DataFrame. Użyj to_string(), aby wydrukować całą ramkę.
```
import pandas as pd
df = pd.read_csv("data.csv")
print(df.to_string())
```
Jeśli masz dużą ramkę z danymi DF zwróci 5 pierwszych wierszy i 5 ostatnich.
Max_rows - liczbę zwracanych wierszy definiuje się w ustawieniach opcjii Pandas. Możesz sprawdzić maksymalną liczbę wierszy w systemie za pomocą instrukcji pd.options.display.max_rows.
```
import pandas as pd
print(pd.options.display.max_rows)
```
Za pomocą tej samej funkcji można zmienić ustawienia. Zwiększ maksymalną liczbę wierszy, tak aby wyświetlić całą ramkę danych.
```
import pandas as pd
pd.options.display.max_rows = 9999
df = pd.read_csv("data.csv")
print(df)
```

## Pandas Read JSON
Duże zbiory danych są często przechowywane w formacie JSON. JSON to zwykły tekst, ale ma format obiektu i jest dobrze znany w świecie programowania.
```
import pandas as pd
df = pd.read_json("data.json")
print(df.to_string())
```
Użyj to_string() aby wydrukować całą ramkę danych DF.
Obiekty JSON mają ten sam format co słowniki Pythona.

## Pandas Analyzing DataFrame

Przeglądanie danych - jedną z najczęściej używanych metod szybkiego podglądu ramki DataFrame jest metoda head(). Zwraca ona nagłówki i określa liczbę wierszy, zaczynając od góry.
```
import pandas as pd
df = pd.read_csv("data.csv")
print(df.head(10))
```
Istnieje również metoda tail() do przeglądania ostatnich wierszy ramki DataFrame. Metoda tail() zwraca nagłówek i określa liczbę wierszy, zaczynając od dołu.
```
print(df.tail())
```
Informacje o danych - obiekt DataFrame posiada metodę o nazwie info(), która dostarcza więcej informacji o zbiorze danych.
```
print(df.info())
```
Wynik wyjaśniony - wynik mówi nam, że jest 169 wierszy i 4 kolumny oraz nazwa każdej z typem danych.
Warości zerowe - metoda info() mówi nam również ile wartości innych niż null znajduje się w każdej kolumnie, a w naszym zestawie danych wygląda na to, że w kolumnie "kalorie" znajdują się164 z 169 wartości innych niż null. Oznacza to, że z jakiegoś powoduw kolumnie "kalorie" znajduje się 5 wierszy bez żadnej wartości. Puste wartości lub null mogą być nieprawidłowe podczas analizy danych, dlatego należy rozważyć usunięcie wierszy z pustymi wartościami. Jest to krok w kierunku tak zwanego czyszczenia danych.

## Pandas - Czyszczenie danych

Czyszczenie danych - oznacza naprawianie błędnych danych w zestawie danych. Złymi danymi mogą być:
- puste komórki,
- dane z złym formacie,
- złe dane,
- duplikaty.

Nasz zestaw danych zawiera kilka pustych komórek(Data w wierszu 22 i kalorie w wierszu 18 i 28). Zbiór danych zawiera nieprawidłowy format (Data w wierszu 26). Zestaw danych zawiera błędne dane(czas trwania w wierszu 7). Zbiór danych zawiera duplikaty (wiersz 11 i 12).

## Pandas - Czyszczenie pustych komórek
Puste komurki mogą potencjalnie dać błędny wynik podczas analizy danych.
Usuń wiersze - jednym ze sposobów radzenia sobie z pustymi komórkami jest usunięcie wierszy zawierających puste komórki. Zwykle jest to w porządku, ponieważ zbiory danych mogą być bardzo duże, a usunięcie kilku wierszy nie będzie miało dużego wpływu na wynik.
```
# Przykład: zwróć nową ramkę danych bez pustych komórek
import pandas as pd
df = pd.read_csv("data.csv")
new_df = df.dropna()
print(new_df.to_string())
```
Domyślnie dropna() zwraca nową ramkę DataFrame i nie zmienia orginału.
Jeśli chcesz zmienić orginalną ramkę DataFrame, użyj argumentu inplace=True.
```
# Przykład: usuń wszystkie wiersze z wartością null
import pandas as pd
df = pd.read_csv("data.csv")
df = df.dropna(inplace=True)
print(df.to_string())
```
Teraz funkcja dropna (inplace=True) nie zwróci nowej ramki DataFrame ale usunie wszystkie wiersze zawierające wartość null z orginalnej ramki DataFrame.
Zmień puste wartości -innym sposobem radzenia sobie z pustymi komórkami jest wstawienie nowej wartości. W ten sposób nie musisz usuwać wierszy tylko z powodu pustych komórek. Metoda fillna() pozwala zastąpić puste komórki wartością.
```
# Przykład: zamień wartość null na 130
import pandas as pd
df = pd.read_csv("data.csv")
df.fillna(130, inplace=True)
```
Zmień tylko dla określonych kolumn - powyższy przykład zastępuje wszystkie puste miejsca w całej ramce danych. Aby zastąpić tylko puste wartości w jednej kolumnie, określ nazwę kolumny dla ramki DataFrame.
```
# Przykład: zamień wartość null w kolumnach "kalorie" na 130
import pandas as pd
df = pd.read_csv("data.csv")
df["calories"].fillna(130, inplace=True)
```
Zastąp używając średniej, mediany lub mode - powsechnym sposobem zastępywania pustych komórek jest obliczenie wartości średniej, mediany, mody kolumny. Pandas używa metod mean(), median(), mode() do obliczenia tych wartości.
mean()
```
# Przykład: oblicz średnią i zastąp nią puste wartości
import pandas as pd
x = df["calories"].mean()
df["calories"].fillna(x, inplace=True)
```
median()
```
# Przykład: oblicz medianę i zastąp nią puste wartości
import pandas as pd
x = df["calories"].median()
df["calories"].fillna(x, inplace=True)
```
mode()
```
# Przykład: oblicz medianę i zastąp nią puste wartości
import pandas as pd
x = df["calories"].mode()
df["calories"].fillna(x, inplace=True)
```
Czyszczenie danych w złym formacie - komórka zawierająca dane w złym formacie mogą utrudniać lub nawet uniemożliwić analizę danych. Aby to naprawić, masz dwie możliwości, usunąć wiersz lub przekonwertować komórki na sam format.
Konwertuj na podobny format - w ramce danych mamy dwie komórki o niewłaściwym formacie. Spróbujemy przekonwertować wszystkie komórki "daty" na daty. Pandas mają na to metodę to_datetime()
```
# Przykład: konwertuj do daty
import pandas as pd
df = pd.read_csv("data.csv")
df["date"] = pd.to_datetime(df["date"])
print(df.to_string())
```
Jak widać z wyniku, data w wierszu 26 została naprawiona, ale pusta data w wierszu 22 otrzymała wartość (nie czas), innymi słowy wartość pustą. Jednym ze sposobów radzenia sobie z pustymi wartościami jest ich usunięcie.
Usuwanie wierszy - wartość nał można traktować jako null, a za pomocą metody dropna() możemy usunąć wiersz.
```
# Przykład: usuń wiersz z null
df.dropna(subset=["data"], inplace=True)
```
## Pandas - Naprawianie błędnych danych

Złe dane - "błędne dane" nie muszą oznaczać "pustych komórek" lub "złego formatu", mogą być po prostu błędne, tak jak gdyby ktoś zarejestrował 199 zamiast 1.99. Czasami możesz wykryć błędne dane, patrząc na zbiór danych, ponieważ masz oczekiwania dotyczące tego, jakie powinny być. Jeśli spojrzysz na nasz zbiór danych, że we wierszu 7 czas trwania wynosi 450, ale dla wszystkich pozostałych wierszy czas trwania wynosi 30 do 60. NIe musi to być błąd, ale biorąc pod uwagę, że jest to zbiór danych dotyczących czyichś treningów, wnioskujemy z tego, że ta osoba nie ćwiczyła przez 450 min.

Zastępowanie wartości - jednym ze sposobów naprawienia błędnych wartości jest zastąpienie ich czymś innym. W naszym przykładzie jest to zapewne literówka i wartość powinna wynosić 45 zamiast 450.
```
# przykład: ustaw czas trwania na 45.
df.loc[7, "duration"] = 45
```
W przypadku małych zbiorów danych można zastępować dane jedne po drugich, ale nie w przypadku dużych zbiorów danych. Aby zastąpić błędne dane większymi zbiorami danych, możesz stworzyć pewne reguły np.: ustalić pewne granice dla wartości i zastąpić wszelkie wartości, które są poza granicami.
```
# przykład: przejżyj w pętli wszystkie wartości w kolumnie "Czas trwania". Jeśli wartość jest większa niż 120 ustaw jąna 120.
for x in df.index:
    if df.loc[x, "Duration"] > 120:
        df.loc[x, "Duration"] = 120
```
Usuwanie wierszy - inne postępowanie to usuwanie wierszy z błędami.
```
for x in df.index:
    if df.loc[x, "Duration"] > 120:
        df.drop(x, inplace = True)
```

## Pandas - Naprawianie usuwanie duplikatów

Odkrywanie duplikatów - 


