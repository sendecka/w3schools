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
- Dodawanie elementów do słownika odbywa się poprzez 
