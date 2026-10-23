# Scenariusz Lekcji & Materiały Dydaktyczne: JavaScript – Funkcje Wbudowane, Własne i Manipulacja DOM (Formularz Rejestracji)

**Kwalifikacja:** INF.03 (Tworzenie i administracja stronami i aplikacjami internetowymi oraz bazami danych)  
**Temat:** Wykorzystanie funkcji wbudowanych, własnych oraz modelu DOM do walidacji formularza rejestracji w JavaScript.

---

## 1. Wprowadzenie Teoretyczne

### 1.1 Funkcje Wbudowane w JavaScript (Narzędzia CKE INF.03)
W języku JavaScript dostępne są wbudowane metody i funkcje, które znacznie ułatwiają walidację danych pobieranych z elementów HTML:

* **Konwersja i sprawdzanie typów:**
  * `parseInt(tekst)` / `parseFloat(tekst)` – konwersja ciągu znaków na liczbę całkowitą lub zmiennoprzecinkową.
  * `Number(wartość)` – rzutowanie wartości na typ liczbowy.
  * `isNaN(wartość)` – sprawdza, czy przekazana wartość NIE jest prawidłową liczbą (`true` jeśli to nie liczba).
* **Metody i właściwości tekstowe (String):**
  * `.length` – właściwość zwracająca długość łańcucha znaków (np. `haslo.length`).
  * `.trim()` – metoda usuwająca białe znaki (spacje, tabulatory) z początku i końca tekstu.
  * `.includes(szukanyTekst)` – sprawdza, czy tekst zawiera podany podciąg (zwraca `true` lub `false`).
  * `.toLowerCase()` / `.toUpperCase()` – zmiana wielkości liter.

### 1.2 Funkcje Tworzone przez Użytkownika (Funkcje Własne)
Funkcje własne pozwalają na grupowanie powtarzalnego kodu oraz dzielenie logiki aplikacji na czytelne bloki.

```javascript
// Przykład funkcji przyjmującej argumenty i zwracającej wartość
function sprawdzDlugoscHasla(haslo, minimalnaDlugosc) {
    if (haslo.length >= minimalnaDlugosc) {
        return true;
    } else {
        return false;
    }
}
```

### 1.3 Manipulacja DOM w Formularzach
Model DOM (Document Object Model) umożliwia odczytywanie stanu pól formularza i ich dynamiczną modyfikację:

* **Pobieranie wartości:** `document.getElementById("idPola").value`
* **Odczyt stanu checkboxa:** `document.getElementById("idCheckboxa").checked` (zwraca `true` / `false`)
* **Zmiana zawartości tekstu:** `element.innerText = "Komunikat"`
* **Modyfikacja stylów CSS:** `element.style.borderColor = "red"` lub `element.style.color = "green"`

---

## 2. Przykład Aplikacji: Wzorcowy Formularz Rejestracji

Poniższy kod prezentuje typowe zadanie egzaminacyjne z kwalifikacji **INF.03**, łączące walidację pól, funkcje wbudowane i własne oraz zmianę stylów w DOM.

### 2.1 Kod HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formularz Rejestracji - INF.03</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            padding: 20px;
        }
        .form-container {
            background-color: #ffffff;
            max-width: 400px;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .pole {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
        #komunikat {
            margin-top: 15px;
            font-weight: bold;
            padding: 10px;
            border-radius: 4px;
        }
    </style>
</head>
<body>

    <div class="form-container">
        <h2>Panel Rejestracji</h2>

        <div class="pole">
            <label for="login">Login:</label>
            <input type="text" id="login" placeholder="Wpisz login">
        </div>

        <div class="pole">
            <label for="email">E-mail:</label>
            <input type="text" id="email" placeholder="przyklad@domena.pl">
        </div>

        <div class="pole">
            <label for="haslo">Hasło:</label>
            <input type="password" id="haslo">
        </div>

        <div class="pole">
            <label for="powtorzHaslo">Powtórz hasło:</label>
            <input type="password" id="powtorzHaslo">
        </div>

        <div class="pole">
            <label>
                <input type="checkbox" id="regulamin"> Akceptuję regulamin serwisu
            </label>
        </div>

        <button id="btnRejestruj">Zarejestruj się</button>

        <div id="komunikat"></div>
    </div>

    <script src="skrypt.js"></script>
</body>
</html>
```

### 2.2 Kod JavaScript (`skrypt.js`)

```javascript
// Podpięcie zdarzenia kliknięcia pod przycisk
document.getElementById("btnRejestruj").addEventListener("click", walidujFormularz);

// Główna funkcja walidująca
function walidujFormularz() {
    // 1. Pobranie danych z formularza
    let loginInput = document.getElementById("login");
    let emailInput = document.getElementById("email");
    let hasloInput = document.getElementById("haslo");
    let powtorzHasloInput = document.getElementById("powtorzHaslo");
    let regulaminInput = document.getElementById("regulamin");

    // Użycie funkcji wbudowanej .trim() do usunięcia spacji
    let login = loginInput.value.trim();
    let email = emailInput.value.trim();
    let haslo = hasloInput.value;
    let powtorzHaslo = powtorzHasloInput.value;
    let czyRegulamin = regulaminInput.checked;

    // Resetowanie stylów obramowań
    zresetujStyl([loginInput, emailInput, hasloInput, powtorzHasloInput]);

    // 2. Sprawdzenie, czy pola nie są puste
    if (login === "" || email === "" || haslo === "" || powtorzHaslo === "") {
        wyswietlBlad("Wszystkie pola muszą być wypełnione!");
        if (login === "") oznaczBlednePole(loginInput);
        if (email === "") oznaczBlednePole(emailInput);
        if (haslo === "") oznaczBlednePole(hasloInput);
        if (powtorzHaslo === "") oznaczBlednePole(powtorzHasloInput);
        return;
    }

    // 3. Walidacja e-maila za pomocą funkcji własnej
    if (!sprawdzEmail(email)) {
        wyswietlBlad("Podaj poprawny adres e-mail (musi zawierać '@' oraz '.')!");
        oznaczBlednePole(emailInput);
        return;
    }

    // 4. Walidacja długości hasła (funkcja wbudowana .length)
    if (haslo.length < 6) {
        wyswietlBlad("Hasło musi składać się z co najmniej 6 znaków!");
        oznaczBlednePole(hasloInput);
        return;
    }

    // 5. Sprawdzenie zgodności haseł
    if (haslo !== powtorzHaslo) {
        wyswietlBlad("Podane hasła różnią się od siebie!");
        oznaczBlednePole(hasloInput);
        oznaczBlednePole(powtorzHasloInput);
        return;
    }

    // 6. Sprawdzenie akceptacji regulaminu
    if (!czyRegulamin) {
        wyswietlBlad("Musisz akceptować regulamin serwisu!");
        return;
    }

    // Jeśli walidacja przebiegła pomyślnie
    wyswietlSukces("Konto dla użytkownika " + login + " zostało pomyślnie utworzone!");
}

// --- FUNKCJE POMOCNICZE (WŁASNE) ---

// Funkcja własna sprawdzająca poprawność adresu e-mail
function sprawdzEmail(adres) {
    // Użycie funkcji wbudowanej .includes()
    return adres.includes("@") && adres.includes(".");
}

// Funkcja wyświetlająca komunikat o błędzie i zmieniająca style w DOM
function wyswietlBlad(tresc) {
    let komunikatDiv = document.getElementById("komunikat");
    komunikatDiv.innerText = tresc;
    komunikatDiv.style.color = "#721c24";
    komunikatDiv.style.backgroundColor = "#f8d7da";
    komunikatDiv.style.border = "1px solid #f5c6cb";
}

// Funkcja wyświetlająca komunikat sukcesu
function wyswietlSukces(tresc) {
    let komunikatDiv = document.getElementById("komunikat");
    komunikatDiv.innerText = tresc;
    komunikatDiv.style.color = "#155724";
    komunikatDiv.style.backgroundColor = "#d4edda";
    komunikatDiv.style.border = "1px solid #c3e6cb";
}

// Funkcja podświetlająca błędne pole
function oznaczBlednePole(element) {
    element.style.borderColor = "red";
}

// Funkcja przywracająca domyślny wygląd pól
function zresetujStyl(elementy) {
    elementy.forEach(function(el) {
        el.style.borderColor = "#ccc";
    });
}
```

---

## 3. Zestaw Zadań dla Uczniów (Karta Pracy)

### Zadanie 1: Licznik siły hasła
Dodaj pod polem hasła element `<p id="silaHasla"></p>`. Napisz funkcję własną `ocenSileHasla(haslo)`, która podpięta pod zdarzenie `input` pola hasła (`addEventListener("input", ...)`):
* Wyświetla tekst **"Słabe"** (kolor czerwony), jeśli hasło ma mniej niż 6 znaków.
* Wyświetla tekst **"Średnie"** (kolor pomarańczowy), jeśli hasło ma od 6 do 9 znaków.
* Wyświetla tekst **"Mocne"** (kolor zielony), jeśli hasło ma 10 lub więcej znaków oraz zawiera co najmniej jedną cyfrę (skorzystaj z pętli lub sprawdź znak po znaku za pomocą `isNaN()`).

---

### Zadanie 2: Walidacja wieku (Liczby i Konwersja)
Do formularza dodaj pole tekstowe lub liczbowe na rok urodzenia (`<input type="number" id="rokUrodzenia">`).
1. Utwórz funkcję `sprawdzWiek(rok)`, która:
   * Zamienia pobraną wartość na liczbę całkowitą za pomocą `parseInt()`.
   * Sprawdza przy użyciu `isNaN()`, czy użytkownik podał prawidłową wartość.
   * Oblicza wiek użytkownika (przyjmując aktualny rok).
2. Jeśli wiek jest mniejszy niż 18 lat, formularz zablokuje rejestrację i wyświetli komunikat: *"Rejestracja dozwolona tylko dla osób pełnoletnich!"*.

---

### Zadanie 3: Generowanie domyślnego loginu z imienia i nazwiska
Zamiast osobnego pola login, dodaj pola *Imię* oraz *Nazwisko*.
1. Napisz funkcję własną `generujLogin(imie, nazwisko)`, która:
   * Usuwa zbędne spacje z obu pól (`.trim()`).
   * Zamienia wszystkie litery na małe (`.toLowerCase()`).
   * Zwraca login utworzony z pierwszej litery imienia oraz pełnego nazwiska (np. dla "Jan Kowalski" zwraca "jkowalski").
2. Wyświetl wygenerowany login w elemencie `<span>` na stronie w momencie opuszczenia pola z nazwiskiem (zdarzenie `blur` lub `change`).