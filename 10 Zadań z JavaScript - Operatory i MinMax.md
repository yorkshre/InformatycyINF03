# 10 Zadań z JavaScript: Operatory i Skrajne Wartości

Ten zestaw zawiera 10 praktycznych zadań utrwalających operatory przypisania, operatory porównania oraz znajdowanie wartości minimalnych i maksymalnych w języku JavaScript.

---

### Zadanie 1: Zwiększenie wartości (Przypisanie)
Masz zmienną `punkty = 100`. Użyj operatora `+=`, aby dodać do niej `50` punktów, a następnie wypisz wynik w konsoli.

### Zadanie 2: Porównanie ścisłe
Co zwróci wyrażenie `5 === "5"`? Wyjaśnij krótko w komentarzu, dlaczego wynik jest taki, a nie inny.

### Zadanie 3: Sprawdzenie pełnoletności
Napisz instrukcję `if`, która sprawdza, czy zmienna `wiek` jest większa lub równa `18`. Jeśli tak, wypisz w konsoli `"Pełnoletni"`, w przeciwnym razie `"Niepełnoletni"`.

### Zadanie 4: Minimum z trzech liczb
Użyj wbudowanej metody `Math.min()`, aby znaleźć najmniejszą liczbę spośród `14, 2, 29` i przypisz ją do zmiennej `najmniejsza`.

### Zadanie 5: Maksimum z tablicy
Masz tablicę `let liczby = [10, 45, 3, 88, 21];`. Użyj operatora rozproszenia (`...`) wraz z `Math.max()`, aby znaleźć największą liczbę w tej tablicy.

### Zadanie 6: Zakup z pomniejszeniem budżetu
Zdefiniuj zmienne `portfel = 200` oraz `koszt = 75`. Jeśli `portfel >= koszt`, odejmij koszt od portfela, używając operatora przypisania `-=`.

### Zadanie 7: Porównanie luźne a wartości falsy
Co zwróci wyrażenie `0 == false` i dlaczego operator `==` zachowuje się w ten sposób?

### Zadanie 8: Podwójny warunek (Zakres temperatury)
Napisz instrukcję `if`, która sprawdza, czy zmienna `temperatura` jest większa niż `0` **oraz** mniejsza niż `30` (wykorzystaj operator logiczny `&&`).

### Zadanie 9: Operator różności ścisłej
Napisz warunek sprawdzający, czy zmienna `rola` jest **różna** (pod względem wartości lub typu) od `"admin"` (użyj operatora `!==`).

### Zadanie 10: Własne minimum w pętli
Napisz funkcję lub pętlę dla tablicy `[12, 5, 23, 1, 9]`, która znajdzie najmniejszą liczbę **bez używania** metody `Math.min`.