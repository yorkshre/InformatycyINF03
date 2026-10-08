# Ćwiczenia JavaScript: Instrukcje warunkowe oraz Operator Trójskładnikowy

Poniższy zestaw instrukcji i zadań pozwala przećwiczyć użycie konstrukcji `if...else` oraz operatora trójskładnikowego w praktyce (inspirowane m.in. logiką gotowania jajek na odpowiedni czas).

---

## 1. Wprowadzenie teoretyczne

### Instrukcja warunkowa `if...else`
Służy do wykonywania różnych bloków kodu w zależności od spełnienia określonych warunków.
```javascript
let zmienna = wartosc;

if (warunekPierwszy) {
    // Kod wykonywany, gdy warunekPierwszy jest prawdziwy (true)
} else if (warunekDrugi) {
    // Kod wykonywany, gdy warunekDrugi jest prawdziwy
} else {
    // Kod wykonywany, gdy żaden z powyższych warunków nie został spełniony
}
```

### Operator trójskładnikowy (`? :`)
Jest skróconą formą zapisu instrukcji `if...else`, idealną do przypisywania wartości do zmiennych na podstawie prostego warunku.
```javascript
let zmienna = (warunek) ? "Wartość gdy true" : "Wartość gdy false";
```

---

## 2. Zadania praktyczne

### Zadanie 1: Klasyczna instrukcja `if...else if...else`
Napisz skrypt w JavaScript, który realizuje następującą logikę opartą o czas gotowania jajka:
* Zdefiniuj zmienną `czasGotowania` i przypisz jej wybraną liczbę minut (np. `6`).
* Za pomocą rozbudowanej instrukcji `if...else` sprawdź:
  1. Jeśli `czasGotowania <= 4`, wypisz w konsoli: `"Jajko na miękko"`.
  2. Jeśli `czasGotowania > 4` i `czasGotowania <= 7`, wypisz: `"Jajko średnie (na półmiękko)"`.
  3. W każdym innym przypadku (powyżej 7 minut), wypisz: `"Jajko na twardo"`.

### Zadanie 2: Operator trójskładnikowy (pojedynczy)
* Zdefiniuj zmienną `minuty = 8`.
* Użyj **operatora trójskładnikowego**, aby przypisać do nowej zmiennej `statusJajka` napis `"Gotowe do wyciągnięcia"`, jeśli czas jest mniejszy lub równy 8 minut, w przeciwnym razie przypisz `"Zbyt długo gotowane"`.
* Wyświetl wynik w konsoli za pomocą `console.log(statusJajka)`.

### Zadanie 3: Zagnieżdżony operator trójskładnikowy
* Zdefiniuj zmienną `minuty = 5`.
* Stwórz jedną instrukcję z użyciem **zagnieżdżonego operatora trójskładnikowego**, która rozstrzygnie:
  * Jeśli `minuty <= 4` -> `"Na miękko"`
  * W przeciwnym razie, jeśli `minuty <= 7` -> `"Na półmiękko"`
  * W przeciwnym razie -> `"Na twardo"`
* Przypisz wynik do zmiennej i wyświetl go w konsoli.
```
