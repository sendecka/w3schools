# <p style="text-align: center;">Python Functions </p>

Funkcja to blok kodu, który działa tylko wtedy gdy zostanie wywołany. Do funkcji można przekazać dane zwane parametrami. W rezultacie funkcja może zwrócić dane.

- Tworzenie funkcji - jest definiowana jako słowo kluczowe def:
```
def my_function():
  print("Hello from a function")
```
Wywołanie funkcji - użyj nazwy funkcji i nawiasu.
```
my_function()
```
- Argumenty - można przekazywać informacje do funkcji jako argumenty. Argumenty podaje siępo nazwie funkcji w nawiasach. Możeszdodać dowolną ilość argumentów, wystarczy oddzielić je przecinkiem. Poniższy przykład ma funkcję z 1 argumentem (fname). Przy wywołaniu funkcji przekazujemy imię, które służy wewnątrz funkcji do wywołania połnego imienia i nazwiska.
```
def my_function(fname):
  print(fname + " Refsnes")

my_function("Emil")
my_function("Tobias")
my_function("Linus")
```
- Parametry czy argumenty? - terminów parametr i argument można używać do tego samego, informacji przekazywanych do funkcji. Z punktu widzenia funkcji parametr to zmienna wymieniona w nawiasach w definicji funkcji. Argument to wartość wysyłana do funkcji podczas jej wywołania.
- Liczba argumentów - domyślnie funkcja musi zostać wywołana z odpowiednią liczbą argumentów. Oznacza to, że jeśli funkcja oczekuje 2 argumentów, musi wywołać funkcję z 2 argumentami, nie więcej i nie mniej.
```
def my_function(fname, lname):
  print(fname + " " + lname)

my_function("Emil", "Refsnes")
```
- Arbitrary Arguments *args - jeśli nie wiesz ile argumentów zostanie przekazane do Twojej funkcji, dodaj * przed nazwą parametru w def. funkcji. W ten sposób funkcja otrzyma krotkę argumentów i będzie mogła uzyskać dostęp do elementów.
```
def my_function(*kids):
  print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
```
- Keywords arguments - możesz również wysłać argumenty ze składnią klucz = wartość. W ten sposób kolejność argumentów nie ma znaczenia.
```
def my_function(child3, child2, child1):
  print("The youngest child is " + child3)

my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```
- Arbitrary keyword arguments ** kwargs - jeśli nie wiesz ile argumentów słów kluczowych zostanie przekazanych do Twojej funkcji, dodaj dwie ** przed nazwą parametru w def. funkcji. W ten sposób funkcja otrzyma słownik elementów i będzie mogła uzyskać do nich dostęp.
```
def my_function(**kid):
  print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")
```
- Domyślna wartość parametru - jeśli wywołamy funkcję bez argumentu użyje ona wartości domyślnej.
```
def my_function(country = "Norway"):
  print("I am from " + country)

my_function("Sweden")
my_function("India")
my_function()
my_function("Brazil")
```
- Przekazywanie listy jako argumentów - możesz wysłać argumenty dowolnego typu do funkcji, a wewnątrz funkcji będzie on traktowany jako ten sam typ danych.
```
def my_function(food):
  for x in food:
    print(x)

fruits = ["apple", "banana", "cherry"]

my_function(fruits)
```
- Zwracana wartość - aby funkcja zwróciła wartość, użyj return instrukcji.
```
def my_function(x):
  return 5 * x

print(my_function(3))
print(my_function(5))
print(my_function(9))
```
- The pass - funkcja nie może być pusta, jeżeli masz pustą funkcję bez treści, umieść ją w instrukcji pass, aby uniknąć błędu.
```
def myfunction():
  pass
```
- Recursion - Python akceptuje rekursję funkcji, czyli zdefiniowana funkcja może wywołać samą siebie. Ma to tą zaletę, że można przeglądać dane w pętli aby osiągnąć wynik.
```
def tri_recursion(k):
  if(k > 0):
    result = k + tri_recursion(k - 1)
    print(result)
  else:
    result = 0
  return result

print("\n\nRecursion Example Results")
tri_recursion(6)
``` 
