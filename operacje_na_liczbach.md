#Lekcja: Operacje na liczbach
---

##1. Wykorzystanie zmiennych w skryptach

Przedstawię kilka przykładów wykorzystania zmiennych w sktypcie i operacji na nich.


```js
document.write(10);
document.write('<br>');
var a = 10;
document.write(a);
document.write('<br>');
var b = '10';
var c = a+b;
document.write(c);
document.write('<br>');
var c = a+parseInt(b);
document.write(c);
document.write('<br>');
```
W pierwszej linijce wypisujemy liczbę 10. Kolejna to wypisanie htmlowego znacznika przejścia do nowej linii.

Linijka trzecia to deklaracja zmiennej o nazwie a i przypisanie jej wartości 10.
6 linia wydaje się podobna, jednak znaczniki ” sprawiają, że nie mamy w tym momencie do czynienia z liczbową wartością zmiennej b, ale z wartością tekstową.

Próbując dodać do siebie wartości a oraz b w kolejnej linii nie dostaniemy oczekiwanego wyniku 20, ale 1010, gdyż + połączył nam liczbę 10 z ciągiem znaków o tej samej wartości - `konkatenacja` – łączenie ze sobą wyrażeń

W linii 10 wykorzystujemy funkcję `parseInt` języka javascript, która zamienia nam ciąg znaków w liczbę całkowitą (int – integer – liczba całkowita).

Rezultat działania skryptu:
```text
10
10 
1010 
20
```
```js
var b1 = "1";
var b2 = "1.5";
var b3 = "2";
b1 = parseInt(b1);
b2 = parseFloat(b2);
b3 = b3 * 1;
var suma = b1 + b2 + b3;
document.write(suma)
```
Deklaracja trzech zmiennych z przypisaniem im wartości tekstowych. Funkcję `parseInt` już znamy. parseFloat zamienia nam wartość tekstową w liczbę zmiennoprzecinkową `(float)`. Również pomnożenie (*) wartości przez 1 sprawiło, że mamy do czynienia z liczbą. Suma trzech wartości początkowo tekstowych daje nam zmiennoprzecinkowy wynik:`45`
```js
var a = 4;
var b = 3;
 
document.write(a+b);
document.write('<br>');
document.write(a-b);
document.write('<br>');
document.write(a*b);
document.write('<br>');
document.write(a/b);
document.write('<br>');
document.write(a%b);
document.write('<br>');
```
Kolejne operacje sumy, różnicy, iloczynu i ilorazu na zmiennych całkowitoliczbowych a i b. Ostatnie z przeprowadzonych działań to reszta z dzielenia (%, modulo). Reszta z dzielenia całkowitego 4/3 wynosi 1.
Wynik działania programu
```text
7
1
12
1.3333333333333333
1
```

```js
var a = 4;
 
document.write(a++);
document.write('<br>');
document.write(++a);
document.write('<br>');
document.write(a);
document.write('<br>');
```
Kolejny przykład jest zastosowaniem `inkrementacji (++)` – zwiększania wartości o 1. Pierwszy zapis (a++) powoduje wypisanie pierwotnej wartości a, a następnie zwiększenie jej o 1 (wypisane 4, zwiększenie do 5). Następnie ++a wykonuje te czynności w kolejności odwrotnej (najpierw zwiększenie wartości a do 6, następnie wypisanie jej na ekran).
```text
4
6
6
```
Kolejny przykład poniżej. 
Pierwsza linijka to stadardowe dzielenie wartości a przez b. W trzeciej mamy podłogę `(floor)` z dzielenia, czyli zaokrąglenie wyniku do najbliższej całkowitej wartości w dół. Kolejne zaokrąglenie jest do bliższej wartości całkowitej – w dół lub w górę. `Ceil` zaokrągla nam do najbliższej całkowitej wartości w górę. W ramach ciekawostki macie również dwukrotne użycie tyldy w celu zaokrąglenia liczby. ~ jest operatorem bitowym i zwraca nam dla liczby n wartość -(n+1).

```js
var a = 4;
var b = 3;
 
document.write(a/b);
document.write('<br>');
document.write(Math.floor(a/b));
document.write('<br>');
document.write(Math.round(a/b));
document.write('<br>');
document.write(Math.ceil(a/b));
 
document.write('<br><br>');
document.write(~~(a/b));
```
Wynik działania programu:
```text
1.3333333333333333
1
1
2 

1
```

2. Generowanie liczb losowych (`Math.random`)

Funkcja `Math.random()` zwraca pseudolosową liczbę zmiennoprzecinkową z przedziału **$[0, 1)$** (włącznie z 0, ale bez 1).

### Przykład kodu:
```javascript
var a = Math.random();
document.write(a);
document.write('<br>');

a *= 100;
document.write(Math.round(a));
```

### Wyjaśnienie:
* `Math.random()` generuje ułamek losowy (np. `0.4582...`).
* `a *= 100` przesuwa przecinek o dwa miejsca w prawo, dając wartość z przedziału $[0, 100)$.
* `Math.round(a)` zaokrągla wynik do najbliższej liczby całkowitej.

### Przydatne funkcje zaokrąglające:
* `Math.floor(x)` — zaokrągla **w dół** (odrzuca część ułamkową).
* `Math.ceil(x)` — zaokrągla **w górę**.
* `Math.round(x)` — zaokrągla do **najbliższej** liczby całkowitej.

> **Wzór na losową liczbę całkowitą z przedziału $\langle	ext{min}, 	ext{max}
angle$:**
> ```javascript
> var min = 1, max = 10;
> var losowa = Math.floor(Math.random() * (max - min + 1)) + min;
> ```

---

## 2. Typy danych i operator `typeof`

JavaScript jest językiem **dynamicznie typowanym**, co oznacza, że typ zmiennej jest ustalany automatycznie na podstawie przypisanej wartości. Operator `typeof` pozwala sprawdzić aktualny typ zmiennej.

### Przykład kodu:
```javascript
var a = 1;
var b = '1';
var c = 2.3;
var d = false;

document.write(typeof(a) + "<br>");
document.write(typeof(b) + "<br>");
document.write(typeof(c) + "<br>");
document.write(typeof(d));
```

### Wynik wykonania:
```text
number
string
number
boolean
```

### Podsumowanie typów:
| Zmienna | Wartość | Zwracany typ (`typeof`) | Opis |
| :--- | :--- | :--- | :--- |
| `a` | `1` | `number` | Liczba całkowita |
| `b` | `'1'` | `string` | Ciąg znaków (tekst) |
| `c` | `2.3` | `number` | Liczba zmiennoprzecinkowa |
| `d` | `false` | `boolean` | Wartość logiczna (prawda/fałsz) |

---

## 3. Operatory logiczne (`&&`, `||`, `!`)

Operatory logiczne pozwalają na łączenie wielu warunków i zwracają wartość `true` lub `false`.

### Przykład 1: Koniunkcja i dysjunkcja
```javascript
var a = true;
var b = false;
var c;

document.write(a + '<br>');

c = a && b; // Koniunkcja (I)
document.write(c + '<br>');

c = a || b; // Dysjunkcja (LUB)
document.write(c);
```

**Wynik:**
```text
true
false
true
```

### Przykład 2: Złożone wyrażenie logiczne i negacja
```javascript
var a = 2;
var b = -4;
var c;

c = ((a > 0) && (b < 0)) || (a > b);
document.write(c + '<br>');
document.write(!c); // Negacja
```

**Wynik:**
```text
true
false
```

### Tabela prawdy dla operatorów:
* **`&&` (AND / I)** — Zwraca `true` **tylko wtedy**, gdy obie strony są prawdziwe.
* **`||` (OR / LUB)** — Zwraca `true`, gdy **przynajmniej jedna** strona jest prawdziwa.
* **`!` (NOT / NEGACJA)** — Odwraca wartość logiczną (`!true` $
ightarrow$ `false`, `!false` $
ightarrow$ `true`).

---

## 4. Wartość bezwzględna i operator warunkowy (`? :`)

### Przykład kodu:
```javascript
var a = -3;
a = Math.abs(a); // Wartość bezwzględna
document.write(a + '<br>');

document.write((a > 0) ? 2 : 7); // Operator trójargumentowy
```

### Wynik:
```text
3
2
```

### Wyjaśnienie:
1. `Math.abs(-3)` zwraca wartość bezwzględną liczby `-3`, czyli `3`.
2. Operator trójargumentowy ma składnię:
   $$	ext{warunek} 	ext{ ? } 	ext{wartość\_gdy\_prawda} 	ext{ : } 	ext{wartość\_gdy\_fałsz}$$
   Skoro `a > 0` ($3 > 0$) jest prawdą (`true`), zostaje zwrócona pierwsza wartość, czyli `2`.
