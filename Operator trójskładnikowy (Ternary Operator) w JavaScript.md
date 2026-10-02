# Operator trójskładnikowy (Ternary Operator) w JavaScript

Cześć! Dzisiaj nauczymy się jednego z najprzydatniejszych skrótów w języku JavaScript – **operatora trójskładnikowego** (ang. *ternary operator*). Jest to elegancki i szybki sposób na zapisanie prostych instrukcji warunkowych `if...else`.

---

## 1. Czym jest operator trójskładnikowy?

Zamiast pisać długi blok kodu z użyciem tradycyjnego `if` i `else`, możemy zamknąć ten sam warunek w jednej linii kodu. 

Nazwa "trójskładnikowy" bierze się stąd, że jest to jedyny operator w JavaScript, który przyjmuje **trzy argumenty** (operandy):
1. **Warunek** (który zwraca wartość logiczną `true` lub `false`).
2. Wyrażenie wykonywane, gdy warunek jest **prawdziwy** (`true`).
3. Wyrażenie wykonywane, gdy warunek jest **fałszywy** (`false`).

---

## 2. Składnia (Jak to się pisze?)

Oto ogólny wzór budowy takiego wyrażenia:

```javascript
warunek ? wyrażenie_jeśli_prawda : wyrażenie_jeśli_fałsz;
```

* Znak zapytania (`?`) oddziela warunek od kodu, który wykona się w przypadku sukcesu.
* Dwukropek (`:`) działa jak słowo kluczowe `else` i oddziela obie ścieżki wyboru.

---

## 3. Porównanie z tradycyjnym `if...else`

Wyobraź sobie, że chcemy sprawdzić wiek użytkownika i zdecydować, czy może głosować.

### Tradycyjny zapis z `if...else`:
```javascript
let wiek = 20;
let status;

if (wiek >= 18) {
  status = "Możesz głosować";
} else {
  status = "Jesteś za młody";
}

console.log(status); // "Możesz głosować"
```

### Zapis za pomocą operatora trójskładnikowego:
```javascript
let wiek = 20;
let status = (wiek >= 18) ? "Możesz głosować" : "Jesteś za młody";

console.log(status); // "Możesz głosować"
```

Zauważ, jak zwięzły stał się nasz kod! Zamiast pięciu linijek kodu zajmujących zmienną, użyliśmy tylko jednej instrukcji.

---

## 4. Przykład praktyczny: Sprawdzanie pełnoletności

Przeanalizujmy kolejny przykład z wartościami numerycznymi:

```javascript
let wiek = 15;
let czyPelnoletni = (wiek >= 18) ? "Tak" : "Nie";

console.log(czyPelnoletni); // Wynik: "Nie"
```

---

## 5. Kiedy warto stosować operator trójskładnikowy?

* **Do prostych przypisań:** Kiedy chcesz przypisać jedną z dwóch wartości do zmiennej w zależności od prostego warunku.
* **Do czytelności (w umiarze):** Kod staje się krótszy i bardziej przejrzysty.

> **Ważna uwaga:** Unikaj "zagnieżdżania" operatorów trójskładnikowych w sobie (np. warunek ? (inny_warunek ? a : b) : c). Zamiast pomóc, sprawi to, że kod stanie się trudny do odczytania i zrozumienia przez innych programistów! W skomplikowanych przypadkach zawsze lepiej użyć tradycyjnego `if...else` lub instrukcji `switch`.

---

## 💡 Podsumowanie w pigułce

* Operator trójskładnikowy to skrótowa wersja `if...else`.
* Składa się z pytajnika (`?`) oraz dwukropka (`:`).
* Świetnie nadaje się do zwięzłego przypisywania wartości zmiennym na podstawie prostych warunków.
