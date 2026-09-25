# Kompleksowy przewodnik po `console.log` i metodach konsoli w JavaScript

Funkcja `console.log()` to jedno z pierwszych i najważniejszych narzędzi, z którymi spotyka się każdy programista JavaScript. Służy do wypisywania komunikatów w konsoli deweloperskiej (w przeglądarce lub w środowisku Node.js). Jest niezastąpiona podczas debugowania, czyli szukania błędów i śledzenia przepływu danych w aplikacji.

---

## Część 1: Teoria i przykłady

### 1. Podstawowe wypisywanie wartości
Możesz przekazać do `console.log` dowolny typ danych: tekst (string), liczbę, wartość logiczną (boolean), a także wiele argumentów oddzielonych przecinkami.

```javascript
console.log("Witaj w świecie JavaScript!");
let punkty = 150;
console.log("Twoje punkty:", punkty);
```

### 2. Nowoczesna interpolacja tekstowa (Template Literals)
Zamiast łączyć teksty i zmienne za pomocą znaków plus (`+`), warto używać ukośnych apostrofów (backticks: `` ` ``) oraz składni `${zmienna}`.

```javascript
let imie = "Kamil";
let poziom = 5;
console.log(`Gracz ${imie} osiągnął ${poziom} poziom.`);
```

### 3. Złożone struktury: Tablice i Obiekty
Konsola doskonale radzi sobie z wyświetlaniem kolekcji danych. Możesz je rozwijać, aby podejrzeć ich strukturę wewnętrzną.

```javascript
let uzytkownik = { id: 1, login: "jan_kowalski", aktywny: true };
let kategorie = ["Frontend", "Backend", "DevOps"];

console.log("Użytkownik:", uzytkownik);
console.log("Kategorie:", kategorie);
```

### 4. Specjalistyczne metody obiektu `console`
Poza klasycznym `log()`, do dyspozycji masz inne przydatne metody:
*   `console.error("Błąd!")` – wyświetla komunikat na czerwono (błąd krytyczny).
*   `console.warn("Uwaga!")` – wyświetla komunikat na żółto (ostrzeżenie).
*   `console.table(dane)` – przedstawia tablicę obiektów w postaci przejrzystej tabeli.

---


```javascript
// Twoje rozwiązanie:
