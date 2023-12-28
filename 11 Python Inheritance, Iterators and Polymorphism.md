# <p style="text-align: center;">Python Inheritance </p>

Dziedziczenie w Python - dziedziczenie pozwala nam zdefiniować klasę, która dziedziczy wszystkie metody i właściwości z innej klasy. Klasa nadrzędna - to klasa, z której siędziedziczy, zwana także bazową klasą podrzędną - to klasa, która dziedziczy z innej klacy, zwana pochodną.

- Utwórz klasę nadrzędną - dowolna klasa może być nadrzędną, więc składnia jest taka sama jak przy tworzeniu dowolnej innej klacy.
```
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

#Use the Person class to create an object, and then execute the printname method:

x = Person("John", "Doe")
x.printname()
```
- Utwórz klasę podrzędną - aby utworzyć klasę dziedziczącą funkcjonalność z innej klasy, podczas tworzenia klasy podrzędnej wyślij klasę nadrzędną jako parametr. Teraz klasa student ma te same właściwości i metody co Person.
```
class Student(Person):
  pass
```
- Dodaj funkcję __init__() - jak dotąd stworzyliśmy klasę potomną, która dziedziczy właściwości i metody od swojego rodzica. Chcemy dodać __init__() funkcję do klasy potomnej (zamiast pass słowa kluczowego).
```
class Student(Person):
  def __init__(self, fname, lname):
    #add properties etc.
```
- Funkcja __init__() - jest wywołana automatycznie za każdym razem, gdy klasa jest używana do tworzenia nowego obiektu. Po dodaniu init klasa podrzędna nie będzie już dziedziczyć funkcji rodzica. Aby zachować dziedziczenie funkcji rodzica __init__(), dodaj wywołanie funkcji rodzica __init__().
```
class Student(Person):
  def __init__(self, fname, lname):
    Person.__init__(self, fname, lname)
```
- Użyj funkcji super() - sprawi, że klasa potomna odziedziczy wszystkie metody i właściwości od swojego rodzica.
```
class Student(Person):
  def __init__(self, fname, lname):
    super().__init__(fname, lname)
```
- Używając funkcji super() musisz używać nazwy elementu rodzica automatycznie odziedziczy on metody i właściwości od rodzica.



# <p style="text-align: center;">Python Iterators </p>

Iteratory Python - iteratory to obiektu posiadające policzalną liczbę wartości. Iteratory to obiekty, po których można iterować, co oznacza, żę można przechodzić przez wszystkie wartości. Technicznie rzecz biorąc, w Python iterator to obiekt implrmrntujący protokół iteratora, na który składa się metody __iter__() i __next__().

Iterator kontrola iterowalności - listy, krotki, słowniki i zbiory są obiektami iterowalnymi. Są to iterowalne kontenery z których można uzyskać iterator. Wszystkie te obiekty posiadają iter(), metodę służącą do uzyskania iteratora.

```
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit))
print(next(myit))
print(next(myit))
```
- Pętla poprzez iterator - możemy użyć pętli for do iteracji po obiekcie.
```
mytuple = ("apple", "banana", "cherry")

for x in mytuple:
  print(x)
```
- Utwórz iterator - aby utworzyć obiekt / klasę jako iterator musisz zaimportować metody __iter__() i __next__() do swojego obiektu. Metoda __iter__() - możesz wykonać operację (inicjowanie), ale zawsze musisz zwrócić sam obiekt iteratora. Metoda __next__() umożliwia także wykonanie operacji i musi zwracać kolejny element w sekwencji.
- Utwórz iterator, który zwraca liczby od 1, a każda sekwencja będzie zwiększona o jeden.
```
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```
- Zatrzymaj iterację - 
