# <p style="text-align: center;">Python RegEx </p>
RegEx - czyli wyrażenie regularne, to sekwencja znaków tworząca wzorzec wyszukiwania. Można go wykorzystać do sprawdzenia czy ciąg zawiera określony wzorzec wyszukiwania.
Moduł RegEx - Python ma wbudowany pakiet o nazwie re, którego można użyć do pracy z wyrażeniami regularnymi.
```
import re
```
- RegEx w Python - po zainstalowaniu re modułu możesz zacząć używać wyrażeń regularnych.
```
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)
```
- Funkcja wyrażeń regularnych - moduł re oferuje zestaw funkcji pozwalających na wyszukiwanie ciągu znaków pod kątem dopasowania.
  > - findall - zwraca listę zawierającą wszystkie dopasowania
  > - search - zwraca match w dowolnym miejscu ciągu gdzie znajduje siędopasowanie
  > - split - zwraca listę, na której ciąg został podzielony przy każdym dopasowaniu.
  > - sub - zastępuje jedno lub wiele dopasowań ciągiem.

Metaznaki - to znaki o specjalnym znaczeniu.
- []	A set of characters	"[a-m]"	
- \	Signals a special sequence (can also be used to escape special characters)	"\d"	
- .	Any character (except newline character)	"he..o"	
- ^	Starts with	"^hello"	
- $	Ends with	"planet$"	
- *	Zero or more occurrences	"he.*o"	
- +	One or more occurrences	"he.+o"	
- ?	Zero or one occurrences	"he.?o"	
- {}	Exactly the specified number of occurrences	"he.{2}o"	
- |	Either or	"falls|stays"	
- ()	Capture and group

Sekwencje specjalne - po specjalnej sekwencji następuje \ jeden ze znaków z poniższej listy i ma ona specjalne znaczenie.
- \A	Returns a match if the specified characters are at the beginning of the string,	
- \b	Returns a match where the specified characters are at the beginning or at the end of a word (the "r" in the beginning is making sure that the string is being treated as a "raw string"),
- \B	Returns a match where the specified characters are present, but NOT at the beginning (or at the end) of a word (the "r" in the beginning is making sure that the string is being treated as a "raw string"),
- \d	Returns a match where the string contains digits (numbers from 0-9),
- \D	Returns a match where the string DOES NOT contain digits,	
- \s	Returns a match where the string contains a white space character,
- \S	Returns a match where the string DOES NOT contain a white space character,
- \w	Returns a match where the string contains any word characters (characters from a to Z, digits from 0-9, and the underscore _ character),
- \W	Returns a match where the string DOES NOT contain any word characters,
- \Z	Returns a match if the specified characters are at the end of the string.

Zestawy - to zestaw znaków w parze nawiasów kwadratowych [] o specjalnym znaceniu.
- [arn]	Returns a match where one of the specified characters (a, r, or n) is present	
- [a-n]	Returns a match for any lower case character, alphabetically between a and n	
- [^arn]	Returns a match for any character EXCEPT a, r, and n	
- [0123]	Returns a match where any of the specified digits (0, 1, 2, or 3) are present	
- [0-9]	Returns a match for any digit between 0 and 9	
- [0-5][0-9]	Returns a match for any two-digit numbers from 00 and 59	
- [a-zA-Z]	Returns a match for any character alphabetically between a and z, lower case OR upper case	
- [+]	In sets, +, *, ., |, (), $,{} has no special meaning, so [+] means: return a match for any + character in the string

Funkcja findall() - zwraca listę zawierającą wszystkie dopasowania.
```
import re
txt = "The rain in Spain"
x = re.findall("ai", txt)
print(x)
```

Funkcja wyszukiwania - funkcja search() wyszukuje dopasowanie w ciągu znaków i zwraca obiekt match, jeśli istnieje dopasowanie. Jeśli istnieje więcej niż jedno dopasowanie to zwróci tylko pierwsze.
```
import re

txt = "The rain in Spain"
x = re.search("\s", txt)

print("The first white-space character is located in position:", x.start())
```

Funkcja split() - zwraca listę, na której ciąg został podzielony na każdym dopasowaniu.
```
import re

txt = "The rain in Spain"
x = re.split("\s", txt)
print(x)
```

Funkcja sub() - zastępuje dopasowania wybranym przez Ciebie tekstem.
```
import re

txt = "The rain in Spain"
x = re.sub("\s", "9", txt)
print(x)
```

Dopasuj obiekt - obiekt dopasowania to obiekt zawierający inf. o wyszukiwaniu i wyniku. None jeśli nie ma dopasowania zamiast obiektu dopasowania zostanie zwrócona wartość. Wykonaj wyszukiwanie, które zwróci obiekt dopasowania.
```
import re

txt = "The rain in Spain"
x = re.search("ai", txt)
print(x) #this will print an object
```

Obiekt match posiada właściwości i metody służące do pobierania informacji o wyszukiwaniu i wyniku.
> - span() - zwraca krotkę zawierającą pozycję początkową i końcową dopasowania.
> - string() - zwraca ciąg znaków przekazany do funkcji.
> - group() - zwraca część ciągu, w którym nastąpiło dopasowanie.


# <p style="text-align: center;">Python PIP </p>

PIP - to menedźer pakietów dla pakietów lub modułu Python. Pakiet zawiera wszystkie pliki potrzebne do modułu. Moduł to biblioteka kodu Pthon, które możesz uwzględnić w swoim projekcie.

Sprawdź czy PIP jest zainstalowany - przejdź w wierszu poleceń do lokalizacji katalogu skryptów Python i wpisz polecenie:

C:\Users\Your Name\AppData\Local\Programs\Python\Python36-32\Scripts>pip --version


# <p style="text-align: center;">Python TRY EXcept </p>

- Blok try pozwala przetestować blok kodu pod kontem błędów,
- Blok except pozwala obsłużyć błąd,
- Blok else umożliwia wykonanie kodu, gdy nie ma błędu,
- Blok finnally pozwala na wykonanie kodu, niezależnie od wyniku bloków try- z wyjątkami.

- Obsługa wyjątków- gdy wystąpi błąd lub wyjątek jak go nazywamy, Python zwykle zatrzyma się i wygeneruje komunikat o błędzie. Wyjątki można obsłużyć za pomocą instrukcji try.
```
try:
  print(x)
except:
  print("An exception occurred")
```

- Wiele wyjątków - możesz zdefiniować dowolną liczbę wyjątków.
```
try:
  print(x)
except NameError:
  print("Variable x is not defined")
except:
  print("Something else went wrong")
```

- W przeciwnym razie - możesz użyć else do zdefiniowania bloku kodu, który zostanie wykonany, jeśli nie zostaną zgłoszone żadne błędy.
```
try:
  print("Hello")
except:
  print("Something went wrong")
else:
  print("Nothing went wrong")
```

Finally - blok ten jeśli jest określony zostanie wykonany niezależnie od tego czy blok try zgłosi błąd czy nie.
```
try:
  print(x)
except:
  print("Something went wrong")
finally:
  print("The 'try except' is finished")
```

Zgłoś wyjątek - możesz zgłosić wyjątek jak wystąpi warunek. Aby zgłosić wyjątek użyj raise.
```
x = -1

if x < 0:
  raise Exception("Sorry, no numbers below zero")
```

