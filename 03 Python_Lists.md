# <p style="text-align: center;">Python Lists </p>

### Python Listy:
- listy służą do przechowywania wielu elementów w jednej zmiennej,
- listy to jeden z czterech wbudowanych typów danych w Python używany do przechowywania kolekcji danych,
- listy sątworzone za pomocą nawiasów kwadratowych [],
```
thislist = ['apple', 'banana', 'cherry']
print(thislist)
```
- elementy są upożądkowane, można je zmieniać i zezwalają na powielanie wartości,
- elementy listy są indeksowane, pierwszy element ma index [0], drugi [1],
- kiedy mówimy, że listy są upożądkowane, oznacza to, że pozycje mają określoną kolejność i ta kolejność się nie zmieni.
- jeżeli dasz nowe pozycje na liście, zostaną one umieszczone na końcu,
- lista jest zmienna, co oznacza, że możemy dodawać i usuwać pozycje na liście już po jej utworzeniu,
- ponieważ listy są indeksowane, mogą zawierać elementy o tej samej wartości,
- aby określić ile elementów ma lista użyj len()
- elementy listy mogą mieć dowolny typ danych: string, int, boolean
```
list1 = ['apple', 'banana', 'cherry']
list2 = [1, 5, 7, 9, 3]
list3 = [True, False, True]
```
- jedna lista może zawierać różne typy danych,
```
list1 = ['abc', 34, True, 40, 'male']
```
- z perspektywy Python listy definiuje się jako obiekty z typem danych "lista" <class, "list">
- konstruktor listy - możliwe jest również użycie konstruktora list() podczas tworzenia nowej listy,
```
thislist = list(("apple", "orange", "cherry"))
print(thislist)
```
### Python Access list:
- pozycje listy są indeksowane i możesz uzyskać do nich dostęp, odwołując siędo numeru indeksu. Pierwsza posycja to 0,
```
thislist = ['apple', 'banana', 'cherry']
print(thislist[1])
banana
```
- indeksowanie negatywne - oznacza rozpoczęcie od końca. -1 odnosi się do ostatniej pozycji, -2 odnosi siędo przedostatniej pozycji.
```
thislist = ['apple', 'banana', 'cherry']
print(thislist[-1])
cherry
```
- zakres indeksów - można określić zakres indeksów, określając gdzie zaczynać i gdzie kończyć zakres. Podczas określenia zakresu zwracaną wartością będzie nowa lista z określonymi pozycjami, ostatnia nie jest uwzględniana,
```
thislist = ['apple', 'banana', 'cherry', 'orange', 'mango', 'apple']
print(thislist[2:5])
['cherry', 'orange', 'mango',]
```
- pominięcie początkowej wartości spowoduje, żę zakres zacznie się od pierwszego elementu,
- pominięcie końcowej wartości spowoduje przesunięcie zakresu na koniec listy,
- zakres indeksów ujemnych, jeśli chcesz zacząć wyszukiwanie od końca listy, określ indeksy ujemne,
```
thislist = ['apple', 'banana', 'cherry', 'orange', 'mango', 'apple']
print(thislist[-4:-1])
['cherry', 'orange', 'mango']
```
- sprawdź czy element istnieje - użyj słowa kluczowego in
```
if 'apple' in thislist :
  print('Yes')
```
### Python chenge list items:
- zmiana wartości elementu listy,
```
thislist = ['apple', 'banana', 'cherry']
thislist[1] = 'bluberry'
print(thislist)
['apple', 'bluberry', 'cherry']
```
- zmień zakres wartości pozycji - zdefiniuj nową listę i odwołaj się do zakresu numerów indeksów, w którym chcesz zmienić wartości,
```
thislist = ['apple', 'banana', 'cherry']
thislist[1:3] = ['bluberry', 'watermelon']
print(thislist)
```
- jeśli wstawisz więcej elementów niż zastępujesz, nowe elementy zostaną wstawione w określonym miejscu, a pozostałe zostaną odpowiednio przesunięte,
- jeśli wstawisz mniej elementów niż zastępujesz, nowe zostaną wstawione w określonym miejscu, a pozostałe zostaną odpowiednio przesunięte,
- aby wstawić element do listy, bez zastępowania żadniej z istniejących wartości, możemy skożystać z insert(). Metoda ta wstawia element o określonym indeksie,

### Python chenge list items:
- dołącz elementy
```
thislist = ['apple', 'banana', 'cherry']
thislist.append('orange')
print(thislist)
['apple', 'banana', 'cherry', 'orange']
```
- wstaw element o określonym indeksie
```
thislist = ['apple', 'banana', 'cherry']
thislist.insert(2, 'watermelon')
print(thislist)
['apple', 'banana', 'watermelon', 'cherry']
```
- dołącz elementy z innej listy
```
thislist = ['apple', 'banana', 'cherry']
tropical = ['mango', pineapple', 'papaya']
print(thislist.extend(tropical))
['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
```
- dodaj dowolną iterację, metoda extend() nie wymaga dołączania list, można dodać dowolny obiekt iterowalny,
- 
### Python remove list items:
- usuń określony element
```
thislist = ['apple', 'banana', 'cherry']
thislist.remove('banana')
print(thislist)
```
Jeżeli istnieje więcej niż jeden element o podanej wartości, remove() usuwa pierwsze wystąpienie,
- usuń określony indeks pop()
```
thislist = ['apple', 'banana', 'cherry']
thislist.pop(1)
print(thislist)
```
Jeśli nie określisz indeksu, pop() metoda usunie ostatni element.
- słowo del również usuwa określony index
```
del thislist(0)
```
- słowo del również może usunąć całą listę
```
del thislist
```
- metoda clear() opróżnia listę, lista nadal istnieje, ale nie zawiera elementów
```
thislist = ['apple', 'banana', 'cherry']
thislist.clear()
print(thislist)
```
### Python loop list:
- pętla po liście - możesz przeglądać elementy listy za pomocą pętli for
```
thislist = ['apple', 'banana', 'cherry']
for x in thislist :
  print(x)
```
- możesz również przejżeć elementy listy odwołując się do ich numerów indexów. Użyj funkcji range() i len(), aby utworzyć odpowiednią iterację
```
thislist = ['apple', 'banana', 'cherry']
for i in range(len(thislist)) :
  print((thislist[i])
```
- możesz przeglądać elementy listy za pomocą pętli while. Użyj len(), aby określić długość listy, nasępnie zacznij od 0 i przeglądaj elementy listy, odwołując siędo ich indeksów. Pamiętaj aby po każdej iteracji zmienić indeks o 1
```
thislist = ['apple', 'banana', 'cherry']
i = 0
while i < len(thislist) :
  print(thislist[i])
i = i + 1
```
### Python list comprehension:
- oferuje najkrótszą składnię do przeglądania list w pętli
```
[print(x) for x in thislist]
```

x
x
x
x
x
x
x
### Python sort lists:
- sortuj listę alfanumerycznie - obiekty listy mają metodę sort(), która domyślnie sortuje listę alfanumerycznie rosnąco
```
thislist = ['apple', 'banana', 'cherry']
thislist.sort()
print(thislist)
```
- sortuj listę malejąco - aby posortować listę malejąca, użyj argumentu słowa kluczowego reverse=True
```
thislist = ['apple', 'banana', 'cherry']
thislist.sort(reverse = True)
print(thislist)
```
- dostosuj funkcjęsortowania - możesz również dostosować własne funkcje, używając argumentu słowa kluczowego key= function. Funkcja zwróci liczbę, która posłóży do sortowania listy.
```
def myfunc(n) :
  return abs (n - 50)
thislist = [100, 50, 65, 82, 23]
thislist.sort(key = myfunc)
print(thislist)
[50, 65, 23, 82, 100]
```
- sortowanie bez uwzględnienia wielkości liter - domyślnie w sort() rozróżnia wielkość liter, co powoduje, że wszystkie duże litery są sortowane przed małymi. Możemy użyć wbudowanej funkcji podczas sortowania listy. Jeśli chcesz, aby funkcja nie uwzględniła wielkości liter, użyj str.lower jako funkcji kluczowej.
```
thislist = ['apple', 'Apple','banana', 'cherry']
thislist.sort(key = str.lower)
print(thislist)
```
### Python copy lists:
- nie możesz skopiować listy wpisując list1 = list2, ponieważ będzie tylko odniesieniem do listy1, a zmiany na liście1 zostaną automatycznie wprowadzone w list2. Do tego celów jest metoda copy()
```
thislist = ['apple', 'Apple','banana', 'cherry']
mylist = thislist.copy()
print(mylist)
```
- Innym sposobej jest użycie metody wbudowanej listy()
```
thislist = ['apple', 'Apple','banana', 'cherry']
mylist = list(thislist)
print(mylist)
```
### Python join lists:
- można łączyć dwie lub więcej list. Jednym ze sposobów jest użycie operatora +
```
thislist1 = ['apple', 'Apple','banana', 'cherry']
thislist2 = ['apple', 'a','b', 'c']
thislist3 = thislist1 + thislist2
print(thislist3)
```
- innym sposobem jest dodanie wszystkich elementów z listy1 do listy2, jeden po drugim
```
thislist1 = ['apple', 'Apple','banana', 'cherry']
thislist2 = ['apple', 'a','b', 'c']
for x in list2 :
  list1.append(x)
print(thislist1)
```
### Python metody:
- python ma zestaw wbudowanych metod, które można używać na listach
> - append() -> dodaj nowy element na końcu listy
> - clear() -> usuwa wszystkie elementy listy
> - copy() -> zwraca kopię listy
> - count() -> zwraca liczbę elementów o określonej wartości
> - extend() -> dodaje elementy listy na końcu bieżącej listy
> - index() -> zwraca index pierwszego elementu o określonej wartości
> - insert(() -> dodaje element w określonej pozycji
> - pop() -> usuwa element na określonej pozycji
> - remove() -> usuwa element o określonej wartości
> - reverse() -> odwraca kolejność listy
> - sort() -> sortuje listę
