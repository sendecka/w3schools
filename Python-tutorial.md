# <p style="text-align: center;">Python tutorial </p>

### Python komentarze:
- mogą służyć do wyjaśnienia kodu,
- mogą służyć do zwiększenia czytelności kodu,
- mogą służyć do zapobiegania wykonywania kodu podczas testowania.

```
/#/ komentarz jednowierszowy
 """ comment """ komentarz wielowierszowy
```
### Python - Variables:
- zmienne są kontenerami do przechowywania danych,
- w python nie ma polecenia deklarowania zmiennych,
- zmienna jest tworzona w momęcie pierwszego przyisania jej wartości.

```
x = 5
y = "john"
print(x)
print(y)
```
- zmienne nie muszą być deklarowane z konkretnym typem, mogą zmieniać typ po ich ustanowieniu.

```
x = str(3)
y = int(3)
z = float(3)

print(x)
"3"
print(y)
3
print(z)
3.0
```
- za pomocą funkcji można uzyskać typ danych danej zmiennej type()
```
x = 5
print(type(x))

<class 'int'>
```
```
y = "John"
print(type(y))

<class 'str'>
```
- w nazwach zmiennych uwzględniana jest wielkość liter
```
a = 4
A = "Sally"
```
### Python - Variable names
- zmienna może mieć krótkąnazwę lub bardziej opisową,
- nazwa zmiennej musi sięzaczynać od litery lub _,
- nazwa zmiennej nie może zaczynać sięod cyfry,
- nazwa zmiennej może zawierać tylko znaki alfanumeryczne i podkreślenia,
- w nazwach jest rozróżniana wielkość liter,
- nazwa zmiennej nie może być słowem kluczowym języka Python,
- nazwy zmiennych mogą zawieraćwiele słów,
- istnieje możliwość przypisania wielu wartości do wielu zmiennych,
```
x, y, z = "Orange", "Banana", "Cherry"
print(x)
print(y)
print(z)
```
- można przypisać tą samą wartość do wielu zmiennych w jednym wierszu,
```
x = y = z = "Orange"
```
- rozpakowywanie kolekcji zmiennych.
```
fruits = ["Apple", "Banana", "Cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)
```
### Python - Output Variable 
- funkcja print() jest używana do wyprowadzania zmiennych,
```
x = "Python is awesome"
print(x)
```
- wyprowadzanie wielu zmiennych oddzielonych przecinkami,
```
x = "Python"
y = "is"
z = "awesome"
print(x,y,z)
```
- gdy spróbujesz połączyć ciąg znaków z liczbą za pomocą + wyświetli się błąd.
  
### Python - Global Variables
- zmienne utworzone poza funkcją są nazywane zmiennymi globalnymi,
- zmienne globalne mogą być używane przez każdego zarówno wewnątrz funkcji jak i poza,
- jeżeli utworzysz funkcjęo tej samej nazwie w funkcji, będzie ona lokalna i będzie ją można używać tylko wewnątrz funkcji.
- zmienna globalna o tej samej nazwie pozostaje niezmienna.

### Python - Global keyword
- zwykle gdy tworzysz zmienną wewnątrz funkcji możesz jej używać tylko wewnątrz funkcji,
- aby utworzyć zmienną globalną wewnątrz funkcji należy użyć słowa kluczowego global.
```
global x
x = "ok"
```

### Python - Data Types
- zmienne mogą przechowywać dane różnych typów, a różne typy mogą wykonać różne zadania,
- Python ma wbudowane następujące typy danych:
  Text type: str
  Numeric types: int, float, complex
  Sequence types: list, tuple, range
  Mapping type: dict
  Set types: set, frozenset
  Boolean type: bool
  Binary types: bytes, bytearray, memoryview
  Non types: Nontype

### Python - Getting the data type
- możesz sprawdzić typ danych za pomocą funkcji type()
```
x = 5
print(type(x))
```
- w Pythonie typ danych jest ustawiany podczas przypisania wartości do zmiennej,
- jeśli chcesz ustawić określony typ zmiennych możesz skorzystać z funkcji konstruktora
```
x = int(20)
y = str("Hello world")
```
### Python - Numbers
- są trzy typy numeryczne w Pythonie:
  Int - liczba całkowita dodatnia lub ujemna, bez miejsc dziesiętnych o nieograniczonej długości.
  ```
  x = 1
  print(x)
  ```
  Float - Liczba zmiennoprzecinkowa to liczba dodatnia lub ujemna zawierająca jedną lub więcej miejsc po przecinku.
  ```
  x = 1.1
  print(x)
  ```
  Complex - liczby zespolone, zapisuje się je z literą j jako część urojoną.
  ```
  x = 3+5j
  print(x)
  ```
  - można dokonać konwersji z jednego typu danych na inny metodą int(), float(), complex().
  - nie można konwertować liczb zespolonych na inne.

### Python - Random Number
  - Python nie ma random() funkcji do tworzenia liczb losowych, ale ma wbudowany moduł o nazwie random, którego można używać do tworzenia liczb losowych.
 ```
import random
print(random.randrange(1,10))
```

### Python - Casting
- można sięzdażyć, że trzeba będzie określić typ zmiennej. Można to zrobić za pomocą castingu. Python jest językiem obiektowym i jako taki używa klas do definiowania typów danych, w tym tyów pierwotnych.
- rzutowanie odbywa się za pomocą funkcji konstruktora:
  int() - konstruuje liczbęcałkowitą z literału całkowitego, literału zmiennoprzecinkowego(usuwa wszystkie miejsca dziesiętne) lub iterału łańcuchowego (pod warunkiem, zę reprezentuje liczbę całkowitą)
  float() - konstruuje zmienną zmiennoprzecinkową z literału całkowitego, zmiennoprzecinkowego lub literału łańcuchowego (pod warunkiem, że ciąg reprezentuje liczbę zmiennoprzecinkową lub liczbę całkowitą).
  str() - konstruuje ciąg znaków z szerokiej gamy typów danych w tym ciągów znaków, literałów całkowitych i iterałów zmiennoprzecinkowego.

### Python - Strings
- w Pythonie ciągi są ujmowane w "" lub ''
- ciągi wielowierszowe można przypisać do zmiennej używając trzech cudzysłowów """ lub trzech pojedyńczych cudzysłowów ''' w efekcie podział wiersza jest w tym samym miejscu co w kodzie.
- ciągi są tablicami, pojedyńczy znak to po prostu ciąg znaków o długości 1, aby uzyskać dostęp do znaków można użyć nawiasów kwadratowych (liczymy od 0)
```
a = "Hello world"
print(a[1])
```
- pętla przez ciąg, ponieważ ciągi znaków są tablicami, może przechodzić przez znaki w ciągu za pomocą pętli for.
```
for x in "banana": print(x)
```
- aby uzyskać długość łańcucha użyj len()
```
a = "Hello world"
print(len(x))
```
- aby sprawdzić czy w ciągu znaków występuje dana fraza lub znak, możemy użyć słowa kluczowego in
```
txt = "The best things in life are free!"
print("free" in txt)
True
```
- aby sprawczić czy dana fraza nie występuje w ciągu znaków użyj słowa not in
```
txt = "The best things in life are free!"
print("expensive" in txt)
True
```
  
