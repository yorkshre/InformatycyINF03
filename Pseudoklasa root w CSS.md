# Pseudoklasa `:root` w CSS i zmienne globalne

Cześć! W tym materiale nauczymy się, czym jest pseudoklasa `:root` w języku CSS oraz jak wykorzystać ją do tworzenia i zarządzania **zmiennymi globalnymi** (custom properties).

---

## 1. Do czego służy `:root`?

Pseudoklasa `:root` w CSS dopasowuje się do **głównego elementu nadrzędnego (korzenia)** całego dokumentu. W przypadku dokumentów HTML tym elementem jest znacznik `<html>`. 

Choć selektor `html` robi niemal to samo, pseudoklasa `:root` ma **większą specyficzne (specificity)**, dzięki czemu jest standardowym i najczęściej wybieranym miejscem do definiowania zmiennych globalnych.

Najczęstszym zastosowaniem `:root` jest przechowywanie zmiennych, które mogą być używane w dowolnym miejscu arkusza stylów. Zmienne w CSS definiuje się za pomocą dwóch myślników na początku nazwy (np. `--nazwa-zmiennej`).

### Przykład użycia:

```css
:root {
  --glowny-kolor: #3498db;
  --kolor-tekstu: #2c3e50;
  --odstep: 16px;
}

body {
  background-color: var(--glowny-kolor);
  color: var(--kolor-tekstu);
  padding: var(--odstep);
}

button {
  background-color: var(--kolor-tekstu);
  color: var(--glowny-kolor);
  padding: var(--odstep);
}
```

---

## 2. Dlaczego warto używać `:root` do zmiennych?

1. **Centralne zarządzanie (Single Source of Truth):** Jeśli zechcesz zmienić motyw kolorystyczny całej strony (np. z niebieskiego na zielony), zmieniasz wartość tylko w jednym miejscu – w bloku `:root`.
2. **Dziedziczenie:** Zmienne zdefiniowane w `:root` są dostępne globalnie w całym dokumencie dla każdego elementu potomnego.
3. **Łatwa obsługa trybów (np. Dark Mode):** Możesz bardzo łatwo nadpisać zmienne dla wybranej klasy, np. `.dark-theme`.

---

## 3. Zadania dla uczniów

### Zadanie 1: Paleta barw strony
Stwórz strukturę HTML z nagłówkiem `<h1>`, akapitem oraz przyciskiem. W pliku CSS zdefiniuj w bloku `:root` trzy zmienne kolorystyczne:
* `--primary-color` (np. odcień fioletu)
* `--secondary-color` (np. odcień żółtego)
* `--text-color` (kolor ciemnoszary)

Następnie użyj tych zmiennych do ostylowania elementów strony (kolor tła strony, kolor nagłówka, kolor tła oraz tekstu przycisku).

### Zadanie 2: Modyfikacja wielkości czcionek
W bloku `:root` zdefiniuj zmienną `--base-font-size` ustawioną na `16px`. Użyj tej zmiennej dla elementu `body`. Następnie utwórz klasę `.big-text`, która nadpisuje tę zmienną na `24px` i przypisz ją do wybranego akapitu.

---

## 4. Rozwiązania zadań

### Rozwiązanie zadania 1

**HTML:**
```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Zadanie root</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Witaj na stronie!</h1>
    <p>To jest przykładowy akapit tekstowy.</p>
    <button>Kliknij mnie</button>
</body>
</html>
```

**CSS (`style.css`):**
```css
:root {
  --primary-color: #6c5ce7;
  --secondary-color: #ffeaa7;
  --text-color: #2d3436;
}

body {
  font-family: Arial, sans-serif;
  color: var(--text-color);
  background-color: #f5f6fa;
  padding: 20px;
}

h1 {
  color: var(--primary-color);
}

button {
  background-color: var(--primary-color);
  color: var(--secondary-color);
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
```

### Rozwiązanie zadania 2

**CSS:**
```css
:root {
  --base-font-size: 16px;
}

body {
  font-size: var(--base-font-size);
}

.big-text {
  --base-font-size: 24px;
  font-size: var(--base-font-size);
}
```