# Obiekty w JavaScript i DOM (Egzamin INF.03 / EE.09)

---

## 1. Obiekty w JavaScript – Teoria i Zastosowanie Egzaminacyjne

Obiekt w JavaScript to złożona struktura danych przechowująca powiązane właściwości (zmienne) oraz metody (funkcje). 

Na egzaminie zawodowym INF.03 znajomość obiektów przydaje się do:
* Przetwarzania struktur danych (np. tablice obiektów reprezentujące towary, bilety, użytkowników lub usługi).
* Pobierania danych z formularzy HTML i pakowania ich w jeden obiekt logiczny.
* Dynamicznego generowania zawartości strony (tabel, list) na podstawie danych z obiektów.
* Operacji matematycznych i manipulacji datami za pomocą obiektów wbudowanych (`Math`, `Date`).

---

### Tworzenie obiektu (Literał obiektu)

```javascript
const produkt = {
    nazwa: "Pralka",
    cena: 1200,
    ilosc: 3,
    
    // Metoda obiektu
    obliczWartosc: function() {
        return this.cena * this.ilosc;
    }
};
```

---

### Dostęp do właściwości i metod

1. **Notacja kropkowa (zalecana):**
   ```javascript
   console.log(produkt.nazwa); // Pralka
   console.log(produkt.obliczWartosc()); // 3600
   ```

2. **Notacja tablicowa:**
   ```javascript
   console.log(produkt["cena"]); // 1200
   ```

---

### Modyfikacja obiektu

```javascript
produkt.cena = 1100; // zmiana istniejącej właściwości
produkt.gwarancja = 24; // dodanie nowej właściwości
```

---

### Tablice obiektów (Format egzaminacyjny)

W zadaniach practicalnych dane bardzo często występują w postaci tablicy obiektów:

```javascript
const uslugi = [
    { nazwa: "Mycie", cena: 30 },
    { nazwa: "Woskowanie", cena: 50 },
    { nazwa: "Tapicerka", cena: 100 }
];

// Przeglądanie tablicy za pomocą pętli for...of
for (let usluga of uslugi) {
    console.log(usluga.nazwa + " - " + usluga.cena + " zł");
}
```

---

## 2. Model DOM – Praktyczny przykład z komentarzami

Poniższy przykład pokazuje typowy schemat ze sprawdzianów i arkuszy CKE INF.03: pobranie danych z elementów HTML, przetworzenie ich i dynamiczna zmiana treści na stronie za pomocą obiektu `document` (DOM).

**Kod HTML:**
```html
<label>Podaj imię: <input type="text" id="poleImie"></label>
<button id="przyciskPowitanie">Wyświetl powitanie</button>
<div id="komunikat"></div>
```

**Kod JavaScript (z komentarzami):**
```javascript
// 1. Podpięcie nasłuchiwania zdarzenia 'click' pod przycisk o ID 'przyciskPowitanie'
document.getElementById('przyciskPowitanie').addEventListener('click', function() {
    
    // 2. Pobranie wartości wpisanej przez użytkownika w pole tekstowe
    const wpisaneImie = document.getElementById('poleImie').value;
    
    // 3. Sprawdzenie prostego warunku (walidacja)
    if (wpisaneImie.trim() === "") {
        // Jeśli pole jest puste, wypisz komunikat o błędzie
        document.getElementById('komunikat').innerHTML = "<span style='color: red;'>Musisz podać imię!</span>";
        return; // przerwanie dalszego wykonywania funkcji
    }
    
    // 4. Utworzenie obiektu przechowującego dane użytkownika
    const uzytkownik = {
        imie: wpisaneImie,
        czasLogowania: new Date().toLocaleTimeString(),
        
        // Metoda generująca powitanie
        generujWiadomosc: function() {
            return `Witaj, ${this.imie}! Zalogowano o godzinie ${this.czasLogowania}.`;
        }
    };
    
    // 5. Modyfikacja struktury DOM – wstawienie wygenerowanego tekstu do elementu div
    const kontenerWyniku = document.getElementById('komunikat');
    kontenerWyniku.innerHTML = `<b>${uzytkownik.generujWiadomosc()}</b>`;
    
    // Dodatkowa modyfikacja stylów elementu DOM przez JS
    kontenerWyniku.style.backgroundColor = "#eef9ff";
    kontenerWyniku.style.padding = "10px";
    kontenerWyniku.style.marginTop = "10px";
});
```

---

## 3. Arkusz Zadań dla Ucznia

---

### Zadanie 1
Stwórz obiekt o nazwie `samochod`, który będzie posiadał następujące właściwości:
* `marka` (tekst)
* `model` (tekst)
* `przebieg` (liczba)
* `stanPaliwa` (liczba, np. 50)

Dodaj do obiektu metody:
* `przejedz(km)` – zwiększa `przebieg` o podaną liczbę kilometrów oraz zmniejsza `stanPaliwa` o `km * 0.05`.
* `zatankuj(litry)` – zwiększa `stanPaliwa` o podaną liczbę litrów.

Przetestuj działanie obiektu w konsoli przeglądarki (wywołaj obie metody i sprawdź stan właściwości).

---

### Zadanie 2
Napisz funkcję `stworzBilet(rodzaj, cenaBazowa, znizkaPercent)`, która zwraca obiekt biletu o właściwościach `rodzaj`, `cenaBazowa`, `znizka` oraz metodzie `obliczCene()`, która zwraca ostateczną cenę biletu po uwzględnieniu zniżki.

---

### Zadanie 3
Utwórz tablicę obiektów o nazwie `magazyn`. Każdy obiekt powinien reprezentować towar i zawierać pola: `id`, `nazwa`, `cena`, `dostepny` (true/false).

Napisz kod JS, który:
1. Wypisze w konsoli nazwy produktów, które są dostępne (`dostepny === true`).
2. Obliczy średnią cenę wszystkich produktów znajdujących się w magazynie.

---

### Zadanie 4
Utwórz tablicę obiektów `uczniowie` zawierającą imiona oraz średnie ocen kilku uczniów. Napisz funkcję `znajdzNajlepszego(tablica)`, która przyjmie jako parametr tablicę uczniów i zwróci obiekt ucznia z najwyższą średnią.

---

### Zadanie 5 (Zadanie stylizowane na INF.03)
Stwórz stronę HTML z prostym skryptem JS według poniższej specyfikacji.

**Wymagania dla HTML:**
* Formularz zawierający:
  * Pole wyboru typu `<select>` o ID `kategoria` z opcjami: "Elektronika" (cena 100 zł), "Odzież" (cena 50 zł), "Książki" (cena 30 zł).
  * Pole liczbowe `<input type="number">` o ID `sztuki` określające liczbę zamawianych przedmiotów.
  * Pole wyboru typu checkbox o ID `dostawa` ("Dostawa kurierem +15 zł").
  * Przycisk `<button type="button">` o ID `obliczBtn` z napisem "Przelicz".
* Kontener `<div>` o ID `wynik` do wyświetlania podsumowania.

**Wymagania dla JavaScript:**
1. Po kliknięciu przycisku skrypt powinien pobrać wartości z formularza.
2. Skrypt tworzy obiekt `zamowienie` z pobranymi danymi oraz metodą `obliczRazem()`.
3. Metoda `obliczRazem()` wylicza łączną kwotę (cena kategorii * sztuki + ewentualny koszt dostawy).
4. Podsumowanie zamowienia zostaje wstawione do elementu `#wynik` w formacie:  
   `Zamówienie: [kategoria], sztuk: [sztuki]. Do zapłaty: [suma] zł.`