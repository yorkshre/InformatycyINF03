# JavaScript – operacje na ciągach znaków

## 1. Czym jest ciąg znaków?

W JavaScript ciąg znaków (`String`) służy do przechowywania tekstu. Tekst zapisujemy najczęściej w cudzysłowie `"..."`, apostrofach `'...'` lub backtickach `` `...` ``.

```javascript
let tekst = "Witaj, świecie!";
let imie = 'Anna';
let komunikat = `Cześć ${imie}!`;
```

Ciąg znaków można traktować jako uporządkowaną sekwencję znaków. Każdy znak ma swój indeks, a numerowanie rozpoczyna się od `0`.

---

## 2. Długość tekstu – `length`

Właściwość `length` zwraca liczbę znaków znajdujących się w tekście.

```javascript
let tekst = "Witaj, świecie!";

console.log(tekst.length);
```

Warto pamiętać, że spacje również są znakami i są uwzględniane w `length`.

### Ćwiczenie

Sprawdź długość następujących tekstów:

```javascript
let a = "JavaScript";
let b = "Programowanie";
let c = "Witaj świecie!";
```

---

## 3. Łączenie tekstów – konkatenacja

Łączenie kilku ciągów znaków nazywamy **konkatenacją**. Możemy wykorzystać do tego operator `+`.

```javascript
let imie = "Anna";
let tekst = "Witaj " + imie + "!";

console.log(tekst);
```

Możemy również wykorzystać operator `+=`.

```javascript
let zdanie = "JavaScript";
zdanie += " jest ciekawy.";

console.log(zdanie);
```

### Powtarzanie tekstu

Do wielokrotnego dopisywania tekstu możemy wykorzystać pętlę:

```javascript
const slowo = "JavaScript ";
let zdanie = "";

for (let i = 0; i < 3; i++) {
    zdanie += slowo;
}

console.log(zdanie);
```

Można również użyć metody `repeat()`:

```javascript
console.log("Ha! ".repeat(3));
```

---

## 4. Dostęp do pojedynczych znaków

Do konkretnego znaku możemy odwołać się za pomocą indeksu:

```javascript
let tekst = "JavaScript";

console.log(tekst[0]); // J
console.log(tekst[1]); // a
console.log(tekst[4]); // S
```

Możemy także użyć metody `charAt()`:

```javascript
console.log(tekst.charAt(0)); // J
console.log(tekst.charAt(4)); // S
```

### Indeksowanie od końca

Ostatni znak możemy znaleźć za pomocą:

```javascript
console.log(tekst[tekst.length - 1]);
```

Przykład:

```javascript
let tekst = "JavaScript";

console.log(tekst[tekst.length - 1]); // t
console.log(tekst[tekst.length - 2]); // p
```

---

## 5. Kod znaku – `charCodeAt()`

Metoda `charCodeAt()` zwraca wartość numeryczną kodu znaku.

```javascript
let tekst = "JavaScript";

console.log(tekst.charCodeAt(0)); // kod znaku J
console.log(tekst.charCodeAt(1)); // kod znaku a
```

### Zamiana kodu na znak – `String.fromCharCode()`

Odwrotną operację wykonuje:

```javascript
String.fromCharCode()
```

Przykład:

```javascript
console.log(String.fromCharCode(65)); // A
console.log(String.fromCharCode(97)); // a
```

---

## 6. Wielkie i małe litery

### `toUpperCase()`

Zamienia litery na wielkie:

```javascript
let tekst = "JavaScript";

console.log(tekst.toUpperCase());
// JAVASCRIPT
```

### `toLowerCase()`

Zamienia litery na małe:

```javascript
let tekst = "JavaScript";

console.log(tekst.toLowerCase());
// javascript
```

### Pierwsza litera wielka

Możemy połączyć kilka metod:

```javascript
let tekst = "javascript";

let wynik = tekst.charAt(0).toUpperCase() + tekst.slice(1);

console.log(wynik);
// Javascript
```

---

## 7. Wyszukiwanie tekstu – `indexOf()`

Metoda `indexOf()` zwraca indeks pierwszego wystąpienia szukanego tekstu.

```javascript
let tekst = "Wszędzie dobrze, ale w domu najlepiej.";

console.log(tekst.indexOf("ale"));
```

Jeżeli szukany fragment nie występuje, metoda zwraca `-1`.

```javascript
console.log(tekst.indexOf("kot"));
// -1
```

### `lastIndexOf()`

Metoda `lastIndexOf()` wyszukuje ostatnie wystąpienie danego fragmentu.

```javascript
let tekst = "ala ma kota, a kot ma Alę";

console.log(tekst.lastIndexOf("kot"));
```

---

## 8. Wycinanie tekstu – `substr()`

Metoda `substr(start, długość)` pozwala wyciąć określoną liczbę znaków.

> **Uwaga:** `substr()` jest metodą starszą i nie powinna być stosowana w nowym kodzie. Współcześnie warto korzystać przede wszystkim z `slice()`.

Przykład:

```javascript
let tekst = "JavaScript";

console.log(tekst.substr(0, 4));
// Java
```

---

## 9. Wycinanie tekstu – `substring()`

Metoda:

```javascript
substring(początek, koniec)
```

zwraca fragment tekstu od podanego indeksu początkowego do indeksu końcowego, przy czym indeks końcowy nie jest uwzględniany.

```javascript
let tekst = "JavaScript";

console.log(tekst.substring(0, 4));
// Java
```

Jeżeli nie podamy drugiego argumentu, tekst zostanie pobrany od wskazanego indeksu do końca:

```javascript
console.log(tekst.substring(4));
// Script
```

---

## 10. Wycinanie tekstu – `slice()`

Metoda `slice()` jest bardzo często stosowana do pobierania fragmentów tekstu.

```javascript
let tekst = "JavaScript";

console.log(tekst.slice(0, 4));
// Java

console.log(tekst.slice(4));
// Script
```

Możemy używać również indeksów ujemnych:

```javascript
console.log(tekst.slice(-6));
// Script
```

Indeks `-1` oznacza ostatni znak:

```javascript
console.log(tekst.slice(-1));
// t
```

### `slice()` a `substring()`

| Cecha | `slice()` | `substring()` |
|---|---|---|
| Drugi argument jest końcem zakresu | Tak | Tak |
| Indeksy ujemne | Tak | Nie |
| Zamiana argumentów miejscami | Nie | Tak |
| Współczesne zastosowanie | Bardzo częste | Częste |

---

## 11. Dzielenie tekstu – `split()`

Metoda `split()` dzieli tekst na elementy i zwraca tablicę.

```javascript
let tekst = "Jan,Anna,Piotr";

let osoby = tekst.split(",");

console.log(osoby);
```

Otrzymamy:

```text
["Jan", "Anna", "Piotr"]
```

Możemy następnie przejść po elementach za pomocą pętli:

```javascript
for (let i = 0; i < osoby.length; i++) {
    console.log(osoby[i]);
}
```

### Dzielenie zdania na słowa

```javascript
let zdanie = "JavaScript jest językiem programowania";

let slowa = zdanie.split(" ");

console.log(slowa);
```

---

## 12. Zamiana fragmentu tekstu – `replace()`

Metoda `replace()` pozwala zamienić fragment tekstu na inny.

```javascript
let tekst = "Wszędzie dobrze, ale w domu najlepiej.";

let zmienione = tekst.replace("domu", "szkole");

console.log(zmienione);
```

### Ważne

Domyślnie `replace()` zamienia pierwsze znalezione wystąpienie danego fragmentu.

Jeżeli chcemy zamieniać wiele wystąpień, możemy wykorzystać wyrażenie regularne z flagą `g`:

```javascript
let tekst = "kot kot kot";

console.log(tekst.replace(/kot/g, "pies"));
```

---

## 13. `encodeURI()` – kodowanie adresu URI

Funkcja `encodeURI()` służy do zakodowania całego adresu URI. Znaki takie jak spacje czy niektóre znaki specjalne zostają przedstawione w postaci odpowiedniej dla URI.

```javascript
let tekst = "https://example.com/strona testowa";

let zakodowany = encodeURI(tekst);

console.log(zakodowany);
```

---

## 14. `decodeURI()` – dekodowanie adresu URI

`decodeURI()` wykonuje operację odwrotną:

```javascript
let tekst = "https://example.com/strona%20testowa";

let wynik = decodeURI(tekst);

console.log(wynik);
```

---

# Najważniejsze metody i właściwości

| Metoda / właściwość | Zastosowanie |
|---|---|
| `length` | sprawdza długość tekstu |
| `charAt()` | pobiera znak o podanym indeksie |
| `[]` | pobiera znak o podanym indeksie |
| `charCodeAt()` | zwraca kod znaku |
| `String.fromCharCode()` | tworzy znak na podstawie kodu |
| `toUpperCase()` | zamienia tekst na wielkie litery |
| `toLowerCase()` | zamienia tekst na małe litery |
| `indexOf()` | szuka pierwszego wystąpienia |
| `lastIndexOf()` | szuka ostatniego wystąpienia |
| `substr()` | wycina fragment tekstu – metoda starsza |
| `substring()` | wycina fragment tekstu |
| `slice()` | wycina fragment tekstu |
| `split()` | dzieli tekst na tablicę |
| `replace()` | zamienia fragment tekstu |
| `encodeURI()` | koduje URI |
| `decodeURI()` | dekoduje URI |
| `repeat()` | powtarza tekst określoną liczbę razy |

---

# Ćwiczenia

## Ćwiczenie 1 – długość tekstu

Utwórz zmienną:

```javascript
let tekst = "Programowanie w JavaScript";
```

Wyświetl liczbę znaków tekstu.

---

## Ćwiczenie 2 – pierwszy i ostatni znak

Dla tekstu:

```javascript
let tekst = "Informatyka";
```

Wyświetl:

1. pierwszy znak,
2. drugi znak,
3. ostatni znak,
4. znak znajdujący się przed ostatnim.

---

## Ćwiczenie 3 – wielkie i małe litery

Utwórz program, który dla:

```javascript
let tekst = "JavaScript jest ciekawy";
```

wyświetli:

- cały tekst wielkimi literami,
- cały tekst małymi literami.

---

## Ćwiczenie 4 – wyszukiwanie

Sprawdź, na którym indeksie znajduje się słowo `"JavaScript"`:

```javascript
let tekst = "Uczę się języka JavaScript";
```

Wykorzystaj `indexOf()`.

---

## Ćwiczenie 5 – wycinanie

Dla tekstu:

```javascript
let tekst = "Programowanie";
```

wykorzystaj `slice()`, aby otrzymać:

```text
Program
```

oraz:

```text
wanie
```

---

## Ćwiczenie 6 – dzielenie tekstu

Podziel poniższy tekst na osobne elementy:

```javascript
let tekst = "Anna;Jan;Piotr;Kasia";
```

Użyj `split(";")`.

Następnie wyświetl każdy element w osobnej linii.

---

## Ćwiczenie 7 – zamiana tekstu

Dany jest tekst:

```javascript
let tekst = "Lubię programować w Pythonie.";
```

Za pomocą `replace()` zamień słowo `Pythonie` na `JavaScript`.

---

## Ćwiczenie 8 – pierwsza litera wielka

Napisz program, który zamieni:

```text
javascript jest językiem programowania
```

na:

```text
Javascript jest językiem programowania
```

Wykorzystaj `charAt()`, `toUpperCase()` oraz `slice()`.

---

# Zadanie podsumowujące

Napisz program, który:

1. pobierze od użytkownika imię i nazwisko,
2. usunie niepotrzebne spacje z początku i końca tekstu,
3. zamieni tekst na małe litery,
4. zamieni pierwszą literę imienia na wielką,
5. wyświetli długość całego tekstu,
6. wyświetli pierwszą literę,
7. wyświetli ostatnią literę,
8. sprawdzi, czy w tekście znajduje się znak spacji.

Przykładowe rozwiązanie może wyglądać następująco:

```javascript
let dane = prompt("Podaj imię i nazwisko:");

dane = dane.trim();
dane = dane.toLowerCase();

let wynik = dane.charAt(0).toUpperCase() + dane.slice(1);

console.log("Dane:", wynik);
console.log("Długość:", wynik.length);
console.log("Pierwszy znak:", wynik[0]);
console.log("Ostatni znak:", wynik[wynik.length - 1]);
console.log("Czy zawiera spację:", wynik.includes(" "));
```

---

# Dodatkowe metody warte poznania

Współczesny JavaScript oferuje również inne przydatne metody pracy z tekstem.

## `trim()`

Usuwa białe znaki z początku i końca tekstu:

```javascript
let tekst = "   JavaScript   ";

console.log(tekst.trim());
// JavaScript
```

## `includes()`

Sprawdza, czy tekst zawiera określony fragment:

```javascript
let tekst = "Uczę się JavaScript";

console.log(tekst.includes("JavaScript"));
// true
```

## `startsWith()`

Sprawdza, czy tekst zaczyna się od określonego fragmentu:

```javascript
let tekst = "JavaScript";

console.log(tekst.startsWith("Java"));
// true
```

## `endsWith()`

Sprawdza, czy tekst kończy się określonym fragmentem:

```javascript
let tekst = "JavaScript";

console.log(tekst.endsWith("Script"));
// true
```

---

# Podsumowanie

Operacje na ciągach znaków są jedną z podstawowych umiejętności w JavaScript. Dzięki metodom `length`, `charAt()`, `slice()`, `substring()`, `split()`, `replace()`, `indexOf()`, `toUpperCase()` i `toLowerCase()` możemy wyszukiwać, dzielić, modyfikować oraz analizować tekst.

Najważniejsze jest zrozumienie indeksowania:

```text
J a v a S c r i p t
0 1 2 3 4 5 6 7 8 9
```

Pamiętaj, że indeksowanie rozpoczyna się od `0`.

## Źródło

Materiał opracowano na podstawie lekcji **„JAVASCRIPT Operacje na ciągach znaków”** opublikowanej w serwisie Technik Programista:

https://technikprogramista.pl/kurs/javascript/lekcja/javascript-operacje-na-ciagach-znakow/
