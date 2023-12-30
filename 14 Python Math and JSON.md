# <p style="text-align: center;">Python MATH </p>

Python posiada zestaw wbudowanych funkcji matematycznych, w tym rozbudowany moduł matematyczny, pozwalający na wykonywanie zadań matematycznych na liczbach.
- Wbudowane funkcje matematyczne - funkcje min() i max() można użyć do znajdywania najniższej lub najwyższej wartości.
```
x = min(5, 10, 25)
y = max(5, 10, 25)

print(x)
print(y)
```
- Funkcja abs() - zwraca wartość bezwzględną (dodatnią) podanej liczby.
```
x = abs(-7.25)
print(x)
```
- Funkcja zwraca wartość x do potęgi y.
```
x = pow(4, 3)
print(x)
```
- Moduł matematyczny - Python posiada wbudowany moduł o nazwie math, który rozszeża listę funkcji matematycznych. Aby z niego skorzystać należy zaimportować math moduł.
```
import math
```
- Metoda math.sqrt() zwraca pierwiastek kwadratowy z liczby.
```
import math
x = math.sqrt(64)
print(x)
```
- Metoda math.celi() - zaokrągla liczbę w górę do najbliższej liczby całkowitej, a math.floor() zaokrągla w dół do najbliższej liczby całkowitej.
```
import math

x = math.ceil(1.4)
y = math.floor(1.4)

print(x) # returns 2
print(y) # returns 1
```
- Stała math.pi zwraca pi (3.14)
```
import math
x = math.pi
print(x)
```
Istnieje wiele innych odniesień matematycznych osobny dział.

# <p style="text-align: center;">Python JSON </p>

- JSON - to składnia służąca do przechowywania i wymiany danych. To tekst zapisany w notacji obiektowej JavaScript.
- Python ma wbudowany pakiet o nazwie json, którego można używać do pracy z danymi.
```
import json
```
- Parse Json - konwertuj z json na Python. Jeśli masz ciąg JSON możesz go przeanalizować za pomocą json.loads(). Wynikiem będzie słownik Python.
```
import json
# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'
# parse x:
y = json.loads(x)
# the result is a Python dictionary:
print(y["age"])
```
- Konwertuj z Python na JSON dzięki json.dumps().
```
import json
# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'
# parse x:
y = json.loads(x)
# the result is a Python dictionary:
print(y["age"])
```
Podczas konwersji z Python na JSON obiekty są konwertowane na odpowiednik JSON (Java Script)
> - dict
> - list
> - tuple
> - string
> - int
> - float
> - True
> - False
> - None

Sformatuj wynik - powyższy przykład drukuje ciąg JSON, ale nie jest on zbyt łatwy do odczytania, bez wcięć i podziałów wiersza metoda json.dumps() posiada parametry ułatwiająca odczytanie wyniku.
```
json.dumps(x, indent=4)
```
Możesz także zdefiniować separatory, wartość domyślna to (", ", ": "), co oznacza użycie przecinka i separacji do oddzielenia poszczególnych obiektów oraz dwukropka i spacji do oddzielenia kluczy od wartości.
Użyj separatora parametru, aby zmienić domyślny separator.
```
json.dumps(x, indent=4, separators=(". ", " = "))
```
Order the Result - metoda json.dumps() posiada parametry umożliwiająca uporządkowanie kluczy w wyniku. Użyj tego parametru, aby określić, czy wynik powinien być posortowany czy nie.
```
json.dumps(x, indent=4, sort_keys=True)
```
