# Lekcja: Zmienne, typy danych i operatory w JavaScript

## Cel lekcji
Poznasz sposób deklarowania zmiennych, konwersję typów danych (napisy vs liczby), podstawowe operacje arytmetyczne i logiczne oraz przydatne funkcje matematyczne z obiektu `Math`.

---

## 1. Konwersja typów danych i konkatenacja

W JavaScript dodanie liczby do ciągu znaków (tekstu) skutkuje **konkatenacją** – czyli połączeniem obu wartości w jeden tekst. Aby wykonać poprawne działanie matematyczne, ciąg znaków należy przekształcić na liczbę.

* **`parseInt(tekst)`** – konwertuje tekst na liczbę całkowitą (*integer*).
* **`parseFloat(tekst)`** – konwertuje tekst na liczbę zmiennoprzecinkową (*float*).
* **Mnożenie przez 1 (`tekst * 1`)** – prosty trik na wymuszenie konwersji tekstu na liczbę.

### Przykład kodu:

```js
// Łączenie tekstów i konwersja
var a = 10;
var b = '10';

document.write(a + b); // Wynik: 1010 (konkatenacja - połączenie napisów)
document.write('<br>');
document.write(a + parseInt(b)); // Wynik: 20 (poprawne dodawanie po konwersji)
document.write('<br>');

// Konwersja na różne typy liczbowe
var b1 = "1";
var b2 = "1.5";
var b3 = "2";

b1 = parseInt(b1);     // Liczba całkowita: 1
b2 = parseFloat(b2);   // Liczba zmiennoprzecinkowa: 1.5
b3 = b3 * 1;           // Wymuszenie typu liczbowego: 2

var suma = b1 + b2 + b3;
document.write(suma); // Wynik: 4.5
```
2. Operatory arytm
## 4. Obiekt Math – Zaokrąglenia, potęgi i losowanie

Do wykonywania bardziej zaawansowanych obliczeń wykorzystuje się wbudowany obiekt `Math`.

* **`Math.floor(x)`** – zaokrąglenie w dół (do najbliższej liczby całkowitej).
* **`Math.ceil(x)`** – zaokrąglenie w górę.
* **`Math.round(x)`** – zaokrąglenie do najbliższej liczby całkowitej (zgodnie z zasadami matematyki).
* **`~~x`** – dwukrotna negacja bitowa (skraca część ułamkową, dając wynik zaokrąglenia w dół dla liczb dodatnich).
* **`Math.pow(podstawa, wykładnik)`** – potęgowanie.
* **`Math.sqrt(x)`** – pierwiastek kwadratowy.
* **`Math.abs(x)`** – wartość bezwzględna (*moduł*).
* **`Math.random()`** – generuje pseudolosową liczbę z przedziału `[0, 1)`.

### Przykład kodu:

```js
var a = 4;
var b = 3;

// Zaokrąglanie
document.write(Math.floor(a/b)); // 1 (w dół)
document.write(Math.round(a/b)); // 1 (do najbliższej)
document.write(Math.ceil(a/b));  // 2 (w górę)
document.write(~~(a/b));         // 1 (obcięcie ułamka)

// Potęgowanie i pierwiastkowanie
document.write(Math.pow(a, b));  // 4^3 = 64
document.write(Math.sqrt(a));     // sqrt(4) = 2

// Wartość bezwzględna
document.write(Math.abs(-3));    // 3

// Losowanie liczby całkowitej z przedziału 0 - 100
var losowa = Math.random();
losowa *= 100;
document.write(Math.round(losowa));
```
