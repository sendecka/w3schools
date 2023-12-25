# <p style="text-align: center;">Python Sets </p>

### Python Sets:
Służy do przechowywania wielu elementów w jednej zmiennej. To jeden z 4 wbudowanych typów danych w Python, używany do przechowywania kolekcji danych. To zbiór który jest nieuporządkowany, niezmienny i nieindeksowany.

```
myset = {"apple", "banana","cherry"}
print(myset)
```
- Set jest nieuporządkowany, więc nie możesz mieć pewności, w jakiej kolejności będą się pojawiać elementy. Za każdym razem mogą pojawić się w innej kolejności.
- Elementy są niezmienne, co oznacza, że nie można ich zmieniać po utworzeniu zestawu. Można natomiast je dodawać i usówać.
- Duplikowanie niedozwolone - nie może sięskładać z dwóch elementów o tej samej wartości.
- Uzyskaj długość zestawu - aby zbadać z ilu elementów składa się zbiór skorzystaj z len().
- Typ danych - elementy zestawu mogą mieć dowolny typ danych. Typy string, int, boolean i jeden zestaw może zawierać różne typy danych.

```
set = {1, "apple", 3, True]
```
- Z perspektywy Pythona zestaw definiuje się jako set <class "set">
- Do utworzeniz zestawu można użyć konstruktora set().
```
thisset = set(("apple", "banana", "cherry"))
print(thisset)
```

### Python access sets items:
Nie możesz uzyskać dostępu do elementów zestawu poprzez odwołanie siędo indeksu lub klucza. Można natomiast przeglądać elementy zestawu za pomocą pętli for lub pytać czy w zestawie znajduje się określone elementy używając in.
```
thisset = {"apple", "banana", "cherry"}
for x in thisset :
  print(x)

thisset = {"apple", "banana", "cherry"}
print("banana" in thisset)
```

### Python add sets items:
- Dodaj elementy - po utworzeniu zestawu nie można zmieniać jego elementów, ale można dodawać nowe elementy. Użyj metody add().
```
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print(thisset)
```
- Dodaj zestaw - aby dodać elementy z innego zestawu użyj update().
```
thisset = {"apple", "banana", "cherry"}
tropical = {"mango", papaya"}
thisset.update(tropical)
print(thisset)
```
- Dodaj nową iterację - obiekt w update() nie musi być zbiorem, może to być dowolny obiekt iterowalny.

### Python remove sets items:
Aby usunąć element w zestawie użyj remove() lub discard().
```
thisset.remove("banana")
thisset.discard("banana")
```
- Jeśli element nie istnieje w zestawie remove wyświetli błąc, discard nie.
- pop() -korzystając z niego, metoda usunie losowy element, więc nie możesz być pewien który element zostanie usunięty. pop() zwraca usunięty element.
```
thisset = {"apple", "banana", "cherry"}
x = thisset.pop()
print(x)
print(thisset)
```
- Metoda clear - opróżni cały zestaw.
```
thisset.clear()
print(thisset)
```
- Metoda del() całkowicie usunie zestaw
```
thisset.del()
print(thisset)
```
### Python loop sets:
- Elementy pętli - możesz przeglądać elementy za pomocą pętli for().
```
thisset = {"apple", "banana", "cherry"}
for x in thisset :
  print(x)
```
### Python join sets:
- Łączenie dwóch zestawów - istnieje kilka sposobów łączenia dwóch lub więcej zestawów. Możesz użyć metody union(), która zwraca nowy zestaw zawierający elementy z obu zestawów lub update(), która wstawia wszystkie elementy z jednego do drugiego.
```
set3 = set1.union(set2)
set1.update(set2)
```
- Wykluczają one zduplikowane elementy.
- Zachowaj wyłącznie duplikaty - intersection_update() zachowa tylko te elementy, które są obecne w obu zestawach.
```
x.intersection_update(y)
```
- Zwróci ona nowy zestaw tylko elementów występujących w obu zestawach.
```
x = z.intersection_update(y)
```
- Zachowaj wszystko ale nie duplikaty - metoda ta zachowa tylko te elementy, które nie występują w obu zestawach.
```
x.symmetric_difference_update(y)
z = x.symmetric_difference(y)
```

### Python sets methods:
> - add()
> - clear()
> - copy()
> - difference()
> - difference_update()
> - discard()
> - intersection()
> - intersection_update()
> - isdisjoint()
> - issubset()
> - issuperset()
> - pop()
> - remove()
> - symmetric_difference()
> - symmetric_difference_update()
> - union()
> - update()
