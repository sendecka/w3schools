# <p style="text-align: center;">Python Booleans </p>

### Python wartości logoczne:
- wartości logiczne reprezentują True lub False,
- kiedy porównasz dwie wartości, wyrażenie jest oceniane, a Python zwraca odpowiedź logiczną,
```
print(10 > 9)
print(10 == 9)
print(10 < 9)
```
- można również uruchomić wartość logiczną w if,
```
a = 200
b = 30
if b > a :
  print('b jest większe od a")
else :
  print('b jest mniejsze od a")
```
- oceniaj wartości i zmienne dzięli bool() większość wartości jest prawdziwa,
```
print(bool("Hello")
print(bool(15))
```
- dowolny ciąg jest True z wyjątkiem pustych ciągów, dowolna liczba jest True z wyjątkiem 0, dowolna lista, krotka i słownik to True z wyjątkiem pustych,
- niektóre wartości są fałszywe. W rzeczywistości nie ma wielu wartości, które dają wynik Fals, z wyjątkiem pustych wartości takich jak (), [], {}, 0 i none,
```
bool(0)
bool(" ")
bool(())
bool([])
bool({})
```
- funkcje mogą zwracać wartość logiczną,
```
def myFunction():
  return True
print(myFunction)
```
### Python operatory:
- operatory służą do wykonywania operacji na zmiennych,
- mamy kilka grup operatorów:
#### - Operatory Arytmetyczne:
Będą używane z wartościami numerycznymi do operacji typowo matematycznych.
- | + | - dodawanie | x + y | 3 + 2 | 5
- | - | - odejmowanie | x - y | 3 - 2 | 1
- | * | - mnożenie | x * y | 3 * 2 | 6
- | / | - dzielenie | x / y | 3 / 2 | 1.5
- | % | - modulo | x % y | 3 % 2 | 1
- | ** | - potęgowanie | x ** y | 3 ** 2 | 9
- | // | - dzielenie bez reszty | x // y | 3 // 2 | 1
#### - Operatory Przypisania:
Służą do przypisania wartości zmiennym
