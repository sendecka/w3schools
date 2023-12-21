# <p style="text-align: center;">Python Tuples </p>

### Python Tuple:
Krotki służą do przechowywania wielu elementów w jednej zmiennej. To jeden z 4 wbudowanych typów danych w Python używanych do przechowywania kolekcji danych.Krotki to zbiór uporządkowany i niezmienny. Zapisuje sięje w nawiasach okrągłych.
```
thistuple = ("apple", "banana", "cherry")
print(thistuple)
```
- elementy są uporządkowane, niezmienne i pozwalają na powielanie wartości. Elementy są indeksowane, pierwszy ma indeks [0], drugi ma indeks [2],
- kiedy mówimy, że elementy są uporządkowane, oznacza to, że elementy mają określoną kolejność i ta kolejność sięnie zmieni
- elementy sąniezmienne, co oznacza, że nie możemy zmienić , dodać ani usunąć elementów po utworzeniu krotki
- ponieważ elementy są indeksowane to mogą zawierać elementy o tej samej wartości
- aby określić ilość elementów użyj len()
```
thistuple = ("apple", "banana", "cherry")
print(len(thistuple))
```
- aby utworzyćkrotkęz jednym elementem należy po elemencie dodać przecinek, w przeciwnym razie Python nie rozpozna go jako krotki
```
thistuple = ("apple",)
print(thistuple)
```
- elementy krotki mogą mieć dowolny typ danych
- z perspektywy python krotka definiowana jest jako obiekt z typem danych tuple

### Python Tuple dostęp:
- uzyskaj dostęp do elementów krotki odwołując się do numeru indeksu w nawiasach kwadratowych
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[1])
```
- indeksowanie negatywne - indeksowanie ujemne oznacza rozpoczęcie od końca -1 oznacza ostatnią pozycję
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[-1])
```
- zakres indeksów - można określić, określając gdzie zaczyna się i gdzie kończy zakres. Podczas określania zakresu wartości zwracana będzie nowa krotka z określonymi elementami.
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[1:2])
```
- pominięcie wartości początkowej sprawi, że zakres zacznie się od pierwszego elementu
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[ :2])
```
- pominięcie wartości końcowej sprawi, że zakres będzie przesunięty do końca
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[1: ])
```
- zakres indeksów ujemny
```
thistuple = ("apple", "banana", "cherry")
print(thistuple[-1:-2])
```
- sprawdź czy element występuje w krotce - użyj słowa in
```
if "apple" in thistuple :
print("Yes")
```

### Python Tuple update:
- krotki są niezmienne, co oznacza, że po utworzeniu nie można ich zmienić, dodawać ani usuwać. Są jednak pewne obejścia
- zmień wartość krotki - możesz przekonwertować krotkęna listę, zmienić listę i przekonwertować spowrotem na krotkę
```
x = ('apple, 'banana', 'cherry')
y = list(x)
y[1] = 'kiwi'
x = tuple(y)
print(x)
```
- Dodaj elementy - są inne sposoby aby dodać elementy do krotki:
  > - konwertuj na listę
  ```
  thistuple = ("apple", "banana", "cherry")
  y = list(thistuple)
  y.append("orange")
  thistuple = tuple(y)
  ```
  > - dodaj krotkędo krotki
  ```
  thistuple += y
  print(thistuple)
  ```
- Usuń elementy - tak samo jak wyżej
```
y = remove("apple")
thistuple = tuple(y)
```
- Całkowite usunięcie
```
del(thistuple)
```
### Python Unpack Tuple:
- Unpacking Tuple - kiedy tworzymy krotkię, zwykle przypisujemy jej wartości. Nazywa sięto pakowaniem krotki.
```
fruits = ('apple', 'banana', 'cherry')
```
- W Pythonie możemy również rozpakować wartości z powrotem do zmiennych.
```
fruits = ("apple", "banana", "cherry")

(green, yellow, red) = fruits

print(green)
print(yellow)
print(red)
```
- Liczba zmiennych musi odpowiadać liczbie wartości w krotce w przeciwnym razie należy użyć gwiazdki, aby zebrać pozostałe wartości w formie listy.
- Korzystanie z * -
