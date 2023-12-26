# <p style="text-align: center;">Python Dictionary </p>

### Python Dictionary:
Słowniki służą do przechowywania danych w parach klucz: wartość. To zbiór uporządkowany, podlegający zmianom i nie pozwalają na duplikaty.
```
thisdict = {
  "brand" : "Ford",
  "model" : "Mustang",
  "year" : 1964
}
print(thisdict)
```
- Elementy słownika - są uporządkowane, zmienne i nie pozwalają na duplikaty. Można się do nich odwołać za pomocą klucza.
```
print(thisdict["brand"]
```
- Elementy są zmienne - co oznacza, że możemy zmieniać, dodawać lub usuwać elementy po utworzeniu słownika.
- Duplikaty niedozwolone - nie mogą zawierać dwóch pozycji o tym samym kluczu.
- Długość słownika - można określić za pomocą len()
```
print(len(thisdict))
```
- Elementy słownika - typy danych mogą mieć dowolny typ danych. String, int, boolean, list.
- Z perspektywy Python słowniki definiuje jako typ danych <class, "dict">
- Konstruktor - do utworzenia słownika można użyć konstruktora dict()
```
thisdict = dict("name" = "john", "age" = 16, "country" = "Norway")
print(thisdict)
```
### Python Access Dictionary:
- Dostęp do elementów słownika można uzyskać odwołując się do jego nazwy klucza zawartej w nawiasach kwadratowych.
```
x = thisdict["model"]
```
- Istnieje również metoda get() która daje ten sam wynik.
```
x = thisdict.get("model")
```
- Metoda keys() zwróci listę wszystkich kluczy w słowniku.
```
x = thisdict.keys("model")
```
- Metoda values() zwróci listę wszystkich wartości znajdujących się w słowniku.
```
x = thisdict.values()
```
- Metoda items() zwróci każdy element słownika w postaci krotek na liście.
```
x = thisdict.items()
```
- Sprawdź czy klucz istnieje - aby określić czy określony klucz występuje w słowniku, użyj słowa in.
```
if "model" in thisdict :
  print("Yes")
```
### Python Change Dictionary items:
- Możesz zmienić wartośćkonkretnego elementu odwołując siędo jego klucza.
```
thisdict = {
  "brand" : "Ford",
  "model" : "Mustang",
  "year" : 1964
}
thisdict["year'] = 2018
```
- Zaktualizuj słownik - metoda update() zaktualizuje słownik o elementy z podanego argumentu. Argument musi być słownikiem lub obiektem iterowalnym z parami klucz: wartość.
```
thisdict.update({"year" : 2020})
```
### Python Add Dictionary items:
- Dodawanie elementów do słownika odbywa się poprzez użycie nowego klucza indeksującego i przypisanie mu wartości.
```
thisdict["color"] = "red"
```
- Metoda update() zaktualizuje słownik o elementy z podanego argumentu. Jeśli pozycja nie istnieje zostanie dodana. Argument musi posiadać klucz: wartość.
```
thisdict.update({"color" : "red"})
```
### Python Remove Dictionary items:
- Istnieje kilka sposobów usuwania elementów ze słownika.
  > - Metoda pop() usuwa element o podanej nazwie klucza.
  ```
  thisdict.pop("model")
  ```
  > - Metoda popitem() usuwa ostatni wstawione element.
  ```
  thisdict.popitem()
  ```
  > - Metoda del usuwa element o określonej nazwie klucza.
  ```
  del thisdict["model"]
  ```
  > - Metoda clear() opróżnia słownik.
  ```
  thisdict.clear()
  ```

### Python Loop Dictionary:
- Możesz przeglądać słownik używając pętli for podczas przeglądania słownika w pętli, wartością są klucze słownika, ale istnieją również metody zwracania wartości.
```
for x in thisdict :
  print(thisdict)
```
- Do zwrócenia wartości słownika.
```
for x in thisdict.values() :
  print(x)
```
- Metoda aby zwrócić klucze słownika.
```
for x in thisdict.keys() :
  print(x)
```
- Wykonaj pętlę między kluczami a wartościami.
```
for x, y in thisdict.items()
  print(x, y)
```
  
### Python Copy Dictionary:
- Nie można skopiować słownika wpisując poprostu dict2 = dict1, ponieważ będzie to tylko odniesienie do dict2, a zmiany dokonane w dict1 zostaną automatycznie wprowadzone również w dict2. Istnieją sposoby na wykonanie kopii, jedną z nich jest użycie wbudowanej metody copy().
```
mydict = thisdict.copy()
```
- Innym sposobem jest wykorzystanie wbudowanej funkcjii dict().
```
mydict = dict(thisdict)
```

### Python Nested Dictionary:

- Zagnieżdzone słowniki - słownik może w sobie zawierać inny słownik.
```
myfamily = {
  "child1" : {
      "name" : "Emil",
      "year" : 2004
    }
  "child2" : {
      "name" : "Tobias",
      "year" : 2007
    }, }
```
- Utwórz 3 słowniki, a następnie utwórz jeden, który będzie zawierał pozostałe 3.
```
myfamily = {
    "child1" : "child1",
    "child21" : "child2",
    "child3" : "child3",
}
```
- Dostęp do elementów zagnieżdżonych w słownikach - używasz nazwy słowników zaczynając od zewnętrznego.
```
print(myfamily["child2"]["name"})
```

### Python Dictionary Methods:
> - clear()
>   - copy()
>   - fromkeys()
>   - get()
>   - items()
>   - keys()
>   - pop()
>   - popitems()
>   - setdefault()
>   - update()
>   - values()
