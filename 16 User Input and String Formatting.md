# <p style="text-align: center;">Python User Input </p>

Dane wejściowe - Python umożliwia wprowadzenie danych przez użytkownika. Oznacza to, żę możemy poprosić użytkownika o wprowadzenie danych, Python używa metodu input().

Poniższy przykład wymaga podania nazwy użytkownika, a kiedy ją wprowadzisz, zostanie ona wydrukowana na ekranie.
```
username = input("Enter username:")
print("Username is: " + username)
```
Python przestaje wykonywać funkcję input() i konstruuje, gdy użytkownik wprowadzi pewne dane.

# <p style="text-align: center;">Python String Formatting</p>

Aby mieć pewność, że ciąg znaków będzie wyświetlany zgodnie z oczekiwaniami, możemy sformatować wynik za pomocą metody format().

String format() - metoda format pozwala na sformatowanie wybranych fragmentów ciągu znaków. Czasami są fragmenty tekstu, nad którymi nie masz kontroli, może pochodzą z bazy danych lub danych wprowadzonych przez użytkownika. Aby kontrolować takie wartości, dodaj {} w tekście i uruchom wartość za pomocą format().
```
price = 49
txt = "The price is {} dollars"
print(txt.format(price))
```

Wiele wartości - jeśli chcesz użyć wielu wartości, poprostu dodaj więcej wartości do metody format().
```
quantity = 3
itemno = 567
price = 49
myorder = "I want {} pieces of item number {} for {:.2f} dollars."
print(myorder.format(quantity, itemno, price))
```

Numery indeksowane - możesz użyć liczb indeksowanych (liczby w nawiasach klamrowych) aby mieć pewność, że wartości są umieszczone we właściwych symbolach zastępczych.
```
quantity = 3
itemno = 567
price = 49
myorder = "I want {0} pieces of item number {1} for {2:.2f} dollars."
print(myorder.format(quantity, itemno, price))
````

Nazwane indeksy - możesz także użyć nazwanych indeksów, wprowadzając nazwę w nawiasach klamrowych {carname}, ale wtedu musisz używać nazw podczas przekazywania wartości parametrów.
```
txt.format(carname = "Ford")
myorder = "I have a {carname}, it is a {model}."
print(myorder.format(carname = "Ford", model = "Mustang"))
```
