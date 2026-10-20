# Tablice i Operacje na DOM w JavaScript (INF.03)

## 1. Tablice Indeksowane (Zwykłe)

Tablice indeksowane służą do przechowywania uporządkowanych list wartości. Indeksowanie w JavaScript zawsze zaczyna się od **0**.

### Tworzenie i dostęp do elementów

```javascript
// Tworzenie tablicy
const owoce = ["jabłko", "banan", "pomarańcza"];

// Dostęp do elementów
console.log(owoce[0]); // "jabłko"
console.log(owoce[1]); // "banan"

// Długość tablicy
console.log(owoce.length); // 3
```

### Najważniejsze metody tablic (często na egzaminie INF.03)

* **`push(element)`** – dodaje element na końcu tablicy.
* **`pop()`** – usuwa ostatni element z tablicy.
* **`unshift(element)`** – dodaje element na początku tablicy.
* **`shift()`** – usuwa pierwszy element z tablicy.
* **`indexOf(element)`** – zwraca indeks podanego elementu (lub -1, jeśli brak).
* **`includes(element)`** – sprawdza, czy element znajduje się w tablicy (zwraca `true`/`false`).
* **`forEach()`** – iteracja po wszystkich elementach tablicy.

#### Przykład iteracji:

```javascript
const liczby = [10, 20, 30, 40];

liczby.forEach(function(liczba, indeks) {
  console.log("Element " + indeks + ": " + liczba);
});
```

### Dodatkowe przykłady użycia tablic

#### Wyszukiwanie maksymalnej i minimalnej liczby w tablicy
```javascript
let oceny = [3, 5, 2, 4, 6, 5];
let max = oceny[0];
let min = oceny[0];

for (let i = 1; i < oceny.length; i++) {
  if (oceny[i] > max) {
    max = oceny[i];
  }
  if (oceny[i] < min) {
    min = oceny[i];
  }
}

console.log("Najwyższa ocena: " + max);
console.log("Najniższa ocena: " + min);
```

#### Filtrowanie elementów (wyciąganie liczb parzystych)
```javascript
let liczby = [12, 5, 8, 19, 22, 7];
let parzyste = [];

for (let i = 0; i < liczby.length; i++) {
  if (liczby[i] % 2 === 0) {
    parzyste.push(liczby[i]); // dodajemy do nowej tablicy
  }
}

console.log("Liczby parzyste: " + parzyste); // Wynik: 12, 8, 22
```

---

## 2. "Tablice Asocjacyjne" (Obiekty w JS)

JavaScript nie posiada klasycznych tablic asocjacyjnych takich jak np. PHP. Zamiast tego używa się **Obiektów**, które przechowują dane w postaci par **klucz: wartość** (`key: value`).

### Tworzenie obiektu i dostęp do danych

```javascript
// Definicja obiektu
const uczen = {
  imie: "Jan",
  nazwisko: "Kowalski",
  wiek: 18,
  klasa: "4TI"
};

// Dostęp za pomocą kropki (Dot notation)
console.log(uczen.imie); // "Jan"

// Dostęp za pomocą nawiasów kwadratowych (Bracket notation)
console.log(uczen["nazwisko"]); // "Kowalski"

// Modyfikacja i dodawanie nowych pól
uczen.srednia = 4.5;
uczen["wiek"] = 19;
```

### Iteracja po obiektach (`for...in`)

```javascript
for (let klucz in uczen) {
  console.log(klucz + ": " + uczen[klucz]);
}
```

### Przykład: Tablica obiektów (struktura bazodanowa)

Na egzaminie dane często reprezentowane są jako tablica obiektów (np. lista pracowników lub produktów).

```javascript
let pracownicy = [
  { imie: "Anna", stanowisko: "Programista", placa: 7500 },
  { imie: "Jan", stanowisko: "Tester", placa: 5500 },
  { imie: "Katarzyna", stanowisko: "Grafik", placa: 6000 }
];

// Wyświetlenie imion wszystkich pracowników w konsoli
for (let i = 0; i < pracownicy.length; i++) {
  console.log(pracownicy[i].imie + " pracuje jako " + pracownicy[i].stanowisko);
}
```

---

## 3. Manipulacja Obiektowym DOM (Document Object Model)

Model DOM reprezentuje strukturę strony HTML jako drzewo obiektów, do których mamy dostęp z poziomu kodu JavaScript.

### Pobieranie elementów z dokumentu

```javascript
// 1. Pobranie po ID (zwraca jeden element)
const naglowek = document.getElementById("tytul");

// 2. Pobranie po klasie (zwraca HTMLCollection / tablicopodobną strukturę)
const elementy = document.getElementsByClassName("opis");

// 3. Nowoczesne metody Query Selector
const przycisk = document.querySelector("#btnSubmit"); // Pierwszy pasujący (po ID)
const wiersze = document.querySelectorAll(".wiersz");  // Wszystkie pasujące (NodeList)
```

### Modyfikacja zawartości i atrybutów

```javascript
const blok = document.getElementById("kontener");

// Zmiana tekstu (bezpieczna)
blok.textContent = "Witaj na stronie!";

// Zmiana struktury HTML
blok.innerHTML = "<h2>Nowy nagłówek</h2><p>Opis...</p>";

// Zmiana stylów CSS
blok.style.backgroundColor = "lightblue";
blok.style.fontSize = "20px";

// Dodawanie/usuwanie klas CSS
blok.classList.add("aktywny");
blok.classList.remove("ukryty");
blok.classList.toggle("podswietlony");
```

### Dodatkowe przykłady manipulacji DOM

#### Zmiana atrybutu (np. podmiana zdjęcia)
```html
<img id="zdjecie" src="obraz1.jpg" alt="Zdjęcie główne" width="200">
<br>
<button onclick="zmienObraz()">Zmień obraz</button>

<script>
  function zmienObraz() {
    let img = document.getElementById("zdjecie");
    
    if (img.src.includes("obraz1.jpg")) {
      img.src = "obraz2.jpg";
      img.alt = "Drugie zdjęcie";
    } else {
      img.src = "obraz1.jpg";
      img.alt = "Zdjęcie główne";
    }
  }
</script>
```

#### Odczyt danych z pól formularza i walidacja
```html
<label>Imię: <input type="text" id="poleImie"></label><br>
<label><input type="checkbox" id="zgoda"> Zgoda marketingowa</label><br>
<button onclick="sprawdzFormularz()">Wyślij</button>

<p id="komunikat"></p>

<script>
  function sprawdzFormularz() {
    let imie = document.getElementById("poleImie").value;
    let zgodaZaznaczona = document.getElementById("zgoda").checked;
    let wynik = document.getElementById("komunikat");

    if (imie === "") {
      wynik.textContent = "Proszę wpisać imię!";
      wynik.style.color = "red";
    } else if (!zgodaZaznaczona) {
      wynik.textContent = "Musisz wyrazić zgodę, " + imie + "!";
      wynik.style.color = "orange";
    } else {
      wynik.textContent = "Dziękujemy, " + imie + "! Formularz wysłany pomyślnie.";
      wynik.style.color = "green";
    }
  }
</script>
```

---

## 4. Przykład Integracji: Tablice + DOM (Wzorzec INF.03)

Kompletny przykład HTML + JS przedstawiający wygenerowanie listy produktów z tablicy obiektów po kliknięciu przycisku.

```html
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <title>INF.03 - Tablice i DOM</title>
  <style>
    .produkt { margin: 5px 0; padding: 5px; border-bottom: 1px solid #ccc; }
  </style>
</head>
<body>

  <button id="btnPobierz">Wyświetl Produkty</button>
  <div id="lista-produktow"></div>

  <script>
    // Tablica obiektów (częsty format danych)
    const produkty = [
      { nazwa: "Klawiatura", cena: 120 },
      { nazwa: "Myszka", cena: 80 },
      { nazwa: "Monitor", cena: 650 }
    ];

    const przycisk = document.getElementById("btnPobierz");
    const kontener = document.getElementById("lista-produktow");

    przycisk.addEventListener("click", function() {
      kontener.innerHTML = ""; // Czyszczenie widoku

      produkty.forEach(function(item) {
        let div = document.createElement("div");
        div.className = "produkt";
        div.textContent = item.nazwa + " - Cena: " + item.cena + " zł";
        kontener.appendChild(div);
      });
    });
  </script>
</body>
</html>
```

---

## 5. Zadania do Samodzielnego Rozwiązania

### Zadanie 1: Licznik i Średnia z Tablicy
Napisz skrypt, który zawiera tablicę z ocenami `[3, 4, 5, 2, 4, 5]`. Za pomocą metody `forEach` oblicz ich sumę oraz średnią ocen, a wynik wyświetl w nagłówku `<h3>` na stronie.

### Zadanie 2: Obiekt Książka
Utwórz obiekt `ksiazka` posiadający właściwości: `tytul`, `autor`, `rokwydania`. Wyświetl te informacje na stronie w postaci listy punktowanej `<ul>`.

### Zadanie 3: Dynamiczne Dodawanie do Tablicy i DOM
Przygotuj formularz z dwoma polami tekstowymi (Imię, Nazwisko) oraz przyciskiem. Po kliknięciu przycisku skrypt ma utworzyć obiekt z podanymi danymi, dodać go do globalnej tablicy, a następnie dopisać nowy wiersz do tabeli HTML `<table>`.
