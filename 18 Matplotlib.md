# MATPLOTLIB

Matplotlib - to niskopoziomowa biblioteka do tworzenia wykresów w Python, która służy jako narzędzie do wizualizacji. 
Jest oprogramowaniem open source i możemy z niego swobodnie korzysać.
Matplotlib - jest napisany główni w python, kilka segmentów jest napisane w C, JavaScript, Objective-C aby zapewnić zgodność.

### Instalacja Matplotlib
Jeśli masz zainstalowany Python PIP w systemie, instalacja Matplotlib jest łatwa. Zainstalj go za pomocą polecenia:

C:\Users\YourName>pip install matplotlib

### Zaimportuj Matplotlib

Po zainstalowaniu aplikacji zaimportuj ją do swoich aplikacji, dodając instrukcję:

```
import matplotlib
```

### Sprawdzenie wersji

Ciąg wersji przechowywany w __version__ atrybute.

### Matplotlib Pyplot

Większość narzędzi Matplotlib znajduje się w module pyplot i są zwykle importowane pod aliasem plt.

```
import matplotlib.pyplot as plt
```
Teraz pakiet Python można nazwać plt.

> Przykład:
  Narysuj linię na diagramie od pozycji (0, 0) do pozycji (6, 250)
```
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([0, 6])
ypoints = np.array([0, 250])

plt.plot(xpoints, ypoints)
plt.show()
```

### Wykres Matplotlib

Rysowanie punktów x i y. Funkcja plot() służy do rysowania punktów (znaczników) na diagramie. Domyślnie plot() rysuje linię od punktu do punktu. Funkcja pobiera parametry służące do określania punktów na diagramie.
Parametr 1 jest tablicą zawierającą punkty na osi x
Parametr 2 jest tablicą zawierającą punkty na osi y

Jeśli chcemy wykreślić linię od (1, 3) do (8, 10) musimy przekazać dwie tablice [1, 8] i [3, 10] do funkcji plot.

> Przykład:
  Narysuj linięna diagramie od pozycji (1, 3) do pozycji (8, 10)
```
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints)
plt.show()
```

### Rysowanie bez linii

Aby wykreślić tylko znaczniki, można użyć parametru skrótu "o" co oznacza "pierścienie".

> Przykład: Narysuj dwa punkty na diagramie, jeden w pozycji (1,3) drugi (8, 10)

```
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 8])
ypoints = np.array([3, 10])

plt.plot(xpoints, ypoints, "o")
plt.show()
```

### Wiele punktów

Możesz wykreślić dowolną liczbę punktów, upewnij się tylko, że masz tą samą liczbę punktów na obu osiach.

> Przykład: Narysuj linię na diagramie od pozycji (1, 3) do (2, 8), następnie do (6, 1) i na koniec (8, 10).

```
import matplotlib.pyplot as plt
import numpy as np

xpoints = np.array([1, 2, 6, 8])
ypoints = np.array([3, 8, 1, 10])

plt.plot(xpoints, ypoints)
plt.show()
```

### Domyślne punkty x

Jeśli nie określimy punktów na osi x, otrzymają one domyślne wartości 0, 1, 2, 3, 4, itp. w zależności od długości punktów y. Jeśli więc weźniemy ten przykład co powyżej i pominiemy x. 

> Przykład: Wykres bez punktów x

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10, 5, 7])

plt.plot(ypoints)
plt.show()
```

### Matplotlib markers

Markery - możesz użyć argumentu słowa kluczowego "marker" aby podkreślić każdy punkt określonym znacznikiem.

> Przykład: Zaznacz każdy punkt kółkiem

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker="o")
plt.show()
```

### Matplotlib Markers

Istnieje wiele znaczników

'o'	Circle	
'*'	Star	
'.'	Point	
','	Pixel	
'x'	X	
'X'	X (filled)	
'+'	Plus	
'P'	Plus (filled)	
's'	Square	
'D'	Diamond	
'd'	Diamond (thin)	
'p'	Pentagon	
'H'	Hexagon	
'h'	Hexagon	
'v'	Triangle Down	
'^'	Triangle Up	
'<'	Triangle Left	
'>'	Triangle Right	
'1'	Tri Down	
'2'	Tri Up	
'3'	Tri Left	
'4'	Tri Right	
'|'	Vline	
'_'	Hline

### Format Strings fmt

Do określenia znacznika można także użyć parametru zapisu ciągu skrótu. Ten parametr jest również fmt i jest zapisywany wg. składni.

> Przykład: Zaznacz każdy punkt kółkiem

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, "o:r")
plt.show()
```

Wartość znacznika może być dowolna z powyższego odniesienia do znacznika. Wartość wiersza może mieć jedną z następujących wartości:
- Odniesienie do linii:
  - "-" - pełna linia
  - ":" - linia kropkowana
  - "--" - linia przerywana
  - "-." - linia kropkowano - przerywana
- Odniesienie do koloru:
  - "r" - czerwony
  - "g" - zielony
  - "b" - niebieski
  - "c" - cyan
  - "m" - magenta
  - "y" - żółty
  - "k" - czarny
  - "w" - biały

### Rozmiar znacznika

Aby ustawić rozmiar znacznika
