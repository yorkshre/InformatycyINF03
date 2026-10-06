# Pętla `for` w JavaScript

## 1. Czym jest pętla?

Pętla pozwala wielokrotnie wykonywać ten sam fragment kodu.

Zamiast pisać:

```javascript
console.log(1);
console.log(2);
console.log(3);
console.log(4);
console.log(5);
```

możemy użyć pętli:

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

Pętla `for` jest szczególnie przydatna wtedy, gdy wiemy, **ile razy chcemy wykonać określone instrukcje**.

---

# 2. Składnia pętli `for`

Podstawowa składnia:

```javascript
for (inicjalizacja; warunek; zmiana) {
    // instrukcje wykonywane w pętli
}
```

Przykład:

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

Pętla wykona się dla wartości:

```text
0
1
2
3
4
```

---

# 3. Elementy pętli `for`

Pętla składa się z trzech podstawowych części:

```javascript
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```

### 1. Inicjalizacja

```javascript
let i = 0
```

Tworzymy zmienną sterującą pętlą.

Najczęściej używa się nazw:

```javascript
i
j
k
```

---

### 2. Warunek

```javascript
i < 10
```

Określa, kiedy pętla ma być wykonywana.

Dopóki warunek jest prawdziwy (`true`), instrukcje wewnątrz pętli są wykonywane.

---

### 3. Zmiana wartości

```javascript
i++
```

Po każdym wykonaniu pętli zmienna `i` zwiększa swoją wartość o `1`.

Jest to skrócony zapis:

```javascript
i = i + 1;
```

---

# 4. Prosty przykład

```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

Wynik:

```text
1
2
3
4
5
6
7
8
9
10
```

---

# 5. Odliczanie w dół

Pętla może również zmniejszać wartość zmiennej.

```javascript
for (let i = 10; i >= 1; i--) {
    console.log(i);
}
```

Wynik:

```text
10
9
8
7
6
5
4
3
2
1
```

Operator:

```javascript
i--
```

oznacza:

```javascript
i = i - 1;
```

---

# 6. Zwiększanie wartości o więcej niż 1

Nie musimy zwiększać zmiennej tylko o `1`.

Możemy użyć:

```javascript
i += 2;
```

Przykład:

```javascript
for (let i = 0; i <= 10; i += 2) {
    console.log(i);
}
```

Wynik:

```text
0
2
4
6
8
10
```

Możemy również użyć:

```javascript
i += 5;
```

Przykład:

```javascript
for (let i = 0; i <= 30; i += 5) {
    console.log(i);
}
```

Wynik:

```text
0
5
10
15
20
25
30
```

---

# 7. Pętla od 1 do 100

```javascript
for (let i = 1; i <= 100; i++) {
    console.log(i);
}
```

Pętla wypisze wszystkie liczby od `1` do `100`.

---

# 8. Liczby parzyste

Do sprawdzania, czy liczba jest parzysta, możemy wykorzystać operator `%`.

Przykład:

```javascript
for (let i = 1; i <= 20; i++) {
    if (i % 2 === 0) {
        console.log(i);
    }
}
```

Operator `%` zwraca resztę z dzielenia.

Przykład:

```javascript
10 % 2
```

wynosi:

```text
0
```

Natomiast:

```javascript
11 % 2
```

wynosi:

```text
1
```

---

# 9. Liczby nieparzyste

```javascript
for (let i = 1; i <= 20; i++) {
    if (i % 2 !== 0) {
        console.log(i);
    }
}
```

---

# 10. Suma liczb

Pętla może być wykorzystywana do obliczeń.

Przykład:

```javascript
let suma = 0;

for (let i = 1; i <= 10; i++) {
    suma = suma + i;
}

console.log(suma);
```

Zmiennej `suma` używamy do przechowywania aktualnego wyniku.

---

# 11. Skrócony zapis sumowania

Zamiast:

```javascript
suma = suma + i;
```

możemy zapisać:

```javascript
suma += i;
```

Przykład:

```javascript
let suma = 0;

for (let i = 1; i <= 10; i++) {
    suma += i;
}

console.log(suma);
```

---

# 12. Tablica i pętla `for`

Pętla `for` może służyć do przechodzenia po elementach tablicy.

Przykład:

```javascript
let owoce = ["jabłko", "banan", "gruszka", "śliwka"];

for (let i = 0; i < owoce.length; i++) {
    console.log(owoce[i]);
}
```

Wynik:

```text
jabłko
banan
gruszka
śliwka
```

Indeksy tablicy zaczynają się od `0`.

Dla tablicy:

```javascript
let owoce = ["jabłko", "banan", "gruszka"];
```

mamy:

```text
indeks 0 → jabłko
indeks 1 → banan
indeks 2 → gruszka
```

---

# 13. Właściwość `length`

Właściwość:

```javascript
.length
```

zwraca liczbę elementów tablicy.

Przykład:

```javascript
let liczby = [10, 20, 30, 40, 50];

console.log(liczby.length);
```

Wynik:

```text
5
```

Dlatego często stosujemy:

```javascript
for (let i = 0; i < liczby.length; i++) {
    console.log(liczby[i]);
}
```

---

# 14. Pętla `for` i instrukcja `if`

Pętlę można łączyć z instrukcją warunkową.

Przykład:

```javascript
for (let i = 1; i <= 20; i++) {
    if (i % 2 === 0) {
        console.log(i + " jest parzysta");
    }
}
```

Pętla przechodzi przez wszystkie liczby, a `if` sprawdza ich właściwość.

---

# 15. Pętla z `break`

Instrukcja:

```javascript
break;
```

natychmiast kończy działanie pętli.

Przykład:

```javascript
for (let i = 1; i <= 10; i++) {

    if (i === 6) {
        break;
    }

    console.log(i);
}
```

Wynik:

```text
1
2
3
4
5
```

Po osiągnięciu wartości `6` pętla zostaje przerwana.

---

# 16. Pętla z `continue`

Instrukcja:

```javascript
continue;
```

pomija aktualne wykonanie pętli i przechodzi do kolejnego obrotu pętli.

Przykład:

```javascript
for (let i = 1; i <= 10; i++) {

    if (i === 5) {
        continue;
    }

    console.log(i);
}
```

Wynik:

```text
1
2
3
4
6
7
8
9
10
```

Liczba `5` została pominięta.

---

# 17. Pętla z tekstem

Pętli `for` można używać również do wykonywania operacji na tekstach.

Przykład:

```javascript
let tekst = "JavaScript";

for (let i = 0; i < tekst.length; i++) {
    console.log(tekst[i]);
}
```

Program wypisze kolejne znaki tekstu.

---

# 18. Zagnieżdżona pętla `for`

Pętla może znajdować się wewnątrz innej pętli.

Przykład:

```javascript
for (let i = 1; i <= 3; i++) {

    for (let j = 1; j <= 3; j++) {
        console.log(i, j);
    }

}
```

Jest to przykład **zagnieżdżonej pętli**.

Zagnieżdżone pętle często wykorzystuje się np. do:

- tworzenia tablic dwuwymiarowych,
- tworzenia tabel,
- generowania wzorów,
- wykonywania obliczeń matematycznych,
- pracy z macierzami.

---

# 19. Generowanie prostych wzorów

Pętla może być wykorzystana do tworzenia wzorów tekstowych.

Przykład:

```javascript
for (let i = 1; i <= 5; i++) {
    console.log("*".repeat(i));
}
```

Wynik:

```text
*
**
***
****
*****
```

---

# 20. Najczęstsze błędy

## Błąd 1 – brak zmiany zmiennej

Niebezpieczny przykład:

```javascript
for (let i = 1; i <= 10;) {
    console.log(i);
}
```

W tym przypadku wartość `i` się nie zmienia.

Może to doprowadzić do **nieskończonej pętli**.

---

## Błąd 2 – nieprawidłowy warunek

Przykład:

```javascript
for (let i = 1; i >= 10; i++) {
    console.log(i);
}
```

Warunek jest fałszywy już na początku, więc pętla nie wykona się ani razu.

---

## Błąd 3 – pomylenie `<` i `<=`

Porównaj:

```javascript
for (let i = 1; i < 5; i++) {
    console.log(i);
}
```

oraz:

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

Pierwsza pętla wypisze:

```text
1
2
3
4
```

Druga:

```text
1
2
3
4
5
```

---

# 21. Schemat działania pętli

Dla:

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

kolejne etapy są następujące:

```text
1. Utworzenie i = 1
2. Sprawdzenie i <= 5
3. Wykonanie instrukcji
4. i++
5. Ponowne sprawdzenie warunku
6. Wykonanie instrukcji
7. i++
8. ...
9. Gdy warunek jest fałszywy → koniec pętli
```

---

# ĆWICZENIA

## Ćwiczenie 1 – liczby od 1 do 10

Napisz program wykorzystujący pętlę `for`, który wypisze liczby od `1` do `10`.

---

## Ćwiczenie 2 – liczby od 10 do 1

Napisz program wypisujący liczby od `10` do `1`.

---

## Ćwiczenie 3 – liczby parzyste

Napisz program wypisujący wszystkie liczby parzyste od `1` do `50`.

---

## Ćwiczenie 4 – liczby nieparzyste

Napisz program wypisujący wszystkie liczby nieparzyste od `1` do `50`.

---

## Ćwiczenie 5 – wielokrotności liczby

Napisz program wypisujący wszystkie wielokrotności liczby `5` od `5` do `100`.

---

## Ćwiczenie 6 – suma liczb

Oblicz sumę wszystkich liczb od `1` do `100`.

Wykorzystaj zmienną pomocniczą.

---

## Ćwiczenie 7 – suma liczb parzystych

Oblicz sumę wszystkich liczb parzystych od `1` do `100`.

---

## Ćwiczenie 8 – tabliczka mnożenia

Napisz program wyświetlający tabliczkę mnożenia dla liczby podanej przez użytkownika.

Przykład dla liczby `7`:

```text
7 × 1 = ...
7 × 2 = ...
7 × 3 = ...
...
7 × 10 = ...
```

---

## Ćwiczenie 9 – tablica

Dana jest tablica:

```javascript
let liczby = [12, 5, 8, 21, 4, 17, 9];
```

Za pomocą pętli `for` wypisz wszystkie elementy tablicy.

---

## Ćwiczenie 10 – największa liczba

Dana jest tablica:

```javascript
let liczby = [12, 45, 7, 89, 23, 56, 3];
```

Za pomocą pętli `for` znajdź największą liczbę.

---

# ZADANIA DO SAMODZIELNEGO WYKONANIA

## Zadanie 1 – suma

Napisz program, który obliczy sumę liczb od `1` do `n`.

Wartość `n` pobierz od użytkownika.

---

## Zadanie 2 – średnia

Napisz program, który dla podanej tablicy liczb obliczy średnią arytmetyczną.

```javascript
let liczby = [4, 7, 10, 15, 20];
```

---

## Zadanie 3 – zliczanie elementów

Dla podanej tablicy policz, ile znajduje się w niej liczb parzystych.

```javascript
let liczby = [2, 7, 8, 11, 14, 17, 20, 25];
```

---

## Zadanie 4 – wyszukiwanie

Napisz program, który sprawdzi, czy podana przez użytkownika liczba znajduje się w tablicy.

```javascript
let liczby = [4, 8, 15, 16, 23, 42];
```

---

## Zadanie 5 – najmniejsza liczba

Znajdź najmniejszą wartość w tablicy:

```javascript
let liczby = [34, 12, 87, 5, 23, 9, 45];
```

---

## Zadanie 6 – suma większych liczb

Oblicz sumę tych elementów tablicy, które są większe od `10`.

```javascript
let liczby = [4, 12, 7, 25, 18, 3, 31, 9];
```

---

## Zadanie 7 – odwracanie tablicy

Wyświetl elementy tablicy w odwrotnej kolejności.

```javascript
let liczby = [10, 20, 30, 40, 50];
```

Nie korzystaj z metody `reverse()`.

---

## Zadanie 8 – liczba wystąpień

Policz, ile razy dana liczba występuje w tablicy.

```javascript
let liczby = [2, 5, 2, 8, 2, 10, 5, 2];
```

---

## Zadanie 9 – filtrowanie liczb

Wyświetl tylko te liczby z tablicy, które są większe od `20`.

```javascript
let liczby = [5, 32, 18, 45, 7, 26, 51, 13];
```

---

## Zadanie 10 – znaki tekstu

Dla tekstu:

```javascript
let tekst = "Programowanie";
```

wyświetl każdy znak w osobnej linii.

---

## Zadanie 11 – zliczanie samogłosek

Napisz program, który policzy liczbę samogłosek w podanym tekście.

Przykład:

```javascript
let tekst = "JavaScript";
```

---

## Zadanie 12 – odwrócony tekst

Napisz program, który za pomocą pętli `for` utworzy tekst zapisany od końca.

Przykład:

```text
JavaScript
```

powinien zostać przekształcony na:

```text
tpircSavaJ
```

Nie korzystaj z `reverse()`.

---

# ZADANIA Z ZAGNIEŻDŻONĄ PĘTLĄ

## Zadanie 13 – prostokąt z gwiazdek

Za pomocą dwóch pętli `for` utwórz prostokąt:

```text
*****
*****
*****
*****
```

---

## Zadanie 14 – trójkąt

Za pomocą zagnieżdżonej pętli utwórz:

```text
*
**
***
****
*****
```

---

## Zadanie 15 – tabliczka mnożenia

Za pomocą dwóch zagnieżdżonych pętli `for` wygeneruj pełną tabliczkę mnożenia od `1` do `10`.

---

## Zadanie 16 – współrzędne

Używając dwóch pętli `for`, wypisz wszystkie pary:

```text
(1,1)
(1,2)
(1,3)
...
(3,3)
```

---

# ZADANIA TRUDNIEJSZE

## Zadanie 17 – liczby pierwsze

Napisz program, który znajdzie i wyświetli wszystkie liczby pierwsze z zakresu od `2` do `100`.

---

## Zadanie 18 – silnia

Napisz program obliczający silnię liczby `n`.

Przykład:

```text
5! = 120
```

---

## Zadanie 19 – potęga

Napisz program obliczający wartość:

```text
a^n
```

bez korzystania z `Math.pow()` ani operatora `**`.

---

## Zadanie 20 – analiza tablicy

Dla tablicy:

```javascript
let liczby = [12, 5, 8, 21, 34, 7, 18, 3, 25, 10];
```

wyznacz:

- największą liczbę,
- najmniejszą liczbę,
- sumę wszystkich liczb,
- średnią,
- liczbę liczb parzystych,
- liczbę liczb nieparzystych.

Do rozwiązania wykorzystaj pętlę `for`.

---

# Podsumowanie

Pętla `for` jest jednym z podstawowych elementów języka JavaScript.

Najważniejszy schemat:

```javascript
for (let i = 0; i < liczba; i++) {
    // kod wykonywany wielokrotnie
}
```

Należy pamiętać o trzech elementach:

1. **Inicjalizacja** – od jakiej wartości zaczynamy.
2. **Warunek** – jak długo pętla ma działać.
3. **Zmiana** – jak zmienia się zmienna sterująca.

Przykład:

```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

Pętla `for` może być łączona między innymi z:

- `if`,
- `else`,
- `break`,
- `continue`,
- tablicami,
- napisami,
- zagnieżdżonymi pętlami,
- operacjami matematycznymi.

**Najważniejsze zadanie podczas nauki:** nauczyć się samodzielnie określać wartość początkową, warunek zakończenia oraz sposób zmiany zmiennej sterującej.