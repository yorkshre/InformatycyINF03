# Operatory w JavaScript

## 1. Wprowadzenie

Operatory w języku JavaScript służą między innymi do:

- wykonywania działań matematycznych,
- przypisywania wartości do zmiennych,
- porównywania wartości,
- tworzenia warunków logicznych,
- łączenia tekstów,
- zwiększania i zmniejszania wartości zmiennych.

Przykład:

```javascript
let a = 10;
let b = 5;

let suma = a + b;

console.log(suma);
```

Wynik:

```text
15
```

---

# 2. Operatory arytmetyczne

Operatory arytmetyczne wykorzystujemy do wykonywania działań matematycznych.

| Operator | Znaczenie | Przykład |
|---|---|---|
| `+` | dodawanie | `a + b` |
| `-` | odejmowanie | `a - b` |
| `*` | mnożenie | `a * b` |
| `/` | dzielenie | `a / b` |
| `%` | reszta z dzielenia | `a % b` |
| `**` | potęgowanie | `a ** b` |
| `++` | zwiększenie o 1 | `a++` |
| `--` | zmniejszenie o 1 | `a--` |

## Przykład

```javascript
let a = 10;
let b = 3;

console.log(a + b);
console.log(a - b);
console.log(a * b);
console.log(a / b);
console.log(a % b);
console.log(a ** b);
```

Wyniki:

```text
13
7
30
3.3333333333333335
1
1000
```

---

# 3. Operator modulo `%`

Operator `%` zwraca **resztę z dzielenia**.

```javascript
console.log(10 % 3);
```

Wynik:

```text
1
```

Ponieważ:

```text
10 = 3 * 3 + 1
```

Operator modulo jest bardzo często wykorzystywany do sprawdzania, czy liczba jest parzysta.

```javascript
let liczba = 8;

console.log(liczba % 2);
```

Wynik:

```text
0
```

Jeżeli:

```javascript
liczba % 2 === 0
```

to liczba jest parzysta.

---

# 4. Potęgowanie `**`

Operator `**` służy do potęgowania.

```javascript
let wynik = 2 ** 3;

console.log(wynik);
```

Wynik:

```text
8
```

Czyli:

```text
2³ = 8
```

Możemy również wykonywać bardziej złożone działania:

```javascript
let wynik = (2 + 3) ** 2;

console.log(wynik);
```

Wynik:

```text
25
```

---

# 5. Inkrementacja `++`

Operator `++` zwiększa wartość zmiennej o 1.

```javascript
let x = 5;

x++;

console.log(x);
```

Wynik:

```text
6
```

Jest to skrócony zapis:

```javascript
x = x + 1;
```

---

# 6. Dekrementacja `--`

Operator `--` zmniejsza wartość zmiennej o 1.

```javascript
let x = 5;

x--;

console.log(x);
```

Wynik:

```text
4
```

Jest to skrócony zapis:

```javascript
x = x - 1;
```

---

# 7. Operator `+` i teksty

Operator `+` może służyć również do łączenia tekstów.

```javascript
let imie = "Anna";
let nazwisko = "Kowalska";

let osoba = imie + " " + nazwisko;

console.log(osoba);
```

Wynik:

```text
Anna Kowalska
```

Takie działanie nazywamy **konkatenacją**, czyli łączeniem napisów.

---

# 8. Łączenie tekstu i liczb

Należy uważać podczas łączenia tekstów i liczb.

```javascript
let a = 5;
let b = 5;

console.log(a + b);
```

Wynik:

```text
10
```

Natomiast:

```javascript
let a = "5";
let b = 5;

console.log(a + b);
```

Wynik:

```text
55
```

Pierwsza wartość jest tekstem, dlatego operator `+` służy tutaj do połączenia tekstów.

Inny przykład:

```javascript
console.log("Wynik: " + 10);
```

Wynik:

```text
Wynik: 10
```

---

# 9. Operatory przypisania

Operator przypisania `=` służy do przypisania wartości zmiennej.

```javascript
let x = 10;
```

Oznacza to:

> do zmiennej `x` przypisz wartość `10`.

## Najważniejsze operatory przypisania

| Operator | Przykład | Odpowiednik |
|---|---|---|
| `=` | `x = 5` | `x = 5` |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |
| `**=` | `x **= 5` | `x = x ** 5` |

## Przykład `+=`

```javascript
let punkty = 10;

punkty += 5;

console.log(punkty);
```

Wynik:

```text
15
```

To samo można zapisać:

```javascript
let punkty = 10;

punkty = punkty + 5;
```

---

# 10. Operator `-=`

```javascript
let liczba = 20;

liczba -= 7;

console.log(liczba);
```

Wynik:

```text
13
```

To samo:

```javascript
liczba = liczba - 7;
```

---

# 11. Operator `*=`

```javascript
let liczba = 5;

liczba *= 4;

console.log(liczba);
```

Wynik:

```text
20
```

---

# 12. Operator `/=`

```javascript
let liczba = 20;

liczba /= 4;

console.log(liczba);
```

Wynik:

```text
5
```

---

# 13. Operatory porównania

Operatory porównania służą do sprawdzania relacji między wartościami.

Wynikiem porównania jest najczęściej:

```javascript
true
```

albo:

```javascript
false
```

## Najważniejsze operatory

| Operator | Znaczenie |
|---|---|
| `==` | równe |
| `===` | identyczne – wartość i typ |
| `!=` | różne |
| `!==` | różne pod względem wartości lub typu |
| `>` | większe |
| `<` | mniejsze |
| `>=` | większe lub równe |
| `<=` | mniejsze lub równe |

---

# 14. `==` a `===`

Jest to bardzo ważna różnica w JavaScript.

## Operator `==`

Porównuje wartości, dopuszczając konwersję typów.

```javascript
console.log(5 == "5");
```

Wynik:

```text
true
```

## Operator `===`

Porównuje zarówno wartość, jak i typ.

```javascript
console.log(5 === "5");
```

Wynik:

```text
false
```

Ponieważ:

```text
5 → number
"5" → string
```

W praktyce warto preferować `===`, gdy chcemy jednoznacznego porównania wartości i typu.

---

# 15. Przykłady operatorów porównania

```javascript
let a = 10;

console.log(a > 5);
console.log(a < 5);
console.log(a >= 10);
console.log(a <= 10);
console.log(a == 10);
console.log(a === 10);
console.log(a != 10);
console.log(a !== 10);
```

Wyniki:

```text
true
false
true
true
true
true
false
false
```

---

# 16. Operatory logiczne

Operatory logiczne pozwalają łączyć kilka warunków.

Najważniejsze:

| Operator | Nazwa | Znaczenie |
|---|---|---|
| `&&` | AND | i |
| `||` | OR | lub |
| `!` | NOT | negacja |

---

# 17. Operator `&&`

Operator `&&` oznacza **AND**, czyli „i”.

Oba warunki muszą być prawdziwe.

```javascript
let wiek = 20;
let maBilet = true;

console.log(wiek >= 18 && maBilet === true);
```

Wynik:

```text
true
```

---

# 18. Operator `||`

Operator `||` oznacza **OR**, czyli „lub”.

Wystarczy, że jeden z warunków jest prawdziwy.

```javascript
let dzien = "sobota";

console.log(dzien === "sobota" || dzien === "niedziela");
```

Wynik:

```text
true
```

---

# 19. Operator `!`

Operator `!` oznacza negację.

Zmienia:

```text
true → false
false → true
```

Przykład:

```javascript
let aktywny = true;

console.log(!aktywny);
```

Wynik:

```text
false
```

---

# 20. Łączenie operatorów

Możemy łączyć wiele operatorów w jednym wyrażeniu.

```javascript
let wiek = 20;
let student = true;

let wynik = wiek >= 18 && student === true;

console.log(wynik);
```

Możemy również stosować nawiasy:

```javascript
let wiek = 16;
let zgoda = true;

let wynik = wiek >= 18 || (wiek < 18 && zgoda === true);

console.log(wynik);
```

---

# 21. Kolejność wykonywania działań

JavaScript stosuje określoną kolejność wykonywania operatorów.

Przykład:

```javascript
let wynik = 2 + 3 * 4;

console.log(wynik);
```

Wynik:

```text
14
```

Najpierw wykonywane jest:

```text
3 * 4
```

a następnie:

```text
2 + 12
```

Dlatego otrzymujemy:

```text
14
```

Jeżeli chcemy zmienić kolejność, używamy nawiasów:

```javascript
let wynik = (2 + 3) * 4;

console.log(wynik);
```

Wynik:

```text
20
```

---

# 22. Operatory w instrukcjach warunkowych

Operatory są bardzo często wykorzystywane razem z `if`.

```javascript
let wiek = 20;

if (wiek >= 18) {
    console.log("Osoba pełnoletnia");
}
```

Możemy wykorzystać operator logiczny:

```javascript
let wiek = 20;
let maDokument = true;

if (wiek >= 18 && maDokument === true) {
    console.log("Możesz wejść.");
}
```

---

# 23. Przykład – system ocen

```javascript
let ocena = 5;

if (ocena >= 5) {
    console.log("Bardzo dobry");
}
```

---

# 24. Przykład – sprawdzanie liczby parzystej

```javascript
let liczba = 12;

if (liczba % 2 === 0) {
    console.log("Liczba jest parzysta");
}
```

---

# 25. Przykład – sprawdzanie przedziału

```javascript
let liczba = 15;

if (liczba >= 10 && liczba <= 20) {
    console.log("Liczba znajduje się w przedziale 10–20.");
}
```

---

# ĆWICZENIA

## Ćwiczenie 1 – podstawowe działania

Utwórz dwie zmienne:

```javascript
let a = 20;
let b = 6;
```

Oblicz i wyświetl:

1. sumę,
2. różnicę,
3. iloczyn,
4. iloraz,
5. resztę z dzielenia.

**Nie korzystaj z kalkulatora.**

---

## Ćwiczenie 2 – potęgowanie

Utwórz zmienną:

```javascript
let liczba = 3;
```

Oblicz:

- `3²`,
- `3³`,
- `3⁴`.

Wykorzystaj operator `**`.

---

## Ćwiczenie 3 – inkrementacja

Utwórz:

```javascript
let punkty = 10;
```

Następnie:

1. zwiększ punkty o 1,
2. zwiększ punkty o 5,
3. wyświetl końcową wartość.

---

## Ćwiczenie 4 – dekrementacja

Utwórz:

```javascript
let zycia = 3;
```

Zmniejsz liczbę żyć o 1.

Następnie wyświetl wynik.

---

## Ćwiczenie 5 – operatory przypisania

Utwórz:

```javascript
let x = 100;
```

Wykonaj kolejno:

```text
+20
-10
*2
/5
```

Wykorzystaj operatory:

```text
+=
-=
*=
/=
```

---

## Ćwiczenie 6 – porównania

Utwórz:

```javascript
let a = 15;
let b = 10;
```

Sprawdź za pomocą operatorów porównania:

1. czy `a` jest większe od `b`,
2. czy `a` jest mniejsze od `b`,
3. czy `a` jest większe lub równe `b`,
4. czy `a` jest równe `b`,
5. czy `a` jest różne od `b`.

---

## Ćwiczenie 7 – `==` i `===`

Sprawdź wyniki:

```javascript
console.log(5 == "5");
console.log(5 === "5");
console.log(10 == "10");
console.log(10 === "10");
```

Następnie wyjaśnij własnymi słowami, dlaczego wyniki są różne.

---

## Ćwiczenie 8 – teksty

Utwórz:

```javascript
let imie = "Jan";
let nazwisko = "Kowalski";
```

Połącz obie zmienne w jeden napis:

```text
Jan Kowalski
```

Wykorzystaj operator `+`.

---

## Ćwiczenie 9 – tekst i liczba

Sprawdź wyniki:

```javascript
console.log(10 + 20);
console.log("10" + 20);
console.log(10 + "20");
console.log("10" + "20");
```

Zapisz swoje obserwacje.

---

## Ćwiczenie 10 – operator `%`

Utwórz zmienną:

```javascript
let liczba = 17;
```

Sprawdź, jaka jest reszta z dzielenia przez:

- `2`,
- `3`,
- `5`.

---

# ZADANIA

## Zadanie 1 – Kalkulator

Napisz program, który posiada dwie zmienne:

```javascript
let a = 25;
let b = 7;
```

Program powinien wyświetlić:

- dodawanie,
- odejmowanie,
- mnożenie,
- dzielenie,
- resztę z dzielenia,
- potęgowanie.

---

## Zadanie 2 – Pole prostokąta

Utwórz zmienne:

```javascript
let bokA = 12;
let bokB = 8;
```

Oblicz:

- pole prostokąta,
- obwód prostokąta.

Wyświetl wyniki w konsoli.

---

## Zadanie 3 – Średnia

Utwórz trzy zmienne zawierające oceny ucznia.

Przykład:

```javascript
let ocena1 = 4;
let ocena2 = 5;
let ocena3 = 3;
```

Oblicz średnią arytmetyczną.

---

## Zadanie 4 – Parzysta czy nieparzysta?

Utwórz zmienną:

```javascript
let liczba = 27;
```

Za pomocą operatora `%` oraz instrukcji `if` sprawdź, czy liczba jest:

- parzysta,
- czy nieparzysta.

---

## Zadanie 5 – Przedział liczbowy

Utwórz zmienną:

```javascript
let liczba = 45;
```

Sprawdź, czy liczba znajduje się w przedziale:

```text
20–50
```

Wykorzystaj operator:

```text
&&
```

---

## Zadanie 6 – Dostęp do systemu

Utwórz:

```javascript
let wiek = 21;
let maKarte = true;
```

Osoba może wejść do systemu, jeśli:

- ma co najmniej 18 lat,
- posiada kartę dostępu.

Wykorzystaj `&&`.

---

## Zadanie 7 – Weekend

Utwórz zmienną:

```javascript
let dzien = "sobota";
```

Sprawdź, czy jest to:

- sobota,
- lub niedziela.

Wykorzystaj operator:

```text
||
```

---

## Zadanie 8 – Logowanie

Utwórz:

```javascript
let login = "admin";
let haslo = "1234";
```

Sprawdź za pomocą operatora `&&`, czy użytkownik podał jednocześnie poprawny login i poprawne hasło.

---

## Zadanie 9 – System punktów

Utwórz:

```javascript
let punkty = 0;
```

Następnie:

1. dodaj 10 punktów,
2. dodaj 20 punktów,
3. odejmij 5 punktów,
4. pomnóż liczbę punktów przez 2.

Wykorzystaj skrócone operatory przypisania.

---

## Zadanie 10 – Sklep internetowy

Utwórz:

```javascript
let cena = 100;
let ilosc = 3;
```

Oblicz wartość zakupów.

Następnie dodaj do ceny dodatkowy koszt dostawy wynoszący 15 zł.

Wyświetl końcową kwotę.

---

# Zadania trudniejsze

## Zadanie 11 – Rabat

Cena produktu wynosi:

```javascript
let cena = 250;
```

Klient otrzymuje rabat 20%.

Oblicz:

1. wysokość rabatu,
2. cenę po rabacie.

---

## Zadanie 12 – Przeliczanie temperatury

Temperatura w stopniach Celsjusza:

```javascript
let celsius = 25;
```

Przelicz ją na stopnie Fahrenheita według wzoru:

```text
F = C * 9 / 5 + 32
```

---

## Zadanie 13 – Czas

Utwórz:

```javascript
let godziny = 2;
let minuty = 35;
```

Oblicz, ile minut łącznie trwa podany czas.

---

## Zadanie 14 – Największa liczba

Utwórz dwie zmienne:

```javascript
let a = 45;
let b = 72;
```

Za pomocą operatorów porównania i `if` wyświetl informację, która liczba jest większa.

---

## Zadanie 15 – Trzy warunki

Utwórz:

```javascript
let wiek = 25;
let maBilet = true;
let jestLista = true;
```

Osoba może wejść na wydarzenie, jeśli:

- ma co najmniej 18 lat,
- ma bilet,
- znajduje się na liście.

Wykorzystaj operator `&&`.

---

# Zadanie projektowe

## Mini kalkulator JavaScript

Utwórz program, który posiada dwie liczby:

```javascript
let a = 20;
let b = 5;
```

Program powinien obliczyć:

- dodawanie,
- odejmowanie,
- mnożenie,
- dzielenie,
- modulo,
- potęgowanie.

Następnie dodaj sprawdzanie:

- czy `a` jest większe od `b`,
- czy `a` jest równe `b`,
- czy `a` jest mniejsze od `b`.

### Wymagania

Program powinien wykorzystywać:

- zmienne `let`,
- operatory arytmetyczne,
- operatory porównania,
- operator `%`,
- operator `**`,
- instrukcję `if`,
- `console.log()`.

**Zadanie wykonaj samodzielnie – bez gotowego rozwiązania.**

---

# Podsumowanie

Najważniejsze operatory JavaScript:

```text
+       dodawanie
-       odejmowanie
*       mnożenie
/       dzielenie
%       reszta z dzielenia
**      potęgowanie
++      zwiększenie o 1
--      zmniejszenie o 1

=       przypisanie
+=      dodanie i przypisanie
-=      odjęcie i przypisanie
*=      pomnożenie i przypisanie
/=      podzielenie i przypisanie
%=      modulo i przypisanie

==      porównanie wartości
===     porównanie wartości i typu
!=      różne
!==     różne pod względem wartości lub typu
>       większe
<       mniejsze
>=      większe lub równe
<=      mniejsze lub równe

&&      AND – i
||      OR – lub
!       NOT – negacja
```

## Najważniejsza zasada

Szczególną uwagę należy zwrócić na różnicę:

```javascript
==
```

oraz:

```javascript
===
```

Operator `===` sprawdza zarówno **wartość, jak i typ danych**, dlatego jest bardzo przydatny przy jednoznacznym porównywaniu wartości.