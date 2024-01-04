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

Przykład:
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

Przykład:
  Narysuj linięna diagramie od pozycji (1, 3) do pozycji (8, 10)
