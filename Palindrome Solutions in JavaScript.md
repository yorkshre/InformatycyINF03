# Palindromy w JavaScript: Od najprostszego do najtrudniejszego rozwiązania

Sprawdzenie, czy dany ciąg znaków jest palindromem (czyli czy czyta się go tak samo od przodu, jak i od tyłu), to klasyczne zadanie programistyczne. Poniżej przedstawiam trzy podejścia o rosnącym stopniu zaawansowania.

---

## 1. Poziom Podstawowy: Metody wbudowane (One-liner)

To najkrótsze i najwygodniejsze podejście do szybkiego rozwiązywania prostych zadań. Wykorzystuje wbudowane w JavaScript metody dla stringów i tablic.

### Jak to działa:
1. `toLowerCase()` – konwertuje cały tekst na małe litery, aby wielkość znaków nie wpłynęła na wynik.
2. `split('')` – dzieli string na tablicę pojedynczych znaków.
3. `reverse()` – odwraca kolejność elementów w tablicy.
4. `join('')` – scala tablicę z powrotem w ciąg znaków.
5. Na koniec porównujemy tak powstały odwrócony ciąg z oryginalnym.

### Kod źródłowy:
```javascript
function isPalindrome(str) {
    const cleaned = str.toLowerCase();
    return cleaned === cleaned.split('').reverse().join('');
}

// Przykłady użycia:
console.log(isPalindrome("Kajak")); // true
console.log(isPalindrome("JavaScript")); // false
```

### Zalety i wady:
* **Zalety:** Bardzo czytelny, krótki kod idealny do codziennego użytku przy prostych danych.
* **Wady:** Tworzy w pamięci dodatkowe obiekty (tablice), co przy bardzo dużych tekstach nie jest najbardziej optymalne.

---

## 2. Poziom Średniozaawansowany: Tradycyjna pętla `for`

To podejście pozwala zrozumieć mechanikę odwracania stringa "od środka" bez polegania na gotowej metodzie `reverse()`.

### Jak to działa:
1. Inicjalizujemy pusty string `reversed`.
2. Uruchamiamy pętlę `for`, która startuje od ostatniego indeksu stringa (`cleaned.length - 1`) i idzie w stronę zera.
3. W każdym kroku doklejamy kolejny znak do zmiennej `reversed`.
4. Porównujemy oryginalny ciąg z odwróconym.

### Kod źródłowy:
```javascript
function isPalindrome(str) {
    const cleaned = str.toLowerCase();
    let reversed = '';

    for (let i = cleaned.length - 1; i >= 0; i--) {
        reversed += cleaned[i];
    }

    return cleaned === reversed;
}

// Przykłady użycia:
console.log(isPalindrome("radar")); // true
console.log(isPalindrome("auto")); // false
```

### Zalety i wady:
* **Zalety:** Dobry trening logiczny, jawnie pokazuje algorytmiczne podejście do manipulacji indeksami.
* **Wady:** Podobnie jak poziom pierwszy, nadal alokuje pamięć na nowy string `reversed`.

---

## 3. Poziom Zaawansowany: Dwa wskaźniki (Two Pointers)

To najbardziej wydajne podejście, często oczekiwane na rozmowach kwalifikacyjnych. Pozwala m.in. ignorować spacje oraz znaki interpunkcyjne w zdaniach (np. *"Kobyła ma mały bok"*).

### Jak to działa:
1. Używamy wyrażenia regularnego `[^a-z0-9]`, aby pozbyć się spacji, wielkich liter i znaków specjalnych.
2. Ustawiamy dwa wskaźniki: `left` na samym początku stringa (indeks `0`) oraz `right` na samym końcu (`length - 1`).
3. Porównujemy znaki pod obu wskaźnikami. Jeśli są różne, natychmiast zwracamy `false` (nie musimy przetwarzać reszty tekstu).
4. Przesuwamy wskaźnik `left` w prawo, a `right` w lewo, dopóki się nie spotkają.

### Kod źródłowy:
```javascript
function isPalindrome(str) {
    // Czyszczenie: zostawiamy tylko małe litery i cyfry
    const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, '');
    
    let left = 0;
    let right = cleaned.length - 1;

    while (left < right) {
        if (cleaned[left] !== cleaned[right]) {
            return false; // Znaleziono niezgodność
        }
        left++;
        right--;
    }

    return true;
}

// Przykłady użycia (ze spacjami i interpunkcją):
console.log(isPalindrome("Kobyła ma mały bok")); // true
console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
```

### Zalety i wady:
* **Zalety:** Najwyższa wydajność, doskonała skalowalność dla wielkich tekstów oraz wbudowana obsługa interpunkcji.
* **Wady:** Nieco bardziej skomplikowany kod na pierwszy rzut oka.

---

## Podsumowanie wydajności

| Poziom | Złożoność czasowa | Złożoność pamięciowa | Obsługa spacji/interpunkcji |
| :--- | :--- | :--- | :--- |
| **1. Wbudowane metody** | $O(N)$ | $O(N)$ | Wymaga dodatkowego czyszczenia |
| **2. Pętla `for`** | $O(N)$ | $O(N)$ | Wymaga dodatkowego czyszczenia |
| **3. Dwa wskaźniki** | $O(N)$ | $O(1)$ (poza stringiem) | Tak, wbudowana |