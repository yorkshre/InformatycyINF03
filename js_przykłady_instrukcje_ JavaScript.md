# 40 zadań: Instrukcje warunkowe i operatory trójargumentowe (JavaScript)

Ten zestaw zawiera 40 praktycznych zadań z instrukcji warunkowych (`if`, `else`, `switch`), operatorów logicznych (`&&`, `||`, `!`) oraz operatora trójargumentowego (`? :`), przygotowanych specjalnie w języku **JavaScript**.

---

## Część 1: Podstawowe instrukcje warunkowe (`if`, `else`) (Zadania 1–10)

### 1. Liczba dodatnia
Napisz program, który sprawdza, czy podana liczba jest dodatnia. Jeśli tak, wypisz odpowiedni komunikat w konsoli.
```javascript
let liczba = 5;
if (liczba > 0) {
    console.log("Liczba jest dodatnia.");
}
```

### 2. Parzystość
Sprawdź, czy podana przez użytkownika liczba całkowita jest parzysta czy nieparzysta (użyj operatora modulo `%`).
```javascript
let liczba = 4;
if (liczba % 2 === 0) {
    console.log("Liczba jest parzysta.");
} else {
    console.log("Liczba jest nieparzysta.");
}
```

### 3. Pełnoletność
Napisz program, który na podstawie podanego wieku sprawdza, czy osoba jest pełnoletnia (`wiek >= 18`).
```javascript
let wiek = 20;
if (wiek >= 18) {
    console.log("Osoba jest pełnoletnia.");
} else {
    console.log("Osoba jest niepełnoletnia.");
}
```

### 4. Większa od 100
Sprawdź, czy wprowadzona liczba jest większa od 100. Jeśli nie, poinformuj o tym użytkownika.
```javascript
let liczba = 85;
if (liczba > 100) {
    console.log("Liczba jest większa od 100.");
} else {
    console.log("Liczba nie jest większa od 100.");
}
```

### 5. Podzielność przez 5
Napisz program sprawdzający, czy podana liczba dzieli się bez reszty przez 5.
```javascript
let liczba = 25;
if (liczba % 5 === 0) {
    console.log("Liczba dzieli się przez 5.");
} else {
    console.log("Liczba nie dzieli się przez 5.");
}
```

### 6. Większa z dwóch liczb
Zadeklaruj dwie różne liczby i wypisz tę, która jest większa.
```javascript
let a = 12, b = 19;
if (a > b) {
    console.log(`Liczba ${a} jest większa.`);
} else {
    console.log(`Liczba ${b} jest większa.`);
}
```

### 7. Ujemna temperatura
Napisz program, który sprawdza, czy wprowadzona temperatura w skali Celsjusza jest poniżej zera.
```javascript
let temperatura = -3;
if (temperatura < 0) {
    console.log("Temperatura jest poniżej zera (mróz).");
} else {
    console.log("Temperatura wynosi zero lub więcej.");
}
```

### 8. Długość hasła
Sprawdź, czy podany ciąg znaków (hasło) ma co najmniej 8 znaków (`.length`).
```javascript
let haslo = "tajnehaslo123";
if (haslo.length >= 8) {
    console.log("Hasło spełnia wymagania długości.");
} else {
    console.log("Hasło jest za krótkie (minimum 8 znaków).");
}
```

### 9. Równe liczby
Napisz program, który sprawdza, czy dwie podane liczby są sobie równe.
```javascript
let x = 15, y = 15;
if (x === y) {
    console.log("Liczby są równe.");
} else {
    console.log("Liczby są różne.");
}
```

### 10. Porównanie z zerem
Sprawdź, czy podana liczba jest różna od zera (`!==`).
```javascript
let liczba = 7;
if (liczba !== 0) {
    console.log("Liczba jest różna od zera.");
} else {
    console.log("Liczba wynosi zero.");
}
```

---

## Część 2: Instrukcje zagnieżdżone i wielostopniowe (`if-else if`) (Zadania 11–20)

### 11. Ocena szkolna
Przydziel ocenę (1-6) na podstawie punktów procentowych:
* >= 90: 5 (lub celujący)
* >= 75: 4
* >= 50: 3
* < 50: 2
```javascript
let punkty = 82;
if (punkty >= 90) {
    console.log("Ocena: Bardzo dobry (5)");
} else if (punkty >= 75) {
    console.log("Ocena: Dobry (4)");
} else if (punkty >= 50) {
    console.log("Ocena: Dostateczny (3)");
} else {
    console.log("Ocena: Niedostateczny (2)");
}
```

### 12. Kalkulator BMI
Oblicz BMI (`waga / (wzrost * wzrost)` w metrach) i wypisz kategorię (niedowaga < 18.5, norma 18.5-24.9, nadwaga >= 25).
```javascript
let waga = 70; // kg
let wzrost = 1.75; // m
let bmi = waga / (wzrost * wzrost);

if (bmi < 18.5) {
    console.log("Niedowaga");
} else if (bmi >= 18.5 && bmi < 25) {
    console.log("Waga prawidłowa");
} else {
    console.log("Nadwaga lub otyłość");
}
```

### 13. Znak liczby
Sprawdź, czy liczba jest dodatnia, ujemna czy równa zero.
```javascript
let liczba = -5;
if (liczba > 0) {
    console.log("Dodatnia");
} else if (liczba < 0) {
    console.log("Ujemna");
} else {
    console.log("Zero");
}
```

### 14. Pora roku
Na podstawie numeru miesiąca (1-12) określ porę roku (np. 12, 1, 2 -> Zima).
```javascript
let miesiac = 4;
if (miesiac === 12 || miesiac === 1 || miesiac === 2) {
    console.log("Zima");
} else if (miesiac >= 3 && miesiac <= 5) {
    console.log("Wiosna");
} else if (miesiac >= 6 && miesiac <= 8) {
    console.log("Lato");
} else if (miesiac >= 9 && miesiac <= 11) {
    console.log("Jesień");
} else {
    console.log("Niepoprawny numer miesiąca");
}
```

### 15. Najmniejsza z trzech liczb
Znajdź najmniejszą spośród trzech unikalnych zmiennych.
```javascript
let a = 14, b = 7, c = 22;
if (a <= b && a <= c) {
    console.log(`Najmniejsza jest ${a}`);
} else if (b <= a && b <= c) {
    console.log(`Najmniejsza jest ${b}`);
} else {
    console.log(`Najmniejsza jest ${c}`);
}
```

### 16. Warunek trójkąta
Sprawdź, czy z trzech boków `a`, `b`, `c` można zbudować trójkąt (suma dwóch dowolnych boków musi być większa od trzeciego).
```javascript
let a = 5, b = 7, c = 10;
if (a + b > c && a + c > b && b + c > a) {
    console.log("Można zbudować trójkąt.");
} else {
    console.log("Nie można zbudować trójkąta.");
}
```

### 17. Kwalifikacja wiekowa
Podziel wiek na: dziecko (<12), nastolatek (12-18), dorosły (19-64), senior (>=65).
```javascript
let wiek = 30;
if (wiek < 12) {
    console.log("Dziecko");
} else if (wiek <= 18) {
    console.log("Nastolatek");
} else if (wiek <= 64) {
    console.log("Dorosły");
} else {
    console.log("Senior");
}
```

### 18. Limit w bankomacie
Sprawdź, czy żądana wypłata nie przekracza salda oraz dziennego limitu (np. 1000 zł).
```javascript
let saldo = 2500;
let dziennyLimit = 1000;
let wyplata = 600;

if (wyplata > saldo) {
    console.log("Brak środków na koncie.");
} else if (wyplata > dziennyLimit) {
    console.log("Przekroczono dzienny limit wypłat.");
} else {
    console.log("Wypłata zakończona sukcesem.");
}
```

### 19. Prędkość pojazdu w terenie zabudowanym
Ocena prędkości: do 50 km/h (OK), 51-70 (Ostrzeżenie), powyżej 70 (Mandat).
```javascript
let predkosc = 65;
if (predkosc <= 50) {
    console.log("Prędkość przepisowa.");
} else if (predkosc <= 70) {
    console.log("Ostrzeżenie: jedziesz za szybko!");
} else {
    console.log("Wysoki mandat za przekroczenie prędkości!");
}
```

### 20. Poprawność daty (1 kwartał)
Sprawdź, czy podany dzień i miesiąc mieszczą się w poprawnym zakresie dla pierwszego kwartału (styczeń-marzec).
```javascript
let miesiac = 2; // luty
let dzien = 29;

if (miesiac === 1 || miesiac === 3) {
    if (dzien >= 1 && dzien <= 31) {
        console.log("Data poprawna.");
    } else {
        console.log("Niepoprawny dzień.");
    }
} else if (miesiac === 2) {
    if (dzien >= 1 && dzien <= 29) {
        console.log("Data poprawna (lutowa).");
    } else {
        console.log("Niepoprawny dzień w lutym.");
    }
} else {
    console.log("Miesiąc poza pierwszym kwartałem.");
}
```

---

## Część 3: Operatory logiczne (`&&`, `||`, `!`) (Zadania 21–30)

### 21. Przedział liczbowy
Sprawdź, czy liczba mieści się w przedziale domkniętym [10, 20].
```javascript
let x = 15;
if (x >= 10 && x <= 20) {
    console.log("Liczba w przedziale [10, 20].");
} else {
    console.log("Liczba poza przedziałem.");
}
```

### 22. Rok przestępny
Sprawdź, czy rok jest przestępny: podzielny przez 4 i nie przez 100, lub podzielny przez 400.
```javascript
let rok = 2024;
if ((rok % 4 === 0 && rok % 100 !== 0) || (rok % 400 === 0)) {
    console.log("Rok jest przestępny.");
} else {
    console.log("Rok nie jest przestępny.");
}
```

### 23. Samogłoska
Sprawdź, czy zmienna tekstowa (pojedynczy znak) jest samogłoską (`a, e, i, o, u, y`).
```javascript
let znak = "e";
if (znak === "a" || znak === "e" || znak === "i" || znak === "o" || znak === "u" || znak === "y") {
    console.log("To jest samogłoska.");
} else {
    console.log("To nie jest samogłoska.");
}
```

### 24. Dostęp administratora
Sprawdź dostęp: użytkownik musi być zalogowany oraz posiadać rolę `"admin"`.
```javascript
let czyZalogowany = true;
let rola = "admin";

if (czyZalogowany && rola === "admin") {
    console.log("Przyznano dostęp do panelu administratora.");
} else {
    console.log("Brak uprawnień.");
}
```

### 25. Wspólna podzielność
Sprawdź, czy liczba dzieli się jednocześnie przez 3 i przez 5.
```javascript
let liczba = 15;
if (liczba % 3 === 0 && liczba % 5 === 0) {
    console.log("Liczba dzieli się przez 3 i 5.");
} else {
    console.log("Warunek podzielności niespełniony.");
}
```

### 26. Negacja warunku
Wykonaj akcję, jeśli liczba *NIE* jest ujemna (`!`).
```javascript
let liczba = 10;
if (!(liczba < 0)) {
    console.log("Liczba nie jest ujemna.");
}
```

### 27. Godziny otwarcia sklepu
Sklep jest otwarty w dni robocze (poniedziałek-piątek, załóżmy dni 1-5) i godziny od 8 do 16.
```javascript
let dzienTygodnia = 3; // np. środa
let godzina = 10;

if (dzienTygodnia >= 1 && dzienTygodnia <= 5 && godzina >= 8 && godzina < 16) {
    console.log("Sklep jest otwarty.");
} else {
    console.log("Sklep jest zamknięty.");
}
```

### 28. Przynajmniej jeden warunek
Sprawdź, czy spośród trzech zmiennych logicznych przynajmniej jedna ma wartość `true`.
```javascript
let a = false, b = true, c = false;
if (a || b || c) {
    console.log("Przynajmniej jedna zmienna jest prawdziwa.");
} else {
    console.log("Wszystkie są fałszywe.");
}
```

### 29. Zniżka biletowa
Darmowy bilet przysługuje, gdy wiek < 7 lub wiek > 65.
```javascript
let wiek = 70;
if (wiek < 7 || wiek > 65) {
    console.log("Przysługuje darmowy bilet.");
} else {
    console.log("Bilet płatny standardowo.");
}
```

### 30. Złożony warunek mieszany
Sprawdź warunek: `(a > 0 && b > 0) || c === 0`.
```javascript
let a = 5, b = -2, c = 0;
if ((a > 0 && b > 0) || c === 0) {
    console.log("Złożony warunek spełniony.");
} else {
    console.log("Warunek niespełniony.");
}
```

---

## Część 4: Operator trójargumentowy (`? :`) oraz instrukcja `switch` (Zadania 31–40)

### 31. Większa liczba (Ternary)
Za pomocą operatora `? :` przypisz do zmiennej `max` większą z dwóch liczb.
```javascript
let a = 10, b = 25;
let max = (a > b) ? a : b;
console.log("Większa liczba to:", max);
```

### 32. Parzystość w jednej linii
Użyj operatora trójargumentowego do wypisania tekstu "Parzysta" lub "Nieparzysta".
```javascript
let liczba = 7;
let wynik = (liczba % 2 === 0) ? "Parzysta" : "Nieparzysta";
console.log(wynik);
```

### 33. Zaliczenie testu
Przypisz zmiennej tekstowej wartość "Zaliczony" lub "Niezaliczony" w zależności od punktów (`>= 50`).
```javascript
let punkty = 48;
let status = (punkty >= 50) ? "Zaliczony" : "Niezaliczony";
console.log(status);
```

### 34. Cena ze zniżką
Za pomocą operatora trójargumentowego oblicz cenę biletu (jeśli student -> cena / 2, w przeciwnym razie pełna).
```javascript
let czyStudent = true;
let cenaNominalna = 40;
let cenaKoncowa = czyStudent ? (cenaNominalna / 2) : cenaNominalna;
console.log("Cena biletu:", cenaKoncowa);
```

### 35. Prosty kalkulator (`switch`)
Napisz kalkulator obsługujący działania `+`, `-`, `*`, `/` za pomocą instrukcji `switch`.
```javascript
let a = 10, b = 5;
let dzialanie = "+";
let wynik;

switch (dzialanie) {
    case "+":
        wynik = a + b;
        break;
    case "-":
        wynik = a - b;
        break;
    case "*":
        wynik = a * b;
        break;
    case "/":
        wynik = b !== 0 ? a / b : "Nie dzielimy przez zero";
        break;
    default:
        wynik = "Nieznane działanie";
}
console.log("Wynik:", wynik);
```

### 36. Dni tygodnia (`switch`)
Zamień numer dnia tygodnia (1-7) na jego słowną nazwę (1 -> Poniedziałek).
```javascript
let dzienNum = 3;
switch (dzienNum) {
    case 1: console.log("Poniedziałek"); break;
    case 2: console.log("Wtorek"); break;
    case 3: console.log("Środa"); break;
    case 4: console.log("Czwartek"); break;
    case 5: console.log("Piątek"); break;
    case 6: console.log("Sobota"); break;
    case 7: console.log("Niedziela"); break;
    default: console.log("Nie ma takiego dnia tygodnia.");
}
```

### 37. Nazwa miesiąca (`switch`)
Napisz program wypisujący nazwę miesiąca na podstawie liczby od 1 do 12.
```javascript
let miesiac = 5;
switch (miesiac) {
    case 1: console.log("Styczeń"); break;
    case 2: console.log("Luty"); break;
    case 3: console.log("Marzec"); break;
    case 4: console.log("Kwiecień"); break;
    case 5: console.log("Maj"); break;
    case 6: console.log("Czerwiec"); break;
    case 7: console.log("Lipiec"); break;
    case 8: console.log("Sierpień"); break;
    case 9: console.log("Wrzesień"); break;
    case 10: console.log("Październik"); break;
    case 11: console.log("Listopad"); break;
    case 12: console.log("Grudzień"); break;
    default: console.log("Błędny miesiąc.");
}
```

### 38. Menu wyboru gry (`switch`)
Stwórz tekstowe menu (1. Nowa gra, 2. Wczytaj, 3. Wyjście) obsługiwane przez `switch`.
```javascript
let wybor = 1;
switch (wybor) {
    case 1:
        console.log("Rozpoczynanie nowej gry...");
        break;
    case 2:
        console.log("Wczytywanie zapisu gry...");
        break;
    case 3:
        console.log("Zamykanie programu...");
        break;
    default:
        console.log("Niepoprawny wybór w menu.");
}
```

### 39. Zagnieżdżony ternary
Użyj zagnieżdżonego operatora trójargumentowego do określenia znaku liczby (zwróć `1` dla dodatniej, `-1` dla ujemnej, `0` dla zera).
```javascript
let liczba = -4;
let znak = (liczba > 0) ? 1 : ((liczba < 0) ? -1 : 0);
console.log("Znak liczby:", znak);
```

### 40. Ocena literowa (`switch`)
Zamień ocenę literową (`A`, `B`, `C`, `D`, `F`) na opis słowny (np. A -> Celujący / Bardzo dobry).
```javascript
let ocenaLitera = "B";
switch (ocenaLitera) {
    case "A": console.log("Celujący"); break;
    case "B": console.log("Bardzo dobry"); break;
    case "C": console.log("Dobry"); break;
    case "D": console.log("Dostateczny"); break;
    case "F": console.log("Niedostateczny"); break;
    default: console.log("Nieznana ocena.");
}
```

---
*Powodzenia w kodowaniu! Możesz skopiować te przykłady do pliku `.js` i uruchamiać je np. w Node.js lub w konsoli przeglądarki.*
