# Instrukcja warunkowa `switch` w JavaScript

Cześć! W tym materiale nauczymy się, jak korzystać z instrukcji `switch` w języku JavaScript. To niezwykle przydatne narzędzie, gdy musimy sprawdzić jedną zmienną pod kątem wielu różnych wartości, unikając przy tym pisania długich i skomplikowanych ciągów `if...else if...else`.

---

## 1. Czym jest instrukcja `switch`?

Instrukcja `switch` służy do wykonywania różnych bloków kodu w zależności od wyników porównania. Działa ona następująco:
1. Wyrażenie w nawiasie `switch(wyrażenie)` jest wyliczane raz.
2. Wartość tego wyrażenia jest porównywana (z uwzględnieniem ścisłego porównania typów i wartości, jak `===`) z wartościami kolejnych przypadków (`case`).
3. Jeśli zostanie znalezione dopasowanie, uruchamiany jest przypisany do niego kod.
4. Słowo kluczowe `break` przerywa działanie instrukcji i wychodzi z niej. Jeśli zapomnisz `break`, program wykona również kod z kolejnych przypadków!
5. Klauzula `default` działa podobnie jak `else` – uruchamia się wtedy, gdy żaden z wcześniejszych przypadków nie pasował.

---

## 2. Składnia i Przykłady

### Podstawowy przykład (Dni tygodnia)

```javascript
let dzienTygodnia = 3;
let nazwaDnia;

switch (dzienTygodnia) {
  case 1:
    nazwaDnia = "Poniedziałek";
    break;
  case 2:
    nazwaDnia = "Wtorek";
    break;
  case 3:
    nazwaDnia = "Środa";
    break;
  case 4:
    nazwaDnia = "Czwartek";
    break;
  case 5:
    nazwaDnia = "Piątek";
    break;
  default:
    nazwaDnia = "Weekend!";
}

console.log(nazwaDnia); // Wynik: Środa
```

### Grupowanie przypadków
Możesz połączyć kilka instrukcji `case`, jeśli mają one wykonać dokładnie ten sam blok kodu:

```javascript
let miesiac = "styczeń";

switch (miesiac) {
  case "grudzień":
  case "styczeń":
  case "luty":
    console.log("Mamy zimę ❄️");
    break;
  case "czerwiec":
  case "lipiec":
  case "sierpień":
    console.log("Mamy lato ☀️");
    break;
  default:
    console.log("Wiosna lub jesień 🍂");
}
```

---

## 3. Zadania dla uczniów

### Zadanie 1: Ocena słowna
Napisz program z użyciem instrukcji `switch`, który dla zmiennej `ocena` (liczba całkowita od 1 do 6) przypisze do zmiennej `komentarz` odpowiedni opis słowny:
* 1 – "Niedostateczny"
* 2 – "Dopuszczający"
* 3 – "Dostateczny"
* 4 – "Dobry"
* 5 – "Bardzo dobry"
* 6 – "Celujący"
* Domyślnie (dla innych wartości) – "Nieznana ocena"

### Zadanie 2: Kalkulator operacji znakowych
Stwórz prosty kalkulator oparty na zmiennej `operator` (która może przyjmować wartości `'+'`, `'-'`, `'*'`, `'/'`) oraz dwóch liczbach `a` i `b`. Użyj `switch` do wykonania odpowiedniego działania matematycznego i wypisz wynik. Obsłuż przypadek nieznanego operatora w sekcji `default` oraz zabezpiecz przed dzieleniem przez zero.

---

## 4. Rozwiązania zadań

### Rozwiązanie zadania 1
```javascript
let ocena = 4;
let komentarz;

switch (ocena) {
  case 1:
    komentarz = "Niedostateczny";
    break;
  case 2:
    komentarz = "Dopuszczający";
    break;
  case 3:
    komentarz = "Dostateczny";
    break;
  case 4:
    komentarz = "Dobry";
    break;
  case 5:
    komentarz = "Bardzo dobry";
    break;
  case 6:
    komentarz = "Celujący";
    break;
  default:
    komentarz = "Nieznana ocena";
}

console.log(komentarz); // Wynik: Dobry
```

### Rozwiązanie zadania 2
```javascript
let a = 10;
let b = 5;
let operator = '*';
let wynik;

switch (operator) {
  case '+':
    wynik = a + b;
    break;
  case '-':
    wynik = a - b;
    break;
  case '*':
    wynik = a * b;
    break;
  case '/':
    if (b !== 0) {
      wynik = a / b;
    } else {
      wynik = "Nie można dzielić przez zero!";
    }
    break;
  default:
    wynik = "Błąd: nieznany operator!";
}

console.log("Wynik:", wynik); // Wynik: 50
```