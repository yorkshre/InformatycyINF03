***Javascript pętla while***

Kiedy masz już stronę z elementem <script> (lub odwołanie 
do oddzielnego pliku JavaScript), możesz rozpocząć kodowanie. JavaScript jest pełnowartościowym językiem programowania, więc możesz w nim robić większość tego co w innych językach, 
a właściwie nawet więcej, ponieważ programujemy w nim wewnątrz strony internetowej.

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


