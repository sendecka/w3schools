# <p style="text-align: center;">Python While Loops </p>

Python ma dwie proste polecenia pętli.
- While Loops
- For Loops

### While Loops
Za jej pomocą możemy wykonać zestaw instrukcji o ile warunek jest spełniony.
```
i = 1
while i < 6 :
  print(i)
  i += 1
```
Oświadczenie o przerwie - za pomocą instrukcji break możemy zatrzymać pętlę nawet jeśli warunek jest prawdziwy.
```
i = 1
while i < 6 :
  print(i)
  if i == 3 :
  break
  i += 1
```
- Kontynuacja oświadczenia - za pomocą instrukcji continue możemy zatrzymać bieżącą iterację i kontynuować kolejną.
```
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```
- Instrukcja Else - dzięki niej możemy jednorazowo uruchomić blok kodu gdy warunek nie jest już spełniony.
```
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```

### For Loops
Pętla ta służy do iteracji po sekwencji (czyli liście, krotce, słowniku, zestawie lub ciągu znaków). Mniej przypomina słowo kluczowe for w innych językach programowania i działa bardziej jak metoda iterowalna, jaką można znaleźć w innych obiegowych językach. Za pomocą pętli for możemy wykonać zestaw instrukcji, raz dla każdego elementu listy, krotki, zestawu.
```
fruits = ["apple", "bnana", "cherry"]
for x in fruits :
  print(x)
```
Pętla przez ciąg - nawet ciągi znaków są obiektami iterowalnymi, zawierają sekwencję znaków.
```
for x in "banana" :
  print(x)
```
Za pomocą instrukcji break możemy zatrzymać pętlę, zanim przejdzie ona przez wszystkie elementy.
```
fruits = ["apple", "bnana", "cherry"]
for x in fruits :
  print(x)
  if x == "banana" :
    break
```
Kontynuacja oświadczenia - za pomocą instrukcji continue możemy zatrzymać bieżącą iterację pętli i kontynuować następną.
```
if x == "banana" :
  continue
  print(x)
```
Funkcja range() - abyprzejść przez zestaw kodu określoną liczbę razy możemy użyć funkcji range(). Zwraca ona sekwencję liczb, domyślnie zaczynającą się od 0, zwiększającą o 1 i kończącą się na określonej liczbie.
```
for x in range(6) :
  print(x)
```
Funkcja range() domyślnie przyjmuje jako wartość początkową 0, jednakże istnieje możliwość określenia wartości początkowej poprzez dodanie parametru: range(2,6) co oznacza wartości od 2 do 6 (bez 6).
```
for x in range(2, 6) :
  print(x)
```
Funkcja range() domyślnie zwiększa sekwencję o 1, jednakże możliwe jest określenie wartości przyrostu przez dodanie trzeciego parametru range(3, 30, 3).
```
for x in range(2, 30, 3) :
  print(x)
```
Inaczej w pętli for - słowo else w pętli for określa blok kodu, który ma zostać wykonany po zakończeniu pętli.
```
for x in range(6):
  print(x)
else :
  print("Finally")
```
Pętla zagnieżdżona - pętla wewnętrzna zostaje wykonana raz na każdą iterację pętli zewnętrznej.
```
adj = ["red", "big", "tasty"]
fruits = ["apple", "banana", "cherry"]
for x in adj :
  for y in fruits :
    print(x, y)
```
Pętle for nie mogą być puste, jeśli masz pustą pętlę for bez zawartości, umieść instrukcję pass, aby uniknąć błędu.
```
for x in [0, 1, 2]
  pass
```

