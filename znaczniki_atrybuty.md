Znaczniki, Atrybuty i Komentarze
**Kwalifikacja INF.03**

---

## 1. Wprowadzenie do HTML

**HTML** (*HyperText Markup Language*) to kaskadowy język znaczników służący do tworzenia i strukturyzowania zawartości stron internetowych. Nie jest językiem programowania (nie posiada logiki, zmiennych czy pętli), lecz strukturą opisową.

* **Dokumentacja i Standardy:** Standard HTML jest rozwijany przez organizację **W3C** (*World Wide Web Consortium*) oraz **WHATWG**.
* **Aktualna wersja:** HTML5.

---

## 2. Znaczniki (Tags)

Znaczniki to podstawowe elementy konstrukcyjne języka HTML. Służą do informowania przeglądarki, w jaki sposób ma zinterpretować dany fragment tekstu lub zasób.

### 2.1. Budowa znacznika
Znaczniki zapisujemy w nawiasach ostrych `< >`. Występują w dwóch głównych odmianach:

1. **Znaczniki parzyste** – składają się ze znacznika otwierającego i zamykającego (poprzedzonego slash’em `/`):
   ```html
   <p>To jest akapit tekstu.</p>
   <h1>Nagłówek główny</h1>
2. **Znaczniki nieparzyste / samozamykające** – nie zawierają treści ani znacznika zamykającego:
   ```html
   <br>  <!-- złamanie linii -->
   <hr>  <!-- pozioma linia podziału -->
   <img src="obrazek.jpg" alt="Opis obrazka">  <!-- wstawienie obrazu -->
   <input type="text">  <!-- pole formularza -->
   ```

## 3. Podstawowa struktura dokumentu HTML5

Każdy poprawny dokument HTML5 powinien posiadać następującą strukturę bazową:

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tytuł Strony - Technik Programista</title>
</head>
<body>

    <header>
        <h1>Witaj na mojej stronie</h1>
    </header>

    <main>
        <p>To jest treść widoczna dla użytkownika.</p>
    </main>

    <footer>
        <p>&copy; 2026 Technik Programista</p>
    </footer>

</body>
</html>
```

### Wyjaśnienie elementów struktury:
* `<!DOCTYPE html>` – deklaracja typu dokumentu (informuje przeglądarkę, że używamy HTML5).
* `<html lang="pl">` – główny element (korzeń) dokumentu. Atrybut `lang` określa język treści.
* `<head>` – sekcja nagłówkowa (zawiera metadane, tytuł strony, podpięte style CSS, skrypty – informacje niewidoczne bezpośrednio na stronie).
* `<meta charset="UTF-8">` – określa kodowanie znaków (UTF-8 obsługuje polskie znaki diakrytyczne).
* `<meta name="viewport" ...>` – zapewnia prawidłowe skalowanie na urządzeniach mobilnych (RWD).
* `<title>` – tytuł strony wyświetlany na karcie przeglądarki.
* `<body>` – ciało dokumentu (zawiera całą treść widoczną dla użytkownika).

---

  ## 4. Atrybuty (Attributes)

Atrybuty dostarczają dodatkowych informacji o elementach HTML lub zmieniają ich zachowanie.

### 4.1. Składnia atrybutów
Atrybuty umieszcza się **zawsze w znaczniku otwierającym** według schematu: `nazwa_atrybutu="wartość"`.

```html
<a href="https://example.com" target="_blank" title="Przejdź do strony">Odnośnik</a>
```

### 4.2. Najważniejsze atrybuty globalne (dostępne dla większości znaczników)
* `id` – unikalny identyfikator elementu na stronie (np. `id="main-nav"`). Na stronie może być tylko jeden element o danym `id`.
* `class` – nazwa klasy (lub klas rozdzielonych spacją), używana do grupowania elementów w celu ich stylizowania (CSS) lub obsługi w JavaScript (np. `class="btn btn-primary"`).
* `style` – pozwala na dodanie stylów CSS bezpośrednio do elementu (tzw. inline styles).
* `title` – dodatkowa informacja o elemencie, wyświetlana jako tooltip po najechaniu kursorem.
* `lang` – określa język danego elementu.
* `hidden` – ukrywa element na stronie.

### 4.3. Przykłady atrybutów specyficznych dla znaczników
* **Obrazy (`<img>`):**
  * `src` – ścieżka do pliku graficznego.
  * `alt` – tekst alternatywny (wyświetlany, gdy obraz się nie wczyta oraz czytany przez czytniki dla niedowidzących).
  * `width` / `height` – szerokość / wysokość obrazu.
* **Linki (`<a>`):**
  * `href` – adres docelowy (URL lub kotwica `#id`).
  * `target="_blank"` – otwiera link w nowej karcie.
* **Formularze (`<input>`):**
  * `type` – typ pola (np. `text`, `password`, `email`, `checkbox`, `submit`).
  * `placeholder` – tekst podpowiedzi wewnątrz pola.
  * `value` – domyślna lub wprowadzona wartość pola.
  * `required` – pole wymagane do wysłania formularza (atrybut logiczny/booleowski).

---

## 5. Komentarze w HTML

Komentarze służą do umieszczania informacji dla programisty. Są całkowicie ignorowane przez przeglądarkę i nie wyświetlają się na stronie (są jednak widoczne w kodzie źródłowym strony!).

### 5.1. Składnia komentarza
Komentarz rozpoczyna się od `<!--` a kończy na `-->`.

```html
<!-- To jest komentarz jednoliniowy -->

<!--
    To jest komentarz
    wieloliniowy.
    Możemy tu opisać strukturę sekcji.
-->
```

### 5.2. Zastosowanie komentarzy
1. **Dokumentowanie kodu:** Wyjaśnienie skomplikowanej struktury lub przeznaczenia sekcji.
2. **Organizacja kodu:** Oznaczanie początku i końca ważnych bloków (np. `<!-- START: Navigation --> ... <!-- END: Navigation -->`).
3. **Debugowanie (Testowanie):** Tymczasowe wyłączanie fragmentów kodu bez konieczności ich usuwania.

---

## 6. Szybka Ściąga / Podsumowanie

| Pojęcie | Opis | Przykład |
| :--- | :--- | :--- |
| **Znacznik parzysty** | Posiada znacznik otwierający i zamykający. | `<h1>Tekst</h1>` |
| **Znacznik samozamykający** | Nie wymaga znacznika zamykającego. | `<img src="a.jpg" alt="A">` |
| **Atrybut** | Właściwość rozszerzająca znacznik. | `class="box"` |
| **Identyfikator (`id`)** | Unikalna nazwa elementu (max 1 na stronie). | `id="header"` |
| **Klasa (`class`)** | Nazwa grupy elementów (wielokrotnego użytku). | `class="card active"` |
| **Komentarz** | Kod niewidoczny na stronie dla użytkownika. | `<!-- Komentarz -->` |

---

## 7. Pytania kontrolne / Zadania utrwalające (INF.03)

1. Jaka jest różnica między atrybutami `id` a `class`?
2. Dlaczego stosowanie atrybutu `alt` w znaczniku `<img>` jest obowiązkowe ze względów dostępności i SEO?
3. Jak zamieścić komentarz wieloliniowy w kodzie HTML?
4. Co się stanie, jeśli zapomnisz zamknąć znacznika parzystego (np. `<div>`)?
HTML_Znaczniki_Atrybuty_Komentarze_Caly_Dokument-v2.md
Wyświetlam HTML_Znaczniki_
