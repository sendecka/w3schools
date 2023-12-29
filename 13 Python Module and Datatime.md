# <p style="text-align: center;">Python Module </p>

## Co to jest moduł ?
Plik zawierający zestaw funkcji, które chcesz zawrzeć w swojej aplikacji.

- Utwórz moduł - aby utworzyć moduł, zapisz żądany kod w pliku z rozszerzeniem .py
- Użyj moduły - możesz zaimportować moduł i wywołać funkcję.
```
import mymodule
mymodule.greeting("Jonathan")
```
- Zmienne w module - moduł może zawierać funkcje, ale także zmienne wsystkich typów (tablice, słowniki, obiekty).
- Nazywanie modułu - można nazwać pliki modułu dowolną nazwą ale musi mieć rozszerzenie .py
- Zmiana nazwy modułu - możesz utworzyć alias podczas importu pliku używając as.
```
import mymodule as mx
a = mx.person1["age"]
print(a)
```
- Wbudowane moduły - istnieje kilka wbudowanych modułów, które można zaimportować w dowolnym momencie.
- Korzystanie z funkcji dir() - istnieje wbudowana funkcja wyświetlająca listę wszystkich nazw funkcji (lub nazw zmiennych) w module.
```
import platform
x = dir(platform)
print(x)
```
- Importuj z modułu - możesz zaimportować tylko część z modułu używając słowa kluczowego from.
```
from mymodule import person1
print (person1["age"])
```

# <p style="text-align: center;">Python Datatime </p>

## Daty w Python

Data nie jest samodzielnym typem danych, ale możemy zaimplementować moduł o nazwie umożliwiającej datatime pracę z danymi jako obiektami danych.

Zaimportuj moduł datatime i wyświetl bieżącą datę.
```
import datetime
x = datetime.datetime.now()
print(x)
```
- dane wyjściowe - kiedy wykonamy kod z powyższego przykładu wynikiem będzie 2023-09-24 14:15:45.268539 Data będzie zawierać rok,miesiąc, dzień, godzinę, minutę i mikrosekundę. Moduł datatime posiada wiele metod zwracających informację o obiekcie daty. Oto kilka z nich.
```
import datetime
x = datetime.datetime.now()
print(x)
```
- Tworzenie obiektów daty - do stworzenia daty możemy wykorzystać datatime() klasę (konstruktora) moduł datatime. Wymaga ona trzech parametrów, abyutworzyć datę: rok, miesiąc i dzień.
```
import datetime
x = datetime.datetime(2020, 5, 17)
print(x)
```
Klasa datatime() przyjmóje również parametry czasu i strefy czasowej, ale sąone opcjonalne i mają domyślną wartość 0.

- Metoda strftime() - obiekt datatime posiada metodę formatowania obiektów daty w czytelne ciągi znaków. Metoda nazywa się strftime() i przyjmuje jeden parametr format, określający format zwracanego ciągu.
```
import datetime
x = datetime.datetime(2018, 6, 1)
print(x.strftime("%B"))
```
Istnieje szereg odniesień do wszystkich kodów formatu.


