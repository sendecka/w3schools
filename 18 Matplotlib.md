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

Aby ustawić rozmiar znacznika, możesz użyć argumentów słowa kluczowego markersize lub skróconej wersji ms.

> Przykład: Ustaw rozmiar znaczników na 20.

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker="o", ms=20)
plt.show()
```

### Kolor znacznika

Możesz użyć argumentu słowa kluczowego markeredgecolor lub krótszego mec, aby ustalić kolor krawędzi znacznika.

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker="o", ms=20, mec="r")
plt.show()
```
 Możesz użyć argumentu słowa kluczowego markerfacecolor lub skrót mfc, aby ustalić kolor wewnątrz krawędzi znaczników.

> Przykład: Ustaw kolor powierzchni znacznika na czerwony.

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, marker="o", ms=20, mfc="r")
plt.show()
```

Użyj argumentów mec i mfc aby pokolorować cały znacznik.

```
plt.plot(ypoints, marker="o", ms=20, mfc="r", mec="r")
```
Można użyć szesnastkowych wartości kolorów.
```
mec="#4CAF50"
mfc="4CAF50"
```

### Matplotlib line

Styl linii - można użyć argumentu słowa kluczowego linestyle lub skrót ls aby zmienić styl kreślonej linii.

> Przykład: Użyj linii przerywanej.

```
import matplotlib.pyplot as plt
import numpy as np

ypoints = np.array([3, 8, 1, 10])

plt.plot(ypoints, linestyle="dotteso")
plt.show()
```

### Matplotlib line Krótsza składnia

Styl linii można zapisać w krótszej składni: linestyle -> ls, dotted -> :, dashed -> --

### Style linii

Możesz wybrać z kilku różnych styli.
  > - 'solid' (default)	'-'	
  > - 'dotted'	':'	
  > - 'dashed'	'--'	
  > - 'dashdot'	'-.'	
  > - 'None'	'' or ' '

### Kolor linii

Możesz użyć argumentu słowa kluczowego color lub skrót c, aby ustalić kolor linii.

```
plt.plot(ypoints, color="r")
plt.show()
```

Możesz użyć koloru w układzie szesnastkowym.

### Szerokość linii

Aby zmienić szerokość linii, możesz użyć argumentu linewidth lub lw. Wartość jest zmiennoprzecinkowa wyrażoną w punktach.
```
plt.plot(ypoints, linewidth="20.5")
```

### Wiele linii

Możesz narysować wiele linii, dodając więcej plt.plot()
```
import matplotlib.pyplot as plt
import numpy as np

y1 = np.array([3, 8, 1, 10])
y2 = np.array([6, 2, 7, 11])

plt.plot(y1)
plt.plot(y2)
plt.show()
```

Można także wykreślić wiele linii, dodając punkty na osi x i y dla każdej linii w tej samej funkcji plt.plot().

### Matplotlib Labels and title

Utwórz etykiety dla plot - w Python możesz używać funkcji xlabel() i ylabel() do ustawienia etykiety dla osi x i y.

> Przykład: Utwórz etykiety dla osi x i y

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([3, 8, 1, 10, 20, 25, 30, 35, 40])
y = np.array([6, 2, 7, 11, 21, 26, 31, 36, 41])

plt.plot(x,y)
plt.xlabel("Averange Pulse")
plt.ylabel("Calorie burnage")

plt.show()
```
Utwórz tytuł - możesz użyć funkcji title(), aby ustalić tytuł wykresu.

> Przykład: Ustaw tytuł wykresu.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([3, 8, 1, 10, 20, 25, 30, 35, 40])
y = np.array([6, 2, 7, 11, 21, 26, 31, 36, 41])

plt.plot(x,y)
plt.tittle("Sports watch data")
plt.xlabel("Averange Pulse")
plt.ylabel("Calorie burnage")

plt.show()
```
Ustawienie właściwości czcionki dla tytułu i etykiety.
Możesz ustawić parametr fontdict w xlabel() i ylabel i tittle() i ustalić właściwości dla tytułu i etykiety.

> Przykład: Ustaw właściwości czcionki tytułu i etykiet.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([3, 8, 1, 10, 20, 25, 30, 35, 40])
y = np.array([6, 2, 7, 11, 21, 26, 31, 36, 41])

font1 = {'family':'serif','color':'blue','size':20}
font2 = {'family':'serif','color':'darkred','size':15}

plt.tittle("Sports watch data")
plt.xlabel("Averange Pulse")
plt.ylabel("Calorie burnage")

plt.plot(x,y)
plt.show()
```
Umieść tytuł - możesz użyć parametru loc tittle() aby rozmieścić tytuł. Wartości to: left, right, center. Deaful center.

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data", loc = 'left')
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)
plt.show()
```

### Matplotlib Adding grid lines

Dodawanie linii siatki do wykresu - można to zrobić za pomocą funkcji grid(). 

> Przykład: Wyświetl linie siatki do wykresu.

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data", loc = 'left')
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)
plt.grid()
plt.show()
```

Określ które linie siatki mają być wyświetlone - możesz użyć axis parametru w funkcji grid(), aby określić które linie siatki mają być wyświetlane.

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data")
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)

plt.grid(axis = 'y')

plt.show()
```
lub
```
plt.grid(axis = 'x')
```
Ustaw właściwości linii dla siatki - możesz ustalić właściwości siatki w sposób: grid(color = 'color', linestyle = 'linestyle', linewidth = number)

> Przykład: Ustaw właściwości linii siatki

```
import numpy as np
import matplotlib.pyplot as plt

x = np.array([80, 85, 90, 95, 100, 105, 110, 115, 120, 125])
y = np.array([240, 250, 260, 270, 280, 290, 300, 310, 320, 330])

plt.title("Sports Watch Data")
plt.xlabel("Average Pulse")
plt.ylabel("Calorie Burnage")

plt.plot(x, y)

plt.grid(color = 'green', linestyle = '--', linewidth = 0.5)

plt.show()
```

### Matplotlib subplot

Wyświetl wiele wykresów - dzięki subplot() możesz narysować wiele wykresów na jednym rysunku.

> Przykład: Narysuj 2 wykresy.

```
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(1, 2, 1)
plt.plot(x,y)

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(1, 2, 2)
plt.plot(x,y)

plt.show()
```
Funkcja subplot() przyjmuje trzy argumenty opisujące układ figur. Układ jest zorganizowany w wiersze i kolumny, które są reprezentowane przez pierwszy i drugi argument. Trzeci argument reprezentuje indeks bieżącego wykresu.
```
plt.subplot(1,2,1)
```
figura ma 1 wiersz 2 kolumny i jest pierwszym wykresem
```
plt.subplot(1,2,2)
```
figura ma 1 wiersz, 2 kolumny i jest 2

> Przykład: Narysuj dwa wykresy jeden nad drugim.

```
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(2, 1, 1)
plt.plot(x,y)

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(2, 1, 2)
plt.plot(x,y)

plt.show()
```
Tytuł całej przestrzeni gdzie sąwykresy - możesz dodać tytuł całej figury za pomocą subtitle()
> Przykład: podaj tytuł całej figury.

```
import matplotlib.pyplot as plt
import numpy as np

#plot 1:
x = np.array([0, 1, 2, 3])
y = np.array([3, 8, 1, 10])

plt.subplot(2, 1, 1)
plt.plot(x,y)

#plot 2:
x = np.array([0, 1, 2, 3])
y = np.array([10, 20, 30, 40])

plt.subplot(2, 1, 2)
plt.plot(x,y)

plt.show()
```

### Matplotlib Scatter

Tworzenie wykresów punktowych - możesz użć funkcji scatter() do narysowania wykresu punktowego. Funkcja scatter() wykreśla jedną kropkę dla każdej obserwacji. Potrzebuje dwóch tablic o tej samej długości, jednej dla x drugiej dla y.

> Przykład: Wyrysuj wykres scatter.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])

plt.scatter(x, y)
plt.show()
```
Zabarwienie - możesz ustalić własny kolor dla wykresu za pomocą argumentu color lub c.

> Przykład: Ustaw własny kolor znaczników.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
plt.scatter(x, y, color = 'hotpink')

x = np.array([2,2,8,1,15,8,12,9,7,3,11,4,7,14,12])
y = np.array([100,105,84,105,90,99,90,95,94,100,79,112,91,80,85])
plt.scatter(x, y, color = '#88c999')

plt.show()
```
Pokoloruj każdą kropkę - możesz pokolorować każdą kropkę, używając tablicy jako wartości argumentu c.


> Przykład: Ustaw własny kolor znaczników.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
colors = np.array(["red","green","blue","yellow","pink","black","orange","purple","beige","brown","gray","cyan","magenta"])

plt.scatter(x, y, c=colors)

plt.show()
```

Mapa kolorów - modół matplotlib posiada szereg dostępnych map kolorów. Mapa kolorów przypomina listę kolorów gdzie każdy kolor ma wartość z zakresu od 0 do 100.
Jak korzystać z mapy kolorów - możesz określić mapę kolorów za pomocą argumentu cmap z wartością mapy kolorów w tym przypadku, 'viridis' jest to jedna z wbudowanych map kolorów dostępnych w matplotlib. Dodatkowo musisz utworzyć tablicę z wartościami (od 0 do 100) po jednej wartości na każdy punkt na wykresie punktowym.

> Przykład: Utwórz tablicę kolorów i określ mapę kolorów na wykresie punktowym.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
colors = np.array([0, 10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 100])

plt.scatter(x, y, c=colors, cmap='viridis')

plt.show()
```
Możesz dołączyć mapę kolorów dołanczając instrukcję plt.colorbar(). Istnieje wiele domyślnych map kolorów.

> Przykład: Dołącz rzeczywistą mapę kolorów.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
colors = np.array([0, 10, 20, 30, 40, 45, 50, 55, 60, 70, 80, 90, 100])

plt.scatter(x, y, c=colors, cmap='viridis')

plt.colorbar()

plt.show()
```

Rozmiar - za pomocą argumentu możesz zmienić rozmiar kropek s. Podobnie jak koloru, upewnij się, że tablica rozmiarów ma tę samą długość co tablice x i y.

> Przykład: Ustaw własny rozmiar znaczników.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
sizes = np.array([20,50,100,200,500,1000,60,90,10,300,600,800,75])

plt.scatter(x, y, s=sizes)

plt.show()
```
Alfa - za pomocą argumentu alpha możesz dostosować przezroczystość kropek. Podobnie jak kolory upewnij się, że ma tą samą długość co x i y.

> Przykład: Ustaw własny rozmiar znaczników.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array([5,7,8,7,2,17,2,9,4,11,12,9,6])
y = np.array([99,86,87,88,111,86,103,87,94,78,77,85,86])
sizes = np.array([20,50,100,200,500,1000,60,90,10,300,600,800,75])

plt.scatter(x, y, s=sizes, alpha=0.5)

plt.show()
```

Połącz rozmiar koloru i alfa - możesz łączyć mapę kolorów kropek z różnymi rozmiarami kropek.

> Przykład: Twórz losowe tablice zawierające 100 wartości punktów x, punktów y, kolorów i rozmiarów.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.random.randint(100, size=(100))
y = np.random.randint(100, size=(100))
colors = np.random.randint(100, size=(100))
sizes = 10 * np.random.randint(100, size=(100))

plt.scatter(x, y, c=colors, s=sizes, alpha=0.5, cmap='nipy_spectral')

plt.colorbar()

plt.show()
```

### Matplotlib Bars

Tworzenie pasków wykresów - możesz użyć funkcji bar() do rysowania wykresów słupkowych.

> Przykład: Narysuj 4 wykresy słupkowe.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x,y)
plt.show()
```
Funkcja bar() pobiera argumenty opisujące układ słupków. Kategorie i ich wartości reprezentowane przez pierwszy i drugi argument jako tablice.

Horizontal bar -  jeśli chcesz aby słupki wyświetlały się poziomo a nie pionowo użyj funkcji barh().

> Przykład: Narysuj 4 poziome paski.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x, y)
plt.show()
```

Kolor paska - bar() i barh() przyjmują argumenty słowa kluczowe color, aby ustawić kolor słupków.

> Przykład: Narysuj 4 czerwone słupki.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x, y, color = "red")
plt.show()
```

Szerokość paska - argument bar() przyjmuje słowo kluczowe width, aby ustawić szerokość słupków.

> Przykład: Narysuj 4 bardzo cienkie paski.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.bar(x, y, width = 0.1)
plt.show()
```
Domyślna wartość szerokości to 0.8 w przypadku poziomych pasków height zamiast width.

Wysokość paska - Przyjmuje barh() argument słowa kluczowego height, aby ustawić wysokość słupków.

> Przykład: Narysuj 4 bardzo cienkie paski.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.array(["A", "B", "C", "D"])
y = np.array([3, 8, 1, 10])

plt.barh(x, y, height = 0.1)
plt.show()
```

### Matplotlib Histogram

Histogram - to wykres przedstawiający rozkład częstotliwości. Jest to wykres przedstawiający liczbę obserwacji w każdym zadanym przedziale.

Utwórz histogram - w matplotlib używa się hist() do tworzenia histogramów. Funkcja hist() użyje tablicy liczb do utworzenia histogramu, tablica zostanie wysłana do funkcji jako argument.

Dla uproszczenia używamy do losowego generowania tablic zawierającej 250 wartości, gdzie wartości będą się skupiać wokół 170, a odchylenie standardowe wynosi 10.

> Przykład: Normalna dystrybucja danych przez NumPy.

```
import numpy as np

x = np.random.normal(170, 10, 250)

print(x)
```
Funkcja hist() odczyta tablicę i wygeneruje histogram.

```
import matplotlib.pyplot as plt
import numpy as np

x = np.random.normal(170, 10, 250)

plt.hist(x)
plt.show()
```

### Matplotlib Pie charts

Tworzenie wykresów kołowych - w Python możesz użyć funkcji pie() do rysowania wykresów kołowych.

> Przykład: Prosty wykres kołowy.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])

plt.pie(y)
plt.show()
```

Rysowany jest jeden element dla każdej wartości w tablicy. Domyślnie rysowanie pierwszego klina zaczya się od osi x i przesuwa się w kierunku przeciwnym do ruchu wskazuwek zegara.

Etykiety - dodaj etykiety do wykresu kołowego z parametrem label. Parametr label musi być tablicą z jedną etykietą dla każdego klina.

> Przykład: Prosty wykres kołowy.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.show()
```

Kąt początkowy - można zmienić kont początkowy, określając parametr startangle. Parametr startangle jest definiowany za pomocą kąta w stopniach, domyślny kąt to 0.

> Przykład: Rozpocznij pierwszy klin pod kątem 90 stopni.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels, startangle = 90)
plt.show()
```

Parametr explode - chcesz aby któryś z parametrów sięwyróżnił? Parametr explode pozwala na to. Parametr explode jeśli jest określany musi zawierać wartość dla każdego klina. Wartość ta reprezentuje odległość od środka każdego klina.

> Przykład: Wyciągnij klin „Jabłka” 0,2 ze środka ciasta.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]
myexplode = [0.2, 0, 0, 0]

plt.pie(y, labels = mylabels, explode = myexplode)
plt.show()
```

Cień - dodaj cień do wykresu kołowego ustalając parametr shadows na True.

> Przykład: Dodaj cień.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]
myexplode = [0.2, 0, 0, 0]

plt.pie(y, labels = mylabels, explode = myexplode, shadow = True)
plt.show()
```

Zabarwienie - za pomocą parametru colors możesz ustalić kolor każdego klina wykresu kołowego. Parametr ten musi zawierać jeden parametr dla każdego klina.

> Przykład: Określ nowy kolor dla każdego klina.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]
mycolors = ["black", "hotpink", "b", "#4CAF50"]

plt.pie(y, labels = mylabels, colors = mycolors)
plt.show()
```

Legenda - aby dodać listę wyjaśnień dla każdego klina użyj funkcji legend().

> Przykład: Dodaj legendę.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.legend()
plt.show()
```

Legenda z nagłówkiem - aby dodać nagłówek do legendy należy dodać parametr title do funkcji legend().

> Przykład: Dodaj legendę z nagłówkiem.

```
import matplotlib.pyplot as plt
import numpy as np

y = np.array([35, 25, 25, 15])
mylabels = ["Apples", "Bananas", "Cherries", "Dates"]

plt.pie(y, labels = mylabels)
plt.legend(title = "Four Fruits:")
plt.show()
```
