# Pętle warunkowe i instrukcje sterujące w JavaScript

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

```js
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



