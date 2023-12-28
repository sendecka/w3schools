# <p style="text-align: center;">Python Arrays </p>

Python nie ma wbudowanej obsługi tablic, ale zamiast tego można używać list Pythona. Można używać list zamiast tablic, ale trzeba zaimportować bibliotekę, taką jak biblioteka NumPy.
```
cars = ["Ford", "Volvo", "BMW"]
```
Co to jest tablica? - to specjalna zmienna, która może przechowywać więcej niż jedną wartość na raz. Jeśli masz listę elementów przechowanie ich w oddzielnych elementach ,oże być niewygodne. Tablica może przechowywać wiele wartości pod jedną nazwą, a dostęp do wartości można uzyskać odwołując się do numeru indeksu.
- Uzyskaj dostęp do elementów ablicy - odwołujesz się za pomocą numerów indeksów.
```
x = cars[0]
```
- Długośc tablicy - użyj len(), aby zwrócić długość tablicy.
```
x = len(cars)
```
- Zapętlone elementy tablicy - za pomocą pętli for in możesz przeglądać wszystkie elementy tablicy.
```
for x in cars:
  print(x)
```
- Dodawanie elementów tablicy - możesz użyć append() metody aby dodać elementy do tablicy.
```
cars.append("Honda")
```
- Usówanie elementów z tablicy - możesz użyć pop(), aby usunąć elementy z tablicy. Możesz również użyć remove(), by usunąć elementy z tablicy.
```
cars.pop(1)
cars.remove("Volvo")
```

Metody tablicy - zestaw wbudowanych metod tablicowych.
> - append()
> - clear()
> - copy()
> - count()
> - extend()
> - index()
> - insert()
> - pop()
> - remove()
> - reverse()
> - sort()


# <p style="text-align: center;">Python Classes and Objects </p>
Klasy / Obiekty Python - Python jest obiektowym językiem programowania. Prawie wszystko jest obiektem z jego właściwościami i metodami. Klasa przypomina konstruktor obiektów lub plan tworzenia obiektów.
- Utwórz klasę - użyj słowa kluczowego class
```
class MyClass:
  x = 5
```
- Utwórz obiekt - możemy używać klasy do tworzenia obiektów.
```
p1 = MyClass()
print(p1.x)
```
Funkcja __int__() - powyższe przykłady to klasy i obiekty w najprostrzej formie, które nie są zbyt przydatne w rzeczywistych zastosowaniach. Aby zrozumieć znaczenie klas, musimy zrozumieć wbudowaną funkcję __int__(). Wszystkie klasy mają funkcję o nazwie __int__(), która jest zawsze wykonywana podczas inicjowania klasy. Użyj funkcji __int__() aby przypisać wartości do właściwości obiektu lub innych operacji, które są niezbędne do wykonania podczas tworzenia obiektu.

- Utwórz klasę o nazwie Person i użyj funkcji __int__() aby przypisać wartość do imienia i wieku.
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("John", 36)

print(p1.name)
print(p1.age)
```

Funkcja __str__() - kontroluje, co powinno zostać zwrócone gdy obiekt klasy jest reprezentowany jako ciąg znaków. Jeżeli funkcja __str__() nie jest ustawiona to, zwracany jest ciąg znaków reprezentujących obiekt.
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("John", 36)

print(p1)
```
- Metody obiektowe - obiekty również mogą zawierać metody. Metody w obiektach to funkcje należące do obiektu.
```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("John", 36)
p1.myfunc()
```
- Parametr własny - parametr self jest odniesieniem do bieżącej instalacji klasy i służy do uzyskiwania dostępu do zmiennych należących do klacy. NIe musi mieć nazwy self można jąnazwać dowolnie, ale musi to być pierwszy parametr dowolnej funkcji w klasie.
```
class Person:
  def __init__(mysillyobject, name, age):
    mysillyobject.name = name
    mysillyobject.age = age

  def myfunc(abc):
    print("Hello my name is " + abc.name)

p1 = Person("John", 36)
p1.myfunc()
```
- Zmodyfikuj właściwości obiektu - możesz modyfikować właściwości obiektu.
```
p1.age = 40
```
- Usuń właściwości obiektu - za pomocą del
```
del p1.age
```
- Oświadczenie dotyczące przepustki - class definicje nie mogą być puste, jeżeli z jakiegoś powodu masz definicję class bez treści umieść jąw pass, aby uniknąć błędu.
```
class Person:
  pass
```
