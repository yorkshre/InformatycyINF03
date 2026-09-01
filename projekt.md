# Projekt zaliczeniowy: Semantyczny Moduł Alertu i Karty Powiadomień w Panelu SaaS

**Opis z życia:**  
Pracujesz jako Junior Frontend Developer w firmie budującej system zarządzania logistyką (SaaS). Zespół UX/UI oraz SEO/Accessibility przekazał Ci makietę natywnego modułu alertów systemowych, który ma pojawiać się w głównym panelu użytkownika. Twój lider wymaga, aby moduł opierał się na czystej semantyce HTML5, zewnętrznych stylach CSS i wzorcowych zasadach dostępności (WCAG).

---

## Specyfikacja Wymagań Technicznych

### 1. Architektura i Semantyka HTML5
* **Główny kontener:** Wykorzystaj znacznik `<main>` z przypisanym identyfikatorem `id="dashboard-content"` jako główny obszar roboczy strony.
* **Karta powiadomienia:** Wewnątrz `<main>` stwórz kontener `<article>` z identyfikatorem `id="alert-card"`.
* **Nagłówek karty:** Wewnątrz `<article>` umieść sekcję nagłówkową `<header>` z identyfikatorem `id="alert-header"`. W nagłówku dodaj tytuł alertu w znaczniku `<h2>`.
* **Treść komunikatu:** W sekcji głównej artykułu umieść paragraf `<p>` z klasą `class="alert-description"` oraz precyzyjnym atrybutem `title="Komunikat wygenerowany automatycznie przez system logistyczny"`, który wyświetli podpowiedź (tooltip) po najechaniu myszą.
* **Znacznik czasu:** Dołącz znacznik `<time datetime="...">` informujący o precyzyjnym czasie wystąpienia zdarzenia.

---

### 2. Podłączenie i Organizacja CSS
* Utwórz zewnętrzny arkusz stylów `style.css` umieszczony w tym samym katalogu co plik `index.html`.
* Zlinkuj plik CSS w sekcji `<head>` dokumentu za pomocą znacznika `<link>`.

---

### 3. Model Pudełkowy i Style Karty (`#alert-card`)
W pliku `style.css` przypisz do identyfikatora `#alert-card` następujące właściwości:
* **Szerokość:** `width: 320px;` (zmienna adaptacyjna).
* **Obramowanie:** Niestandardowa ramka `border: 2px dotted #1e40af;` (akcent akcentujący status).
* **Margines wewnętrzny:** `padding: 20px;` dla zachowania odpowiedniego oddechu wewnątrz karty (whitespace).
* **Margines zewnętrzny:** `margin: 20px auto;` do wyśrodkowania elementu na ekranie.
* **Tło i Cień:** Subtelny kolor tła `#f8fafc` oraz lekki cień `box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);`.

---

### 4. Typografia i Dostępność (`.alert-description`)
Dla klasy `.alert-description` zdefiniuj parametry zapewniające czytelność i zgodność z normami WCAG:
* **Rozmiar czcionki:** `font-size: 16px;`
* **Styl czcionki:** `font-style: italic;`
* **Kolor tekstu:** Użyj dobrze kontrastującego odcienia granatu/turkusu `#0e7490` (zamiast trudnego do odczytania jasnego koloru na białym tle).
* **Interakcja (Hover):** Dodaj pseudoklasę `:hover`, która przy najechaniu kursorom zmienia kolor tekstu na `#155e75` oraz dodaje delikatne przejście tonalne `transition: color 0.3s ease;`.

---

## Przykładowy Szablon Projektowy (Do Uzupełnienia)

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Panel Logistyczny – Moduł Powiadomień</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <main id="dashboard-content">
        <!-- Tutaj zbuduj strukturę karty powiadomienia -->
    </main>

</body>
</html>
```

---

## Kryteria Oceny i Odbioru Projektu

1. **Poprawność Strukturalna:** Czy znacznik `<main>` zawiera odpowiednio zagnieżdżone `<article>`, `<header>` oraz `<p>`?
2. **Kaskadowość i Izolacja Stylów:** Czy wszystkie style zostały przeniesione do `style.css` bez stosowania stylów wpisanych inline (`style="..."`)?
3. **Zgodność z Model Pudełkowym (Box Model):** Czy właściwości `width`, `padding` oraz `border` zostały prawidłowo przeliczone i zaaplikowane do karty?
4. **Interaktywność:** Czy atrybut `title` oraz efekty hover działają poprawnie w przeglądarce?
