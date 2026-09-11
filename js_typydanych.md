# Typy Danych w JavaScript

JavaScript dzieli swoje typy danych na dwie główne kategorie: **typy proste (pierwotne, primitive)** oraz **typy złożone (referencyjne, reference)**. Różnią się one sposobem, w jaki są przechowywane w pamięci komputera.

---

## 1. Typy proste (Primitive Types)

Typy proste przechowują pojedyncze wartości bezpośrednio w pamięci (na stosie). Są niemutowalne, co oznacza, że ich wartości nie można zmodyfikować po utworzeniu – każda operacja zmieniająca wartość tworzy tak naprawdę nową.

* **`string` (łańcuch znaków):** Służy do przechowywania tekstów, np. `"Cześć"`, `'JavaScript'`, `` `Witaj ${imie}` ``.
* **`number` (liczba):** Reprezentuje zarówno liczby całkowite, jak i zmiennoprzecinkowe, np. `42`, `3.14`. W JavaScript obsługuje także specjalne wartości numeryczne: `Infinity`, `-Infinity` oraz `NaN` (Not-a-Number).
* **`bigint` (duża liczba):** Używany do reprezentowania liczb całkowitych o dowolnie dużej precyzji, przekraczających bezpieczny limit typu `number` ($2^{53} - 1$). Definiuje się go dodając literę `n` na końcu, np. `9007199254740991n`.
* **`boolean` (logiczny):** Przyjmuje tylko dwie wartości określające prawda/fałsz: `true` lub `false`.
* **`undefined`:** Wartość przypisywana automatycznie zmiennym, które zostały zadeklarowane, ale nie zostały jeszcze zainicjalizowane (nie przypisano im żadnej wartości).
* **`null`:** Celowy brak jakiejkolwiek wartości lub obiektu. W przeciwieństwie do `undefined`, musi zostać przypisany przez programistę. *(Ciekawostka: operator `typeof null` zwraca `'object'` ze względów historycznych).*
* **`symbol`:** Wprowadzony w ES6, służy do tworzenia unikalnych i niemutowalnych identyfikatorów, często wykorzystywanych jako klucze właściwości obiektów, aby uniknąć konfliktów nazw.

---

## 2. Typy złożone / referencyjne (Reference Types)

W przeciwieństwie do typów prostych, typy złożone mogą przechowować kolekcje danych oraz bardziej skomplikowane struktury. Zmienna nie przechowuje samej wartości, lecz **referencję (adres w pamięci)** do miejsca, w którym ta wartość się znajduje.

* **`object` (obiekt):** Podstawowa struktura do przechowywania danych w postaci par klucz-wartość (właściwości i metody), np. `{ imie: 'Anna', wiek: 30 }`.
* **`array` (tablica):** Specjalny rodzaj obiektu służący do przechowywania uporządkowanych list danych, np. `['jabłko', 'banan', 'truskawka']`. Indeksowana od zera.
* **`function` (funkcja):** W JavaScript funkcje są obiektami pierwszoklasowymi (first-class citizens). Mogą być przypisywane do zmiennych, przekazywane jako argumenty i zwracane z innych funkcji.

---

## 3. Kluczowa różnica: Wartość vs Referencja

Zrozumienie przekazywania danych jest kluczowe podczas pisania kodu w JS:

### Kopiowanie przez wartość (typy proste)
```javascript
let a = 10;
let b = a; // b otrzymuje kopię wartości
b = 20;
console.log(a); // 10 (a pozostaje bez zmian)
