# <p style="text-align: center;">Python If...Else </p>
### Warunki i instrukcje.
- Równa się: a == b
- Nierówna się: a != b
- Mniej niż: a < b
- Mniejsze lub równe: a <= b
- Większe niż: a > b
- Większe lub równe: a >= b
Instrukcja if jest zapisywana przy użyciu słowa kluczowego if.
```
a = 33
b = 200
if b > a :
  print("b is bigger then a")
```
Python opiera się na wcięciach (białych znakach na początku linii) aby zdefiniować zakres w kodzie. Instrukcja if bez wcięć będzie zgłaszać błąd.

- Elif - słowo kluczowe elif to sposób pythona na powiedzenia "jeśli poprzednie warunki nie były prawdziwe, wypróbuj ten warunek".
```
a = 33
b = 200
if b > a :
  print("b is bigger then a")
elif a == b:
  print("a and b are equal")
```
- W przeciwnym razie -słowo kluczowe else przechowuje wszystko co nie jest ujęte w powyższych warunkach. Można również mieć else bez elif.
```
a = 33
b = 200
if b > a :
  print("b is bigger then a")
else:
  print("a is greater than b")
```
- Krótkie if else - jeśli masz tylko jedną instrukcję do wykonania umieść ją w tym samym wierszu co instrukcję if.
```
if a > b : print("a is greater than b")
```
- Short hand If ... Else - Jeśli masz tylko jedną instrukcję do wykonania, jedną dla if i jedną dla else umieść ją w tym samym wierszu.
```
a = 2
b = 330
print("A") if a > b else print("b")
```
- Można umieścić jedną linię instrukcji if else z 3 warunkami.
```
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
```
### And
Operator logiczny służący do łączenia instrukcji warunkowych.
```
a = 200
b = 33
c = 500
if a > b and c > a :
  print("Oba warunki to True")
```

### Or
Operator logiczny służący do łączenia instrukcji (lub)
```
if a > b or a > c :
  print("conajmniej jeden warunek to true")
```

### Not 
Służy do odwrócenia wyniku instrukcji warunkowej.
```
a = 33
b = 200
if not a > b :
  print("a nie jest większe niż b")
```

### Nasted If
zagnieżdżenie instrukcji w instrukcji
```
x = 41
if x > 10 :
  print("powyżej")
    if x > 20 :
      print("również powyżej 20")
    else :
      print("ale nie powyżej 20")
```
- Instrukcje if nie mogą być puste, jeśli masz instrukcję if bez treści wstaw pass aby uniknąć błędu.
