# Pętla `while` w JavaScript

Pętla `while` wykonuje blok kodu tak długo, jak długo podany warunek jest prawdziwy (`true`). Jest szczególnie przydatna, gdy nie wiemy z góry, ile razy pętla powinna się powtórzyć.

## Składnia

```javascript
while (warunek) {
  // kod do wykonania w każdej iteracji
}
```

---

## Przykłady użycia pętli `while`

### 1. Zliczanie / Iteracja (Podstawowy licznik)
Klasyczne użycie pętli `while` do wyświetlenia kolejnych liczb.

```javascript
let i = 1;

while (i <= 5) {
  console.log("Krok: " + i);
  i++; // Pamiętaj o inkrementacji, aby uniknąć nieskończonej pętli!
}
```

---

### 2. Pobieranie danych od użytkownika z walidacją
Pętla powtarza zapytanie `prompt()` tak długo, aż użytkownik poda poprawną wartość (np. liczbę dodatnią).

```javascript
let podanaLiczba = parseInt(prompt("Podaj liczbę dodatnią:"));

while (isNaN(podanaLiczba) || podanaLiczba <= 0) {
  podanaLiczba = parseInt(prompt("Błąd! Wpisz poprawną liczbę dodatnią:"));
}

console.log("Dziękuję, podałeś liczbę: " + podanaLiczba);
```



### 3. Generowanie elementów na stronie (DOM + INF.03)
Tworzenie punktów listy `<ul>` na podstawie danych.

```html
<ul id="lista-wynikow"></ul>

<script>
  let numer = 1;
  const lista = document.getElementById("lista-wynikow");

  while (numer <= 4) {
    let li = document.createElement("li");
    li.textContent = "Element numer " + numer;
    lista.appendChild(li);
    numer++;
  }
</script>
```
---
## 1. Pętle sterowane warunkiem (`while` oraz `do..while`)

W przeciwieństwie do pętli `for`, w pętlach warunkowych **nie musimy z góry określać dokładnej liczby iteracji**. Kod wewnątrz pętli wykonuje się powtarzalnie, dopóki warunek zawarty w nawiasie zwraca wartość logiczną `true`.

### Porównanie pętli `while` i `do..while`

| Cecha | Pętla `while` | Pętla `do..while` |
| :--- | :--- | :--- |
| **Moment sprawdzania warunku** | **Na początku** bloku (przed wykonaniem kodu) | **Na końcu** bloku (po wykonaniu kodu) |
| **Gwarantowana liczba wykonań** | **`0` razy** (gdy warunek od razu jest fałszywy) | **Minimum `1` raz** (kod zawsze uruchomi się przynajmniej raz) |
| **Główne zastosowanie** | Gdy wykonanie bloku zależy od wstępnego warunku | Gdy akcja musi wykonać się co najmniej raz (np. pobranie danych) |

---

### Przykłady kodu

```javascript
// Pętla while – warunek sprawdzany na początku
let puszki = 0;

while (puszki > 0) {
    console.log("To się NIGDY nie wyświetli, bo puszki = 0");
    puszki--;
}

// Pętla do..while – warunek sprawdzany na końcu
do {
    console.log("To wyświetli się DOKŁADNIE RAZ, mimo że puszki = 0");
    puszki--;
} while (puszki > 0);


// Deklaruje zmienną i przypisuje jej wartość "napoju energetycznego".
var drink = "napoju energetycznego";

// Deklaruje kolejną zmienną i przypisuje jej pusty łańcuch znaków.
var lyrics = "";

// Deklaruje jeszcze jedną zmienną i przypisuje jej wartość liczbową 99.
var cans = 99;

// To jest pętla while, której działanie można opisać tak: dopóki liczba puszek jest
// większa od 0, wykonuje cały kod zawarty w nawiasach klamrowych. Zatrzymuje się,
// gdy już nie została żadna puszka.
while (cans > 0) {

    // Do zmiennej lyrics dodaje za pomocą operatora konkatenacji łańcuchów (+) kolejny wers tekstu piosenki.
    // Wers kończy się HTML-owym znacznikiem nowego wiersza.
    lyrics = lyrics + cans + " puszek "
           + drink + " stoi przy ścianie <br>";

    // I jeszcze raz to samo — przecież tak leci ta piosenka, prawda?
    lyrics = lyrics + cans + " puszek "
           + drink + "<br>";

    // Dodaje kolejny wers, też za pomocą konkatenacji.
    lyrics = lyrics + "Weź jedną i podaj dalej<br>";

    // Jeśli zostały jeszcze jakieś puszki (to znaczy wartość zmiennej cans jest większa od 1)...
    if (cans > 1) {
        // ...dodaj ostatni wers.
        lyrics = lyrics + (cans - 1) + " puszek "
               + drink + " stoi przy ścianie <br>";
    } 
    // W przeciwnym przypadku nie ma już żadnej puszki...
    else {
        // ...więc na końcu tekstu dodaj wers „Żadna puszka...”.
        lyrics = lyrics + "Żadna puszka "
               + drink + " już nie stoi przy ścianie <br>";
    }

    // Zmniejsza liczbę puszek o jeden.
    cans = cans - 1;
}

// Wszystkie wersy piosenki zostały zapisane w zmiennej lyrics, więc teraz możemy je
// wyświetlić na stronie. Jest to równoważne z dodaniem łańcucha do strony, tak by był
// na niej widoczny.
document.write(lyrics);
```




---

## Ćwiczenia praktyczne z rozwiązaniami

### Ćwiczenie 1: Sumowanie liczb od 1 do N
Napisz skrypt, który pobiera od użytkownika liczbę całkowitą $N$, a następnie za pomocą pętli `while` oblicza i wyświetla w konsoli sumę wszystkich liczb całkowitych od $1$ do $N$.

<details>
<summary>Zobacz rozwiązanie</summary>

```javascript
let n = parseInt(prompt("Podaj liczbę N:"));
let suma = 0;
let i = 1;

while (i <= n) {
  suma += i;
  i++;
}

console.log("Suma liczb od 1 do " + n + " wynosi: " + suma);
```
</details>

---

### Ćwiczenie 2: Dzielenie przez 2 (Licznik podziałów)
Napisz program, który przyjmuje dodatnią liczbę całkowitą i dzieli ją przez 2 tak długo, jak długo wynik jest większy lub równy 1. Program powinien zliczyć, ile razy wykonano dzielenie, i wypisać wynik w konsoli.

<details>
<summary>Zobacz rozwiązanie</summary>

```javascript
let liczba = 100;
let ileRazy = 0;

while (liczba >= 1) {
  liczba = liczba / 2;
  ileRazy++;
}

console.log("Wykonano podziałów: " + ileRazy);
```
</details>

---

### Ćwiczenie 3: Zadanie w stylu egzaminacyjnym INF.03 / EE.09
Utwórz formularz HTML zawierający jedno pole tekstowe (liczba początkowa) oraz przycisk „Generuj liczby parzyste”. Po kliknięciu przycisku skrypt za pomocą pętli `while` wygeneruje i wyświetli w bloku `<div>` kolejne liczby parzyste mniejsze bądź równe 20, zaczynając od liczby wpisanej przez użytkownika.

<details>
<summary>Zobacz rozwiązanie</summary>

```html
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <title>INF.03 - Pętla while</title>
</head>
<body>
  <label for="start">Liczba startowa:</label>
  <input type="number" id="start" value="2">
  <button onclick="generuj()">Generuj liczby parzyste</button>

  <div id="wynik"></div>

  <script>
    function generuj() {
      let a = parseInt(document.getElementById("start").value);
      let kontener = document.getElementById("wynik");
      kontener.innerHTML = ""; // Czyszczenie poprzednich wyników

      while (a <= 20) {
        if (a % 2 === 0) {
          kontener.innerHTML += a + "<br>";
        }
        a++;
      }
    }
  </script>
</body>
</html>
```
</details>

---

## Zadania do samodzielnego rozwiązania

### Zadanie A: Odliczanie startu rakiety
Napisz skrypt w JavaScript, który symuluje odliczanie przed startem rakiety. Pętla `while` powinna wypisywać w konsoli kolejne liczby od 10 do 1, a na samym końcu wyświetlić napis `"Start!"`.
* **Wskazówka:** Użyj zmiennej startowej równej `10` i dekrementuj ją (`i--`) w każdej iteracji.

---

### Zadanie B: Obliczanie silni
Stwórz program, który pobiera od użytkownika liczbę $N$ (np. za pomocą okienka `prompt`) i oblicza jej silnię ($N!$) przy użyciu pętli `while`. Wynik wypisz w konsoli.
* *Przypomnienie:* $5! = 1 \cdot 2 \cdot 3 \cdot 4 \cdot 5$.
* **Wskazówka:** Zmienna przechowująca wynik iloczynu musi startować od wartości `1`.

---

### Zadanie C: Interaktywna gra w zgadywanie
Napisz prostą grę, w której ukryta jest stała liczba (np. `7`). Użytkownik w pętli `while` ma za zadanie podawać liczby tak długo, aż poprawnie odgadnie ukrytą wartość.
* **Wskazówka:** Warunkiem pętli `while` może być sprawdzanie, czy wprowadzona wartość jest różna od liczby docelowej (`podana != szukana`).

---

### Zadanie D: Wypisanie liczb podzielnych przez 3 (Praktyka INF.03)
Przygotuj dokument HTML zawierający przycisk oraz blok `<div>` na wyniki. Po kliknięciu przycisku skrypt ma za pomocą pętli `while` znaleźć i wyświetlić w bloku `<div>` wszystkie liczby podzielne przez 3 z przedziału od 1 do 30.
* **Wskazówka:** Skorzystaj z operatora modulo (`% 3 === 0`) do weryfikacji podzielności.

