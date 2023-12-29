# <p style="text-align: center;">Python Polymorphism </p>

Słowo "polimorfizm" oznacza wiele form, a w programowaniu odnosi się do metod/funkcji/operatorów o tej samej nazwie, które możnawykonać na wielu obiektach lub klasach.

- Polimorfizm funkcji - przykładem funkcji Pythona, której można używać na różnych obiektach, jest funkcja len().

## String - w przypadku ciągów len() zwraca liczbęznaków
```
x = "Hello World!"
print(len(x))
# 12
```

## Krotka - w przypadku krotki len() zwracana jest liczba elementów w krotce.
```
mytuple = ("apple", "banana", "cherry")
print(len(mytuple))
# 3
```

## Słownik - W przypadku słownika len() zwracana jest liczba par klucz/wartość w słowniku.
```
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
print(len(thisdict))
# 3
```

## Polimorfizm klas
Jest często używany w metodach klasowych, gdzie możemy mieć wiele klas o tej samej nazwie metody. Załóżmy na przykład, że mamy trzy klasy: Car, Boati Plane, i wszystkie mają metodę zwaną move():
```
class Car:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Drive!")

class Boat:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Sail!")

class Plane:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Fly!")

car1 = Car("Ford", "Mustang")       #Create a Car class
boat1 = Boat("Ibiza", "Touring 20") #Create a Boat class
plane1 = Plane("Boeing", "747")     #Create a Plane class

for x in (car1, boat1, plane1):
  x.move()
```

Spójrz na pętlę for na końcu. Ze względu na polimorfizm możemy wykonać tę samą metodę dla wszystkich trzech klas.

## Polimorfizm klas dziedziczenia

A co z zajęciami z klasami podrzędnymi o tej samej nazwie? Czy możemy tam zastosować polimorfizm?
Tak. Jeśli użyjemy powyższego przykładu i utworzymy klasę nadrzędną o nazwie Vehicle, i stworzymy Car, klasy podrzędne , klasy podrzędne dziedziczą metody, ale mogą je zastąpić Boat:PlaneVehicleVehicle
```
class Vehicle:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Move!")

class Car(Vehicle):
  pass

class Boat(Vehicle):
  def move(self):
    print("Sail!")

class Plane(Vehicle):
  def move(self):
    print("Fly!")

car1 = Car("Ford", "Mustang") #Create a Car object
boat1 = Boat("Ibiza", "Touring 20") #Create a Boat object
plane1 = Plane("Boeing", "747") #Create a Plane object

for x in (car1, boat1, plane1):
  print(x.brand)
  print(x.model)
  x.move()
```

Klasy podrzędne dziedziczą właściwości i metody z klasy nadrzędnej. W powyższym przykładzie widać, że Carklasa jest pusta, ale dziedziczy brand, modeli move()po Vehicle.
Klasy Boati Planerównież dziedziczą brand, modeli move()from Vehicle, ale obie zastępują move()metodę. Ze względu na polimorfizm możemy wykonać tę samą metodę dla wszystkich klas.


# <p style="text-align: center;">Python Scope </p>

Zmienna jest dostępna tylko w regionie w którym została utworzona, nazywa sięto zakres. 

## Zakres lokalny
Zmienna utworzona wewnątrz funkcji należy do lokalnego zakresu tej funkcji i może być użyta tylko wewnątrz tej funkcji.
```
def myfunc():
  x = 300
  print(x)

myfunc()
```
## Funkcja wewnątrz funkcji
Dostęp do zmiennej lokalnej można uzyskać z funkcji znajdującej sięwewnątrz funkcji.
```
def myfunc():
  x = 300
  def myinnerfunc():
    print(x)
  myinnerfunc()

myfunc()
```

## Zakres globalny 
Zmienna utworzona w głównej częsci kodu jest zmienną globalną i należy do zasięgu globalnego. Zmienne globalne są dostępne w dowolnym zakresie globalnym i lokalnym.
```
x = 300
def myfunc():
  print(x)
myfunc()

print(x)
```

## Nazywanie zmiennych
Jeśli operujesz tą samą nzawż zmiennej wewnątrz i na zewnątrz funkcji, Python potraktuje je jako dwie osobne zmienne, jedną dostępną w zasięgu globalnym(poza funkcją) i drugą dostępną w zasięgu lokalnym (wewnątrz funkcji).
```
x = 300

def myfunc():
  x = 200
  print(x)
myfunc()

print(x)
```

## Globalne słowo kluczowe
Jeśli chcesz utworzyć zmienną globalną, ale utkniesz w zasięgu lokalnym, możesz użyć słowa global.
```
def myfunc():
  global x
  x = 300
myfunc()

print(x)
```
Użyj słowa kluczowego global, jeśli chcesz dokonać zmiany w zmiennej globalnej wewnątrz funkcji.
```
x = 300

def myfunc():
  global x
  x = 200
myfunc()

print(x)
```
