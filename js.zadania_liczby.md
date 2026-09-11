# Zestaw zadań i skryptów w JavaScript

### Zadanie 1: Suma trzech liczb
Napisz program, który wczytuje trzy liczby od użytkownika, oblicza ich sumę i wyświetla wynik na ekranie.

```javascript
const a = parseFloat(prompt("Podaj pierwszą liczbę: "));
const b = parseFloat(prompt("Podaj drugą liczbę: "));
const c = parseFloat(prompt("Podaj trzecią liczbę: "));

const suma = a + b + c;

console.log(`Suma podanych liczb wynosi: ${suma}`);
