# JSON w JavaScript – lekcja INF.03

## Cele lekcji

Po lekcji uczeń:
- wyjaśnia, czym jest JSON,
- zna składnię JSON,
- rozróżnia JSON i obiekt JavaScript,
- stosuje `JSON.parse()` i `JSON.stringify()`,
- pracuje z tablicami obiektów,
- pobiera dane JSON za pomocą `fetch()`,
- wyświetla dane JSON w HTML,
- filtruje i przetwarza dane,
- wykonuje obliczenia,
- rozwiązuje zadania praktyczne INF.03.

---

## 1. Czym jest JSON?

**JSON (JavaScript Object Notation)** to tekstowy format zapisu i wymiany danych.

Przykład:

```json
{
    "imie": "Anna",
    "nazwisko": "Kowalska",
    "wiek": 18
}
```

Dane zapisujemy jako:

```text
"klucz": wartość
```

JSON jest często używany do:
- przechowywania danych,
- komunikacji klient–serwer,
- API,
- konfiguracji,
- wymiany danych między aplikacjami.

---

## 2. Składnia JSON

### Obiekt

```json
{
    "imie": "Anna",
    "wiek": 18
}
```

### Tablica obiektów

```json
[
    {
        "imie": "Anna",
        "wiek": 18
    },
    {
        "imie": "Jan",
        "wiek": 19
    }
]
```

### Typy danych

JSON obsługuje:
- tekst,
- liczby,
- `true` / `false`,
- `null`,
- tablice,
- obiekty.

Przykład:

```json
{
    "imie": "Anna",
    "wiek": 18,
    "aktywny": true,
    "telefon": null,
    "zainteresowania": ["programowanie", "muzyka"]
}
```

---

## 3. Najważniejsze zasady JSON

Klucze muszą być zapisane w cudzysłowie:

```json
{
    "imie": "Anna"
}
```

Elementy oddzielamy przecinkami:

```json
{
    "imie": "Anna",
    "wiek": 18
}
```

Nie dodajemy przecinka po ostatnim elemencie:

```json
{
    "imie": "Anna",
    "wiek": 18
}
```

---

# 4. JSON a JavaScript

JSON:

```json
{
    "imie": "Jan",
    "wiek": 20
}
```

JavaScript:

```javascript
const osoba = {
    imie: "Jan",
    wiek: 20
};
```

JSON jest **tekstem**, natomiast obiekt JavaScript jest obiektem programu.

---

# 5. JSON.parse()

`JSON.parse()` zamienia tekst JSON na obiekt JavaScript.

```javascript
const tekst = '{"imie":"Anna","wiek":18}';

const osoba = JSON.parse(tekst);

console.log(osoba.imie);
console.log(osoba.wiek);
```

Wynik:

```text
Anna
18
```

Schemat:

```text
JSON → obiekt JavaScript
```

---

# 6. JSON.stringify()

`JSON.stringify()` zamienia obiekt JavaScript na tekst JSON.

```javascript
const osoba = {
    imie: "Jan",
    wiek: 20
};

const tekst = JSON.stringify(osoba);

console.log(tekst);
```

Wynik:

```json
{"imie":"Jan","wiek":20}
```

Schemat:

```text
obiekt JavaScript → JSON
```

---

# 7. Ściąga

| Operacja | Funkcja |
|---|---|
| JSON → JavaScript | `JSON.parse()` |
| JavaScript → JSON | `JSON.stringify()` |

---

# 8. Odczytywanie właściwości

```javascript
const osoba = {
    imie: "Anna",
    nazwisko: "Kowalska",
    wiek: 18
};

console.log(osoba.imie);
console.log(osoba.nazwisko);
console.log(osoba.wiek);
```

Można również używać:

```javascript
console.log(osoba["imie"]);
```

---

# 9. Tablica obiektów

```javascript
const osoby = [
    {
        imie: "Anna",
        wiek: 18
    },
    {
        imie: "Jan",
        wiek: 19
    },
    {
        imie: "Piotr",
        wiek: 20
    }
];
```

Pierwszy element:

```javascript
osoby[0]
```

Imię pierwszej osoby:

```javascript
osoby[0].imie
```

---

# 10. Pętla for

```javascript
for (let i = 0; i < osoby.length; i++) {
    console.log(osoby[i].imie);
}
```

---

# 11. forEach()

```javascript
osoby.forEach(osoba => {
    console.log(osoba.imie);
});
```

---

# 12. Filtrowanie danych

```javascript
const uczniowie = [
    { imie: "Anna", punkty: 85 },
    { imie: "Jan", punkty: 62 },
    { imie: "Kasia", punkty: 91 }
];

uczniowie.forEach(uczen => {
    if (uczen.punkty >= 70) {
        console.log(uczen.imie);
    }
});
```

Wynik:

```text
Anna
Kasia
```

---

# 13. Obliczenia

```javascript
const produkty = [
    { nazwa: "Monitor", cena: 800 },
    { nazwa: "Laptop", cena: 3500 },
    { nazwa: "Mysz", cena: 100 }
];

let suma = 0;

produkty.forEach(produkt => {
    suma += produkt.cena;
});

console.log(suma);
```

Wynik:

```text
4400
```

---

# 14. Liczenie elementów spełniających warunek

```javascript
let licznik = 0;

produkty.forEach(produkt => {
    if (produkt.cena > 500) {
        licznik++;
    }
});

console.log(licznik);
```

---

# 15. Wyszukiwanie maksimum

```javascript
let najdrozszy = produkty[0];

for (let i = 1; i < produkty.length; i++) {
    if (produkty[i].cena > najdrozszy.cena) {
        najdrozszy = produkty[i];
    }
}

console.log(najdrozszy.nazwa);
console.log(najdrozszy.cena);
```

---

# 16. JSON + HTML

HTML:

```html
<h1>Lista uczniów</h1>
<div id="lista"></div>
```

JavaScript:

```javascript
const uczniowie = [
    { imie: "Anna", wiek: 18 },
    { imie: "Jan", wiek: 19 },
    { imie: "Kasia", wiek: 18 }
];

let wynik = "";

uczniowie.forEach(uczen => {
    wynik += `<p>${uczen.imie} - ${uczen.wiek} lat</p>`;
});

document.getElementById("lista").innerHTML = wynik;
```

---

# 17. Template literals

```javascript
const imie = "Anna";
const wiek = 18;

const tekst = `${imie} ma ${wiek} lat.`;
```

W HTML:

```javascript
wynik += `
    <div>
        <h3>${produkt.nazwa}</h3>
        <p>Cena: ${produkt.cena} zł</p>
    </div>
`;
```

---

# 18. Plik JSON

Przykładowy `dane.json`:

```json
[
    {
        "imie": "Anna",
        "wiek": 18
    },
    {
        "imie": "Jan",
        "wiek": 19
    },
    {
        "imie": "Kasia",
        "wiek": 18
    }
]
```

---

# 19. fetch()

Dane z pliku JSON można pobrać za pomocą:

```javascript
fetch("dane.json")
    .then(response => response.json())
    .then(dane => {
        console.log(dane);
    });
```

Schemat:

```text
fetch()
   ↓
plik JSON
   ↓
response.json()
   ↓
obiekt JavaScript
   ↓
przetwarzanie danych
```

---

# 20. fetch() + HTML

HTML:

```html
<h1>Lista osób</h1>
<div id="lista"></div>
```

JavaScript:

```javascript
fetch("dane.json")
    .then(response => response.json())
    .then(dane => {

        let wynik = "";

        dane.forEach(osoba => {
            wynik += `
                <p>
                    ${osoba.imie} - ${osoba.wiek} lat
                </p>
            `;
        });

        document.getElementById("lista").innerHTML = wynik;
    });
```

---

# 21. JSON + formularz

HTML:

```html
<input type="text" id="imie">
<input type="number" id="wiek">

<button onclick="zapisz()">Zapisz</button>
```

JavaScript:

```javascript
function zapisz() {

    const osoba = {
        imie: document.getElementById("imie").value,
        wiek: Number(document.getElementById("wiek").value)
    };

    const json = JSON.stringify(osoba);

    console.log(json);
}
```

---

# 22. Obiekty zagnieżdżone

JSON:

```json
{
    "imie": "Anna",
    "adres": {
        "ulica": "Polna 10",
        "miasto": "Warszawa"
    }
}
```

Odczyt:

```javascript
console.log(osoba.imie);
console.log(osoba.adres.miasto);
console.log(osoba.adres.ulica);
```

---

# 23. Tablica jako właściwość

```json
{
    "imie": "Anna",
    "zainteresowania": [
        "programowanie",
        "muzyka",
        "sport"
    ]
}
```

Odczyt:

```javascript
console.log(osoba.zainteresowania[0]);
```

Pętla:

```javascript
osoba.zainteresowania.forEach(zainteresowanie => {
    console.log(zainteresowanie);
});
```

---

# 24. JSON + PHP

PHP może tworzyć JSON:

```php
<?php

$dane = [
    "imie" => "Anna",
    "wiek" => 18
];

$json = json_encode($dane);

echo $json;

?>
```

Najważniejsze funkcje PHP:

```text
json_encode()  → PHP → JSON
json_decode()  → JSON → PHP
```

Przykład:

```php
<?php

$json = '{"imie":"Anna","wiek":18}';

$dane = json_decode($json, true);

echo $dane["imie"];
echo $dane["wiek"];

?>
```

---

# 25. Zadania – INF.03

## Zadanie 1 – podstawy

Utwórz:

```javascript
const osoba = {
    imie: "Adam",
    nazwisko: "Nowak",
    wiek: 20
};
```

Wykonaj:
1. wyświetl imię,
2. wyświetl nazwisko,
3. wyświetl wiek,
4. zamień obiekt na JSON,
5. wyświetl JSON.

---

## Zadanie 2 – JSON.parse()

Dany jest:

```javascript
const tekst = `{
    "imie": "Kasia",
    "wiek": 19,
    "miasto": "Kraków"
}`;
```

Wykonaj:
1. zamianę JSON na obiekt,
2. wyświetlenie imienia,
3. wyświetlenie wieku,
4. wyświetlenie miasta.

---

## Zadanie 3 – uczniowie

```javascript
const tekst = `[
    {"imie":"Adam","punkty":45},
    {"imie":"Ola","punkty":87},
    {"imie":"Kamil","punkty":72},
    {"imie":"Ewa","punkty":91}
]`;
```

Wykonaj:
1. `JSON.parse()`,
2. wyświetlenie wszystkich uczniów,
3. wyświetlenie osób z wynikiem powyżej 70,
4. obliczenie średniej,
5. znalezienie najlepszego wyniku.

---

## Zadanie 4 – produkty

Dane:

```json
[
    {"nazwa":"Monitor","cena":800},
    {"nazwa":"Laptop","cena":3500},
    {"nazwa":"Mysz","cena":100},
    {"nazwa":"Klawiatura","cena":200}
]
```

Wykonaj:
1. wyświetl wszystkie produkty,
2. wyświetl produkty droższe niż 500 zł,
3. policz produkty,
4. oblicz sumę cen,
5. znajdź najdroższy produkt.

---

## Zadanie 5 – samochody

```javascript
const samochody = [
    {
        marka: "Toyota",
        model: "Corolla",
        rok: 2020
    },
    {
        marka: "BMW",
        model: "X3",
        rok: 2022
    },
    {
        marka: "Audi",
        model: "A4",
        rok: 2019
    }
];
```

Wykonaj:
1. wyświetl marki,
2. wyświetl samochody po 2020 roku,
3. policz samochody,
4. znajdź najnowszy samochód.

---

## Zadanie 6 – filtrowanie

Wyświetl produkty w cenie od 200 do 1000 zł.

```javascript
if (produkt.cena >= 200 && produkt.cena <= 1000) {
    console.log(produkt.nazwa);
}
```

---

## Zadanie 7 – JSON i HTML

Utwórz:

```html
<h1>Lista produktów</h1>
<div id="produkty"></div>
```

Następnie wyświetl tablicę produktów w elemencie `div`.

---

## Zadanie 8 – plik JSON

Utwórz `dane.json` i pobierz go za pomocą:

```javascript
fetch("dane.json")
    .then(response => response.json())
    .then(dane => {
        console.log(dane);
    });
```

---

## Zadanie 9 – formularz

Utwórz formularz zawierający:
- imię,
- wiek,
- przycisk.

Po kliknięciu utwórz obiekt i zamień go na JSON za pomocą `JSON.stringify()`.

---

# 26. Zadanie praktyczne INF.03 – Lista produktów

Utwórz aplikację internetową.

Plik `produkty.json`:

```json
[
    {
        "nazwa": "Laptop",
        "cena": 3500,
        "kategoria": "Komputery"
    },
    {
        "nazwa": "Mysz",
        "cena": 100,
        "kategoria": "Akcesoria"
    },
    {
        "nazwa": "Monitor",
        "cena": 900,
        "kategoria": "Monitory"
    }
]
```

Aplikacja powinna posiadać:
- nagłówek,
- przycisk „Pokaż produkty”,
- miejsce na dane.

Po kliknięciu należy pobrać JSON i wyświetlić produkty.

### Przykładowy JavaScript

```javascript
function pobierzProdukty() {

    fetch("produkty.json")
        .then(response => response.json())
        .then(produkty => {

            let wynik = "";

            produkty.forEach(produkt => {

                wynik += `
                    <div>
                        <h3>${produkt.nazwa}</h3>
                        <p>Cena: ${produkt.cena} zł</p>
                        <p>Kategoria: ${produkt.kategoria}</p>
                    </div>
                `;

            });

            document.getElementById("wynik").innerHTML = wynik;
        });
}
```

---

# 27. Zadanie końcowe – Baza uczniów

Utwórz aplikację **„Baza uczniów”**.

Plik `uczniowie.json`:

```json
[
    {
        "imie": "Anna",
        "nazwisko": "Kowalska",
        "klasa": "5A",
        "punkty": 85
    },
    {
        "imie": "Jan",
        "nazwisko": "Nowak",
        "klasa": "5A",
        "punkty": 62
    },
    {
        "imie": "Katarzyna",
        "nazwisko": "Wiśniewska",
        "klasa": "5B",
        "punkty": 91
    },
    {
        "imie": "Piotr",
        "nazwisko": "Wójcik",
        "klasa": "5B",
        "punkty": 74
    }
]
```

Aplikacja powinna:

1. pobrać dane z pliku,
2. wyświetlić wszystkich uczniów,
3. wyświetlić imię i nazwisko,
4. wyświetlić klasę,
5. wyświetlić punkty,
6. wyświetlić uczniów z wynikiem co najmniej 70,
7. obliczyć średnią,
8. znaleźć najwyższy wynik,
9. wyświetlić dane w HTML.

Struktura projektu:

```text
baza_uczniow/
│
├── index.html
├── style.css
├── script.js
└── uczniowie.json
```

---

# 28. Zadanie dodatkowe

Rozbuduj bazę uczniów o:

- przycisk „Pokaż wszystkich”,
- przycisk „Tylko zaliczeni”,
- przycisk „Najlepszy wynik”,
- wyszukiwanie po nazwisku,
- sortowanie po punktach,
- liczbę uczniów,
- średnią punktów.

Sortowanie:

```javascript
uczniowie.sort((a, b) => b.punkty - a.punkty);
```

---

# 29. Checklista przed INF.03

- [ ] Wiem, czym jest JSON.
- [ ] Potrafię utworzyć obiekt JSON.
- [ ] Potrafię utworzyć tablicę JSON.
- [ ] Znam `JSON.parse()`.
- [ ] Znam `JSON.stringify()`.
- [ ] Potrafię odczytać właściwość obiektu.
- [ ] Potrafię pracować z tablicą obiektów.
- [ ] Potrafię użyć `for`.
- [ ] Potrafię użyć `forEach()`.
- [ ] Potrafię zastosować `if`.
- [ ] Potrafię filtrować dane.
- [ ] Potrafię policzyć sumę.
- [ ] Potrafię obliczyć średnią.
- [ ] Potrafię znaleźć maksimum.
- [ ] Znam `fetch()`.
- [ ] Potrafię pobrać plik `.json`.
- [ ] Potrafię wyświetlić JSON w HTML.
- [ ] Potrafię pobrać dane z formularza.
- [ ] Znam podstawy JSON w PHP.

---

# 30. Ściąga egzaminacyjna

```javascript
// JSON → JavaScript
const dane = JSON.parse(tekst);

// JavaScript → JSON
const tekst = JSON.stringify(dane);

// właściwość
dane.imie;

// element tablicy
dane[0];

// liczba elementów
dane.length;

// pętla
dane.forEach(element => {
    console.log(element);
});

// warunek
if (element.wiek >= 18) {
    console.log(element.imie);
}

// pobranie JSON
fetch("dane.json")
    .then(response => response.json())
    .then(dane => {
        console.log(dane);
    });

// wyświetlenie w HTML
document.getElementById("wynik").innerHTML = wynik;
```

---

# 31. Najważniejsze schematy

### JSON → JavaScript

```javascript
const dane = JSON.parse(tekst);
```

### JavaScript → JSON

```javascript
const tekst = JSON.stringify(dane);
```

### Plik JSON

```javascript
fetch("dane.json")
    .then(response => response.json())
    .then(dane => {
        // przetwarzanie
    });
```

### Przetwarzanie tablicy

```javascript
dane.forEach(element => {
    console.log(element.nazwa);
});
```

### Filtrowanie

```javascript
dane.forEach(element => {
    if (element.cena > 500) {
        console.log(element.nazwa);
    }
});
```

### Wyświetlanie HTML

```javascript
let wynik = "";

dane.forEach(element => {
    wynik += `<p>${element.nazwa}</p>`;
});

document.getElementById("wynik").innerHTML = wynik;
```

---

# 32. Podsumowanie

Najważniejszy schemat do zapamiętania:

```text
JSON
 ↓
JSON.parse()
 ↓
obiekt JavaScript
 ↓
pętle / warunki / obliczenia
 ↓
HTML
```

Drugi kierunek:

```text
obiekt JavaScript
 ↓
JSON.stringify()
 ↓
tekst JSON
```

W zadaniach praktycznych INF.03 szczególnie warto ćwiczyć:

```text
HTML + CSS + JavaScript + JSON
```

oraz:

```text
HTML + JavaScript + fetch() + plik JSON
```

i:

```text
PHP + JSON
```
