# <p style="text-align: center;">Python File Handling </p>


# <p style="text-align: center;">Python File Open</p>

Python ma kilka funkcji do tworzenia, odczytywania, aktualizowania i usuwania plików.

Obsługa plików
Kluczową funkcją do pracy z plikami jest funkcja open(), przyjmuje ona dwa parametry: nazwa pliku i tryb. Istnieją cztery różne metody (tryby) otwierania pliku:
  - " r " - odczyt - wartośćdomyślna. Otwiera plik do odczytu, błąd jeśliplik nie istnieje.
  - " a " - dołącz - otwiera plik do dołączenia, tworzy plik jeśli nie istnieje.
  - " w " - zapis - otwiera pliki do zapisu, twozy plik jeśli nie istnieje.
  - " x " - utwórz - tworzy określony plik, zwraca błąd jeśli plik istnieje.

Dodatkowo można określić czy plik ma być obsługiwany w trybie binarnym czy tekstowym.
  - " t " - text - wartość domyślna. Tryb tekstowy
  - " b " - binarny - tryb binarny np. obraz

Składnia: 
  f = open("demofile.txt")
  f = open("demofile.txt", "rt")

  # Python file open
Otwórz plik na serwerze - aby otworzyć plik, użyj wbudowanej funkcji open(). Funkcja open() zwraca obiekt pliku, który posiada read() metodę odczytu zawartości pliku.

  ```
  f = open("demofile.txt","r")
  ```

Jeśli plik znajduje się w innej lokalizacji, musisz określić ścieżkę.

  ```
  f = open("D:\\myfiles\welcome.txt", "r")
  print(f.read())
  ```

Odczyt tylko części pliku - domyślnie read() zwraca cały text, ale może także określić, ile znaków chcesz zwrócić.

  ```
  f = open("D:\\myfiles\welcome.txt", "r")
  print(f.read(5))
  ```

Przeczytaj linię - możesz zwrócić jedną linię korzystając z readline().

  ```
  f = open("D:\\myfiles\welcome.txt", "r")
  print(f.readline())
  f.close()
  ```

  # Python zapis plików

Zapis do istniejącego pliku: należy dodać do funkcji open() parametr.
  - " a " - dołącz - dołącz na końcu pliku
  - " w " - zapisz - nadpisz istniejące treści

  ```
  f = open("demofile.txt", "a")
  f.write("Now the file has more content!")
  f.close()
  ```

Utwórz nowy plik, użyj open() z jednym z następujących parametrów:
  - " x " - utwórz - 
