# Instrukcje warunkowe w JavaScript

## 1. Wprowadzenie

Instrukcje warunkowe są jednym z podstawowych elementów języka
JavaScript.

Pozwalają programowi **podejmować decyzje** w zależności od tego, czy
określony warunek jest prawdziwy, czy fałszywy.

Dzięki instrukcjom warunkowym program może reagować na różne sytuacje.

Przykłady:

-   jeżeli użytkownik ma 18 lat lub więcej, wyświetl informację o
    pełnoletności,
-   jeżeli hasło jest poprawne, pozwól się zalogować,
-   jeżeli liczba jest parzysta, wyświetl odpowiedni komunikat,
-   jeżeli temperatura jest niższa od 0°C, wyświetl informację o mrozie,
-   jeżeli użytkownik poda nieprawidłowe dane, wyświetl komunikat o
    błędzie.

### Przykład decyzji

``` text
                 Czy wiek >= 18?
                       |
              +--------+--------+
              |                 |
             TAK               NIE
              |                 |
       "Pełnoletni"       "Niepełnoletni"
```

W JavaScript taką decyzję zapisujemy za pomocą instrukcji `if`.

------------------------------------------------------------------------

## 2. Czym jest warunek?

Warunek jest wyrażeniem, którego wynikiem jest wartość logiczna:

``` javascript
true
```

lub:

``` javascript
false
```

`true` oznacza **prawdę**, natomiast `false` oznacza **fałsz**.

### Przykład

``` javascript
let wiek = 20;

console.log(wiek >= 18);
```

Wynik:

``` text
true
```

Ponieważ 20 jest większe lub równe 18.

Inny przykład:

``` javascript
let wiek = 15;

console.log(wiek >= 18);
```

Wynik:

``` text
false
```

------------------------------------------------------------------------

## 3. Wartości logiczne `true` i `false`

JavaScript posiada specjalny typ danych:

``` javascript
boolean
```

Może on przyjmować dwie wartości:

``` javascript
true
false
```

Przykład:

``` javascript
let zalogowany = true;
let administrator = false;
```

Możemy wykorzystać je bezpośrednio w instrukcji warunkowej:

``` javascript
let zalogowany = true;

if (zalogowany) {
    console.log("Użytkownik jest zalogowany.");
}
```

------------------------------------------------------------------------

## 4. Instrukcja `if`

Podstawowa instrukcja warunkowa w JavaScript ma postać:

``` javascript
if (warunek) {
    // kod wykonywany,
    // gdy warunek jest prawdziwy
}
```

### Przykład

``` javascript
let wiek = 20;

if (wiek >= 18) {
    console.log("Jesteś pełnoletni.");
}
```

Program sprawdza:

``` javascript
wiek >= 18
```

Jeżeli warunek jest prawdziwy, zostanie wykonany kod znajdujący się
pomiędzy klamrami `{ }`.

------------------------------------------------------------------------

## 5. Nawiasy klamrowe `{ }`

W JavaScript instrukcje należące do `if` umieszczamy w bloku kodu:

``` javascript
{
    // instrukcje
}
```

Przykład:

``` javascript
if (wiek >= 18) {
    console.log("Pełnoletni.");
    console.log("Możesz głosować.");
}
```

Obie instrukcje zostaną wykonane, jeżeli warunek będzie prawdziwy.

------------------------------------------------------------------------

## 6. Instrukcja `if...else`

Jeżeli chcemy określić, co ma się wydarzyć zarówno wtedy, gdy warunek
jest prawdziwy, jak i wtedy, gdy jest fałszywy, wykorzystujemy `else`.

Składnia:

``` javascript
if (warunek) {
    // gdy warunek jest true
} else {
    // gdy warunek jest false
}
```

### Przykład

``` javascript
let wiek = 16;

if (wiek >= 18) {
    console.log("Jesteś pełnoletni.");
} else {
    console.log("Jesteś niepełnoletni.");
}
```

W tym przypadku zostanie wyświetlone:

``` text
Jesteś niepełnoletni.
```

------------------------------------------------------------------------

## 7. Instrukcja `if...else if...else`

Czasami program musi sprawdzić więcej niż dwa przypadki.

Wtedy wykorzystujemy:

``` javascript
if
else if
else
```

### Składnia

``` javascript
if (warunek1) {
    // instrukcje
} else if (warunek2) {
    // instrukcje
} else if (warunek3) {
    // instrukcje
} else {
    // instrukcje
}
```

### Przykład

``` javascript
let temperatura = 25;

if (temperatura < 0) {
    console.log("Mróz.");
} else if (temperatura < 15) {
    console.log("Zimno.");
} else if (temperatura < 25) {
    console.log("Ciepło.");
} else {
    console.log("Gorąco.");
}
```

Program sprawdza warunki kolejno od góry.

------------------------------------------------------------------------

## 8. Kolejność wykonywania warunków

Jest bardzo ważna zasada:

> W konstrukcji `if...else if...else` wykonywany jest pierwszy prawdziwy
> warunek.

Przykład:

``` javascript
let x = 20;

if (x > 10) {
    console.log("A");
} else if (x > 15) {
    console.log("B");
} else {
    console.log("C");
}
```

Wynik:

``` text
A
```

Dlaczego?

Ponieważ:

``` javascript
x > 10
```

jest prawdą.

Program nie przechodzi już do kolejnego `else if`.

------------------------------------------------------------------------

## 9. Operatory porównania

Do tworzenia warunków wykorzystujemy operatory porównania.

  Operator   Znaczenie
  ---------- -----------------------------------------
  `==`       równe
  `===`      identyczne pod względem wartości i typu
  `!=`       różne
  `!==`      różne pod względem wartości lub typu
  `>`        większe
  `<`        mniejsze
  `>=`       większe lub równe
  `<=`       mniejsze lub równe

------------------------------------------------------------------------

## 10. Operator `==`

Operator:

``` javascript
==
```

sprawdza, czy wartości są sobie równe, stosując konwersję typów.

Przykład:

``` javascript
console.log(5 == "5");
```

Wynik:

``` text
true
```

JavaScript dokonuje tutaj konwersji typu.

------------------------------------------------------------------------

## 11. Operator `===`

W nowoczesnym JavaScript zdecydowanie zaleca się częste stosowanie
operatora:

``` javascript
===
```

Sprawdza on zarówno wartość, jak i typ danych.

Przykład:

``` javascript
console.log(5 === 5);
```

Wynik:

``` text
true
```

Natomiast:

``` javascript
console.log(5 === "5");
```

wynik:

``` text
false
```

Pierwsza wartość jest liczbą:

``` javascript
5
```

druga jest tekstem:

``` javascript
"5"
```

### Dobra praktyka

Najczęściej stosuj:

``` javascript
===
```

zamiast:

``` javascript
==
```

------------------------------------------------------------------------

## 12. Operatory `!=` i `!==`

Podobna zasada dotyczy operatorów różności.

``` javascript
!=
```

sprawdza różność z konwersją typów.

``` javascript
!==
```

sprawdza różność wartości lub typów bez konwersji.

Przykład:

``` javascript
console.log(5 != "5");
```

wynik:

``` text
false
```

Natomiast:

``` javascript
console.log(5 !== "5");
```

wynik:

``` text
true
```

------------------------------------------------------------------------

## 13. Operator większe `>`

Przykład:

``` javascript
let wiek = 25;

if (wiek > 18) {
    console.log("Wiek jest większy od 18.");
}
```

Warunek:

``` javascript
wiek > 18
```

oznacza:

> Czy wartość zmiennej `wiek` jest większa niż 18?

------------------------------------------------------------------------

## 14. Operator mniejsze `<`

``` javascript
let temperatura = -5;

if (temperatura < 0) {
    console.log("Temperatura jest ujemna.");
}
```

------------------------------------------------------------------------

## 15. Operatory `>=` i `<=`

Operator:

``` javascript
>=
```

oznacza:

> większe lub równe

Operator:

``` javascript
<=
```

oznacza:

> mniejsze lub równe

Przykład:

``` javascript
let punkty = 50;

if (punkty >= 50) {
    console.log("Zaliczone.");
}
```

Wartość `50` również spełnia warunek.

------------------------------------------------------------------------

## 16. Operator `&&` -- logiczne AND

Operator:

``` javascript
&&
```

oznacza:

> i

Oba warunki muszą być prawdziwe.

### Przykład

``` javascript
let wiek = 25;
let maPrawoJazdy = true;

if (wiek >= 18 && maPrawoJazdy === true) {
    console.log("Możesz prowadzić samochód.");
}
```

Muszą być spełnione oba warunki:

``` text
wiek >= 18
```

oraz:

``` text
maPrawoJazdy === true
```

------------------------------------------------------------------------

## 17. Tabela dla `&&`

  Warunek 1   Warunek 2   Wynik
  ----------- ----------- -------
  false       false       false
  false       true        false
  true        false       false
  true        true        true

Zapamiętaj:

> `&&` wymaga spełnienia wszystkich połączonych warunków.

------------------------------------------------------------------------

## 18. Operator `||` -- logiczne OR

Operator:

``` javascript
||
```

oznacza:

> lub

Wystarczy, że jeden z warunków będzie prawdziwy.

### Przykład

``` javascript
let dzien = "sobota";

if (dzien === "sobota" || dzien === "niedziela") {
    console.log("Weekend!");
}
```

------------------------------------------------------------------------

## 19. Tabela dla `||`

  Warunek 1   Warunek 2   Wynik
  ----------- ----------- -------
  false       false       false
  false       true        true
  true        false       true
  true        true        true

Zapamiętaj:

> `||` jest prawdziwe, jeżeli przynajmniej jeden warunek jest prawdziwy.

------------------------------------------------------------------------

## 20. Operator `!` -- negacja

Operator:

``` javascript
!
```

oznacza:

> nie

Odwraca wartość logiczną.

Przykład:

``` javascript
let zalogowany = false;

if (!zalogowany) {
    console.log("Użytkownik nie jest zalogowany.");
}
```

Ponieważ:

``` javascript
zalogowany
```

ma wartość:

``` javascript
false
```

to:

``` javascript
!zalogowany
```

ma wartość:

``` javascript
true
```

------------------------------------------------------------------------

## 21. Łączenie operatorów logicznych

Możemy tworzyć bardziej złożone warunki.

``` javascript
let wiek = 25;
let student = true;

if (wiek >= 18 && student === true) {
    console.log("Osoba jest pełnoletnim studentem.");
}
```

Możemy również połączyć `&&` oraz `||`.

``` javascript
if (wiek >= 18 && (student === true || pracuje === true)) {
    console.log("Warunek został spełniony.");
}
```

### Ważne

Przy skomplikowanych warunkach warto stosować nawiasy:

``` javascript
()
```

Dzięki temu kod jest łatwiejszy do zrozumienia.

------------------------------------------------------------------------

## 22. Sprawdzanie parzystości

Jednym z klasycznych zastosowań instrukcji warunkowej jest sprawdzanie,
czy liczba jest parzysta.

Wykorzystujemy operator modulo:

``` javascript
%
```

Przykład:

``` javascript
let liczba = 10;

if (liczba % 2 === 0) {
    console.log("Liczba jest parzysta.");
} else {
    console.log("Liczba jest nieparzysta.");
}
```

Jeżeli reszta z dzielenia przez 2 wynosi 0, liczba jest parzysta.

------------------------------------------------------------------------

## 23. Liczba dodatnia, ujemna lub zero

``` javascript
let liczba = -5;

if (liczba > 0) {
    console.log("Liczba dodatnia.");
} else if (liczba < 0) {
    console.log("Liczba ujemna.");
} else {
    console.log("Liczba równa zero.");
}
```

------------------------------------------------------------------------

## 24. Pobieranie danych od użytkownika

W przeglądarce możemy wykorzystać funkcję:

``` javascript
prompt()
```

Przykład:

``` javascript
let wiek = prompt("Podaj swój wiek:");

if (wiek >= 18) {
    console.log("Jesteś pełnoletni.");
} else {
    console.log("Jesteś niepełnoletni.");
}
```

Warto pamiętać, że `prompt()` zwraca tekst.

Dlatego jeżeli chcemy wykonywać działania matematyczne, często należy
zamienić tekst na liczbę.

Możemy wykorzystać:

``` javascript
Number()
```

Przykład:

``` javascript
let wiek = Number(prompt("Podaj swój wiek:"));
```

------------------------------------------------------------------------

## 25. Przykład -- pełnoletność

``` javascript
let wiek = Number(prompt("Podaj wiek:"));

if (wiek >= 18) {
    console.log("Jesteś pełnoletni.");
} else {
    console.log("Jesteś niepełnoletni.");
}
```

------------------------------------------------------------------------

## 26. Przykład -- największa z dwóch liczb

``` javascript
let a = Number(prompt("Podaj pierwszą liczbę:"));
let b = Number(prompt("Podaj drugą liczbę:"));

if (a > b) {
    console.log("Większa liczba:", a);
} else if (b > a) {
    console.log("Większa liczba:", b);
} else {
    console.log("Liczby są równe.");
}
```

------------------------------------------------------------------------

## 27. Przykład -- największa z trzech liczb

``` javascript
let a = Number(prompt("Podaj a:"));
let b = Number(prompt("Podaj b:"));
let c = Number(prompt("Podaj c:"));

if (a >= b && a >= c) {
    console.log("Największa liczba:", a);
} else if (b >= a && b >= c) {
    console.log("Największa liczba:", b);
} else {
    console.log("Największa liczba:", c);
}
```

------------------------------------------------------------------------

## 28. Przykład -- ocena

``` javascript
let ocena = Number(prompt("Podaj ocenę:"));

if (ocena === 1) {
    console.log("Niedostateczny");
} else if (ocena === 2) {
    console.log("Dopuszczający");
} else if (ocena === 3) {
    console.log("Dostateczny");
} else if (ocena === 4) {
    console.log("Dobry");
} else if (ocena === 5) {
    console.log("Bardzo dobry");
} else if (ocena === 6) {
    console.log("Celujący");
} else {
    console.log("Nieprawidłowa ocena.");
}
```

------------------------------------------------------------------------

## 29. Przykład -- przedział liczbowy

Sprawdźmy, czy liczba znajduje się w zakresie od 10 do 20.

``` javascript
let x = Number(prompt("Podaj liczbę:"));

if (x >= 10 && x <= 20) {
    console.log("Liczba znajduje się w przedziale.");
} else {
    console.log("Liczba nie znajduje się w przedziale.");
}
```

------------------------------------------------------------------------

## 30. Przykład -- rok przestępny

Możemy wykorzystać złożony warunek:

``` javascript
let rok = Number(prompt("Podaj rok:"));

if ((rok % 4 === 0 && rok % 100 !== 0) || rok % 400 === 0) {
    console.log("Rok przestępny.");
} else {
    console.log("Rok nie jest przestępny.");
}
```

W tym przykładzie wykorzystujemy jednocześnie:

``` text
&&
||
===
!==
%
```

------------------------------------------------------------------------

## 31. Zagnieżdżone instrukcje `if`

Instrukcja `if` może znajdować się wewnątrz innej instrukcji `if`.

Przykład:

``` javascript
let wiek = 25;
let maPrawoJazdy = true;

if (wiek >= 18) {
    if (maPrawoJazdy === true) {
        console.log("Możesz prowadzić samochód.");
    } else {
        console.log("Nie masz prawa jazdy.");
    }
} else {
    console.log("Jesteś niepełnoletni.");
}
```

Najpierw sprawdzany jest wiek.

Jeżeli osoba jest pełnoletnia, sprawdzane jest prawo jazdy.

------------------------------------------------------------------------

## 32. Uproszczenie zagnieżdżonego `if`

Czasami zagnieżdżony warunek można uprościć.

Zamiast:

``` javascript
if (wiek >= 18) {
    if (maPrawoJazdy === true) {
        console.log("Możesz prowadzić.");
    }
}
```

możemy napisać:

``` javascript
if (wiek >= 18 && maPrawoJazdy === true) {
    console.log("Możesz prowadzić.");
}
```

Druga wersja jest krótsza i często bardziej czytelna.

------------------------------------------------------------------------

## 33. Instrukcja `switch`

JavaScript posiada również instrukcję:

``` javascript
switch
```

Jest ona przydatna, gdy chcemy porównać jedną wartość z wieloma
konkretnymi wartościami.

### Przykład

``` javascript
let dzien = 3;

switch (dzien) {
    case 1:
        console.log("Poniedziałek");
        break;

    case 2:
        console.log("Wtorek");
        break;

    case 3:
        console.log("Środa");
        break;

    case 4:
        console.log("Czwartek");
        break;

    default:
        console.log("Nieprawidłowy numer dnia.");
}
```

Wynik:

``` text
Środa
```

------------------------------------------------------------------------

## 34. Rola `break`

Instrukcja:

``` javascript
break;
```

kończy wykonywanie aktualnego przypadku `case`.

Przykład:

``` javascript
switch (ocena) {
    case 5:
        console.log("Bardzo dobry");
        break;

    case 4:
        console.log("Dobry");
        break;

    default:
        console.log("Inna ocena");
}
```

Bez `break` program może przechodzić do kolejnych przypadków.

------------------------------------------------------------------------

## 35. `switch` czy `if...else`?

### `if...else`

Lepiej sprawdza się w przypadku warunków takich jak:

``` javascript
wiek >= 18
```

``` javascript
temperatura < 0
```

``` javascript
punkty >= 50 && punkty <= 100
```

### `switch`

Jest wygodny, gdy porównujemy jedną zmienną z konkretnymi wartościami:

``` javascript
switch (dzien) {
    case 1:
        // ...
}
```

------------------------------------------------------------------------

## 36. Operator warunkowy `? :`

JavaScript posiada również krótką formę instrukcji warunkowej --
**operator warunkowy**, nazywany często operatorem trójargumentowym.

Składnia:

``` javascript
warunek ? wartość1 : wartość2
```

Przykład:

``` javascript
let wiek = 20;

let komunikat = wiek >= 18
    ? "Pełnoletni"
    : "Niepełnoletni";

console.log(komunikat);
```

Jeżeli warunek jest prawdziwy, zostanie wybrana pierwsza wartość.

Jeżeli jest fałszywy -- druga.

------------------------------------------------------------------------

## 37. Kiedy stosować operator `? :`?

Operator warunkowy jest przydatny, gdy mamy prostą decyzję.

Na przykład:

``` javascript
let wynik = liczba % 2 === 0 ? "Parzysta" : "Nieparzysta";
```

Nie należy jednak tworzyć bardzo skomplikowanych konstrukcji:

``` javascript
let wynik = warunek1 ? warunek2 ? "A" : "B" : warunek3 ? "C" : "D";
```

Taki zapis jest trudniejszy do czytania.

W takim przypadku lepiej zastosować `if...else`.

------------------------------------------------------------------------

## 38. Wartości typu Boolean w warunkach

JavaScript może traktować niektóre wartości jako prawdziwe lub fałszywe.

Wartości traktowane jako **false** w kontekście warunkowym to między
innymi:

``` javascript
false
0
-0
""
null
undefined
NaN
```

Pozostałe wartości są zazwyczaj traktowane jako prawdziwe.

### Przykład

``` javascript
let imie = "";

if (imie) {
    console.log("Podano imię.");
} else {
    console.log("Nie podano imienia.");
}
```

Ponieważ pusty napis `""` jest wartością falsy, zostanie wyświetlony
drugi komunikat.

------------------------------------------------------------------------

## 39. Walidacja danych

Instrukcje warunkowe są bardzo często wykorzystywane do sprawdzania
poprawności danych.

Przykład:

``` javascript
let wiek = Number(prompt("Podaj wiek:"));

if (wiek >= 0 && wiek <= 120) {
    console.log("Wprowadzono poprawny wiek.");
} else {
    console.log("Nieprawidłowy wiek.");
}
```

------------------------------------------------------------------------

## 40. Sprawdzanie pustego pola

Przykład:

``` javascript
let imie = prompt("Podaj imię:");

if (imie === "") {
    console.log("Pole nie może być puste.");
} else {
    console.log("Witaj " + imie);
}
```

Możemy również wykorzystać:

``` javascript
if (!imie) {
    console.log("Nie podano imienia.");
}
```

------------------------------------------------------------------------

## 41. Przykład -- logowanie

``` javascript
let login = prompt("Podaj login:");
let haslo = prompt("Podaj hasło:");

if (login === "admin" && haslo === "1234") {
    console.log("Logowanie poprawne.");
} else {
    console.log("Nieprawidłowy login lub hasło.");
}
```

Zwróć uwagę na operator:

``` javascript
&&
```

Oba warunki muszą być prawdziwe.

------------------------------------------------------------------------

## 42. Przykład -- system biletowy

Załóżmy następujące zasady:

``` text
0–6 lat       → bezpłatny
7–17 lat      → ulgowy
18–64 lat     → normalny
65+           → senior
```

Program:

``` javascript
let wiek = Number(prompt("Podaj wiek:"));

if (wiek >= 0 && wiek <= 6) {
    console.log("Bilet bezpłatny.");
} else if (wiek <= 17) {
    console.log("Bilet ulgowy.");
} else if (wiek <= 64) {
    console.log("Bilet normalny.");
} else {
    console.log("Bilet seniora.");
}
```

------------------------------------------------------------------------

## 43. Najczęstsze błędy

### Błąd 1 -- `=` zamiast `===`

Niepoprawne:

``` javascript
let x = 10;

if (x = 10) {
    console.log("10");
}
```

Do porównania należy stosować:

``` javascript
if (x === 10) {
    console.log("10");
}
```

------------------------------------------------------------------------

### Błąd 2 -- brak nawiasów klamrowych

Chociaż JavaScript pozwala w niektórych sytuacjach pominąć klamry dla
pojedynczej instrukcji:

``` javascript
if (x > 10)
    console.log(x);
```

lepszym nawykiem jest:

``` javascript
if (x > 10) {
    console.log(x);
}
```

------------------------------------------------------------------------

### Błąd 3 -- pomieszanie `&&` i `||`

Przykład:

``` javascript
if (wiek >= 18 && maPrawoJazdy === true)
```

oznacza:

> wiek co najmniej 18 **i** posiadanie prawa jazdy.

Natomiast:

``` javascript
if (wiek >= 18 || maPrawoJazdy === true)
```

oznacza:

> wiek co najmniej 18 **lub** posiadanie prawa jazdy.

To zupełnie inne warunki.

------------------------------------------------------------------------

## 44. Przykład analizy kodu

Przeanalizuj:

``` javascript
let x = 8;

if (x > 10) {
    console.log("A");
} else if (x > 5) {
    console.log("B");
} else {
    console.log("C");
}
```

### Krok 1

Sprawdzamy:

``` javascript
x > 10
```

czyli:

``` text
8 > 10
```

Fałsz.

### Krok 2

Sprawdzamy:

``` javascript
x > 5
```

czyli:

``` text
8 > 5
```

Prawda.

### Wynik

``` text
B
```

------------------------------------------------------------------------

# 45. Ćwiczenia -- poziom podstawowy

## Ćwiczenie 1

Napisz program, który pobiera liczbę i sprawdza, czy jest większa od
100.

------------------------------------------------------------------------

## Ćwiczenie 2

Napisz program sprawdzający, czy podana liczba jest parzysta.

------------------------------------------------------------------------

## Ćwiczenie 3

Napisz program sprawdzający, czy użytkownik jest pełnoletni.

------------------------------------------------------------------------

## Ćwiczenie 4

Pobierz temperaturę i wyświetl:

``` text
poniżej 0 → Mróz
0–15 → Zimno
16–25 → Ciepło
powyżej 25 → Gorąco
```

------------------------------------------------------------------------

## Ćwiczenie 5

Pobierz dwie liczby i wyświetl większą.

Jeżeli są równe, wyświetl:

``` text
Liczby są równe.
```

------------------------------------------------------------------------

# 46. Ćwiczenia -- poziom średni

## Ćwiczenie 6 -- ocena

Pobierz ocenę od 1 do 6 i wyświetl jej opis.

------------------------------------------------------------------------

## Ćwiczenie 7 -- przedział

Sprawdź, czy liczba znajduje się w przedziale:

``` text
[10, 50]
```

------------------------------------------------------------------------

## Ćwiczenie 8 -- największa z trzech

Pobierz trzy liczby i wyświetl największą.

------------------------------------------------------------------------

## Ćwiczenie 9 -- logowanie

Utwórz system sprawdzający:

``` text
login: admin
hasło: 1234
```

Jeżeli oba dane są poprawne, wyświetl:

``` text
Logowanie poprawne.
```

------------------------------------------------------------------------

## Ćwiczenie 10 -- bilet

Napisz program określający rodzaj biletu na podstawie wieku.

------------------------------------------------------------------------

# 47. Ćwiczenia -- poziom zaawansowany

## Ćwiczenie 11 -- trójkąt

Pobierz trzy długości boków:

``` javascript
a
b
c
```

Sprawdź, czy można z nich zbudować trójkąt.

Wykorzystaj warunki:

``` text
a + b > c
a + c > b
b + c > a
```

------------------------------------------------------------------------

## Ćwiczenie 12 -- rodzaj trójkąta

Jeżeli można zbudować trójkąt, określ, czy jest:

-   równoboczny,
-   równoramienny,
-   różnoboczny.

------------------------------------------------------------------------

## Ćwiczenie 13 -- kalkulator

Utwórz prosty kalkulator wykonujący:

``` text
+
-
*
/
```

Program powinien:

1.  pobrać dwie liczby,
2.  pobrać operator,
3.  wykonać odpowiednie działanie,
4.  zabezpieczyć dzielenie przez zero,
5.  poinformować o nieprawidłowym operatorze.

------------------------------------------------------------------------

## Ćwiczenie 14 -- system oceniania

Pobierz liczbę punktów od 0 do 100 i przypisz ocenę:

``` text
0–39    → niedostateczny
40–54   → dopuszczający
55–69   → dostateczny
70–84   → dobry
85–94   → bardzo dobry
95–100  → celujący
```

------------------------------------------------------------------------

# 48. Zadania typu „jaki będzie wynik?"

### Zadanie 1

``` javascript
let x = 15;

if (x > 10) {
    console.log("A");
} else {
    console.log("B");
}
```

**Jaki będzie wynik?**

------------------------------------------------------------------------

### Zadanie 2

``` javascript
let x = 7;

if (x % 2 === 0) {
    console.log("Parzysta");
} else {
    console.log("Nieparzysta");
}
```

------------------------------------------------------------------------

### Zadanie 3

``` javascript
let x = 20;

if (x > 10) {
    console.log("A");
} else if (x > 15) {
    console.log("B");
} else {
    console.log("C");
}
```

------------------------------------------------------------------------

### Zadanie 4

``` javascript
let a = 5;
let b = 10;

if (a > b) {
    console.log(a);
} else {
    console.log(b);
}
```

------------------------------------------------------------------------

# 49. Odpowiedzi

### Zadanie 1

``` text
A
```

### Zadanie 2

``` text
Nieparzysta
```

### Zadanie 3

``` text
A
```

### Zadanie 4

``` text
10
```

------------------------------------------------------------------------

# 50. Zadania -- znajdź błąd

## Zadanie 1

Znajdź błąd:

``` javascript
let wiek = 20;

if (wiek = 18) {
    console.log("Masz 18 lat.");
}
```

### Popraw kod.

------------------------------------------------------------------------

## Zadanie 2

Znajdź błąd:

``` javascript
let x = 10;

if (x > 5 {
    console.log("Większe");
}
```

------------------------------------------------------------------------

## Zadanie 3

Popraw warunek:

``` javascript
if (wiek >= 18 || maPrawoJazdy === true) {
    console.log("Możesz prowadzić.");
}
```

Założenie:

> Osoba musi mieć ukończone 18 lat **i jednocześnie** posiadać prawo
> jazdy.

------------------------------------------------------------------------

# 51. Dobre praktyki w JavaScript

Podczas tworzenia instrukcji warunkowych warto:

1.  Preferować `===` zamiast `==`.
2.  Preferować `!==` zamiast `!=`.
3.  Stosować nawiasy klamrowe `{}`.
4.  Nadawać zmiennym czytelne nazwy.
5.  Unikać bardzo długich warunków.
6.  Przy złożonych warunkach stosować nawiasy.
7.  Sprawdzać przypadki brzegowe.
8.  Walidować dane wprowadzane przez użytkownika.
9.  Unikać niepotrzebnego zagnieżdżania `if`.
10. Pisać kod tak, aby jego działanie było łatwe do odczytania.

------------------------------------------------------------------------

# 52. Najważniejsze konstrukcje

### `if`

``` javascript
if (warunek) {
    // kod
}
```

### `if...else`

``` javascript
if (warunek) {
    // kod
} else {
    // kod
}
```

### `if...else if...else`

``` javascript
if (warunek1) {
    // kod
} else if (warunek2) {
    // kod
} else {
    // kod
}
```

### `switch`

``` javascript
switch (wartosc) {
    case 1:
        // kod
        break;

    case 2:
        // kod
        break;

    default:
        // kod
}
```

### Operator warunkowy

``` javascript
let wynik = warunek ? wartość1 : wartość2;
```

------------------------------------------------------------------------

# 53. Ściąga -- operatory

``` text
===   równe, ta sama wartość i typ
!==   różne
>     większe
<     mniejsze
>=    większe lub równe
<=    mniejsze lub równe

&&    AND – i
||    OR – lub
!     NOT – zaprzeczenie

%     modulo – reszta z dzielenia
```

------------------------------------------------------------------------

# 54. Podsumowanie

Instrukcje warunkowe umożliwiają JavaScriptowi podejmowanie decyzji.

Najważniejsza konstrukcja to:

``` javascript
if (warunek) {
    // instrukcje
}
```

Jeżeli potrzebujemy dwóch możliwości:

``` javascript
if (warunek) {
    // TAK
} else {
    // NIE
}
```

Jeżeli mamy więcej możliwości:

``` javascript
if (warunek1) {
    // ...
} else if (warunek2) {
    // ...
} else {
    // ...
}
```

Do tworzenia warunków wykorzystujemy operatory porównania:

``` javascript
=== !== > < >= <=
```

oraz operatory logiczne:

``` javascript
&& || !
```

W JavaScript warto szczególnie pamiętać o różnicy pomiędzy:

``` javascript
=
```

a:

``` javascript
===
```

`=` służy do przypisywania wartości, natomiast `===` do porównywania.

Opanowanie instrukcji warunkowych jest niezbędne przed rozpoczęciem
nauki kolejnych elementów JavaScript, takich jak:

-   pętle,
-   funkcje,
-   tablice,
-   obiekty,
-   DOM,
-   zdarzenia,
-   formularze,
-   walidacja danych,
-   programowanie aplikacji internetowych.
