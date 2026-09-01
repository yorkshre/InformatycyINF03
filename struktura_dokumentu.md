 HTML i CSS – Kompletne Kompendium wiedzy

## 1. Definicja HTML i CSS

### **HTML (HyperText Markup Language)**
Hipertekstowy język znaczników wykorzystywany do tworzenia struktury strony internetowej i jej zawartości.

* **Hipertekstowy** – dane mają postać niezależnych elementów połączonych ze sobą odnośnikami (linkami).
* **Język znaczników** – format dokumentu, który poza samą treścią zawiera dodatkowe elementy określające jego układ, wygląd oraz sposób wyświetlania.

> **Ciekawostka:** Pierwsze przeglądarki internetowe (w latach 1991–1992) wyświetlały wyłącznie prosty, sformatowany tekst z podstawowymi odnośnikami, bez skomplikowanych układów graficznych czy stylów.

### **CSS (Cascading Style Sheets)**
Kaskadowe Arkusze Stylów to język używany do definiowania wyglądu i układu elementów na stronie. CSS pozwala na określenie kolorów, czcionek, marginesów, obramowań oraz wielu innych właściwości wizualnych elementów strukturalnych HTML.

---

## 2. Podstawowy szablon strony w HTML5

```html
<!DOCTYPE HTML>
<html lang="pl">
    <head>
        <meta charset="utf-8"/>
        <meta name="description" content="" />
        <meta name="keywords" content="" />
        <title>Tytuł strony</title>
    </head>
    <body>
        <header>
            <h1>Nagłówek 1</h1>
        </header>
        <nav>
            Nawigacja
        </nav>
        <main>
            <section>
                <article>
                    <h2>Artykuł pierwszy</h2>
                    <p>To jest treść artykułu.</p>
                </article>
            </section>
        </main>
        <footer>
            Stopka
        </footer>
    </body>
</html>
```

---

## 3. Opis podstawowych elementów HTML

* **`html`** – główny element określający, że jest to dokument HTML. Wewnątrz znajdują się dwa kluczowe elementy: `head` oraz `body`.
* **`head`** – zawiera metadane i informacje o dokumencie (tytuł, meta tagi, style CSS itp.). Definiuje ważne informacje o stronie, które nie są wyświetlane bezpośrednio w oknie przeglądarki.
* **`title`** – określa tytuł strony internetowej wyświetlany na pasku tytułu lub karcie przeglądarki.
* **`meta`** – służy do definiowania informacji o dokumencie (opis strony, słowa kluczowe, kodowanie znaków itp.)[cite: 3]. Jest ważny dla wyszukiwarek internetowych i wspomaga pozycjonowanie (SEO)[cite: 3].
* **`body`** – określa właściwą zawartość strony wyświetlaną w okienku przeglądarki (nagłówki, tekst, obrazy, linki)[cite: 3].
* **`header`** – nagłówek strony lub sekcji, zazwyczaj zawiera logo, menu nawigacyjne i inne informacje na temat strony[cite: 3].
* **`nav`** – sekcja zawierająca menu nawigacyjne na stronie internetowej[cite: 3].
* **`main`** – definiuje główną treść strony (unikalną dla danego dokumentu)[cite: 3].
* **`section`** – wydzielona sekcja tematyczna strony (np. wpis na blogu, artykuł, galeria zdjęć)[cite: 3].
* **`article`** – samodzielna, niezależna treść (artykuł, post na blogu, recenzja, komentarz)[cite: 3].
* **`aside`** – treść poboczna (np. pasek boczny, reklamy, lista kategorii, menu)[cite: 3].
* **`footer`** – stopka strony lub sekcji (autor, prawa autorskie, linki powiązane, kontakt)[cite: 3].

---

## 4. Deklaracja DOCTYPE
Deklaracja `DOCTYPE` to linijka kodu umieszczana na samym początku dokumentu HTML, która informuje przeglądarkę internetową, jakiej wersji HTML należy używać do poprawnego wyświetlenia strony[cite: 3]. Jest to kluczowa informacja, ponieważ różne wersje mają odmienne zasady i składnię[cite: 3].


### HTML 4.01 Strict (starsza wersja)
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "[http://www.w3.org/TR/html4/strict.dtd](http://www.w3.org/TR/html4/strict.dtd)">
```

> **Warto zaznaczyć:** Deklaracja `DOCTYPE` w starszych wersjach HTML była bardziej skomplikowana i zawierała szczegółowe odwołania do DTD (Document Type Definition), które określały dokładnie dozwalane elementy i atrybuty[cite: 3]. W HTML5 proces ten został maksymalnie uproszczony[cite: 3].
---

## 5. Element `<head>` w szczegółach

Element `<head>` definiuje informacje o dokumencie, które nie są widoczne bezpośrednio na stronie, ale są niezbędne dla przeglądarki oraz robotów indeksujących wyszukiwarek[cite: 3]. Umieszcza się go pomiędzy otwierającym tagiem `<html>` a otwierającym tagiem `<body>`[cite: 3].

### Kluczowe elementy wewnątrz `<head>`:

#### 1. Tytuł strony (`<title>`)
Określa tytuł strony wyświetlany na pasku tytułowym przeglądarki oraz w wynikach wyszukiwania[cite: 3].
```html
<head>
  <title>Tytuł strony</title>
</head>
```

#### 2. Metadane (`<meta>`)
Definiuje metadane strony, takie jak opis, słowa kluczowe, autor czy kodowanie znaków[cite: 3].
```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Opis strony">
  <meta name="keywords" content="słowo kluczowe1, słowo kluczowe2, słowo kluczowe3">
  <meta name="author" content="Autor strony">
</head>
```
* **`charset`** – kodowanie znaków (dla języka polskiego zalecane jest `UTF-8` lub `ISO-8859-2`)[cite: 3].
* **`description`** – zwięzły, tekstowy opis naszej strony internetowej[cite: 3].
* **`keywords`** – słowa kluczowe charakterystyczne dla witryny

#### 3. Podłączanie plików zewnętrznych (`<link>`)
Umożliwia podłączenie zasobów zewnętrznych, takich jak pliki stylów CSS czy ikona favicon[cite: 3].
```html
<head>
  <link rel="stylesheet" href="style.css">
  <link rel="shortcut icon" href="favicon.ico">
</head>
```

#### 4. Style wewnętrzne (`<style>`)
Umożliwia zdefiniowanie stylów CSS bezpośrednio w dokumencie bez konieczności tworzenia osobnego pliku[cite: 3].
```html
<head>
  <style>
    body {
      background-color: #f5f5f5;
      font-family: Arial, sans-serif;
    }
  </style>
</head>
```

#### 5. Skrypty JavaScript (`<script>`)
Umożliwia dodanie skryptów wykonujących funkcje interaktywne lub walidację formularzy[cite: 3].
```html
<head>
  <script>
    function myFunction() {
      alert("Hello World!");
    }
  </script>
  <script src="script.js"></script>
</head>
```

---

## 6. Element `<body>` i struktura semantyczna HTML5

W HTML5 element `<body>` można podzielić na różne sekcje strukturalne[cite: 3]:

```html
<body>
  <header>
    <h1>Tytuł strony</h1>
    <nav>
      <ul>
        <li><a href="#">Strona główna</a></li>
        <li><a href="#">O nas</a></li>
        <li><a href="#">Kontakt</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <article>
      <h2>Artykuł pierwszy</h2>
      <p>To jest treść artykułu.</p>
    </article>
    <article>
      <h2>Artykuł drugi</h2>
      <p>To jest treść drugiego artykułu.</p>
    </article>
  </main>

  <footer>
    <p>Copyright &copy; 2023</p>
  </footer>
</body>
```

### Charakterystyka sekcji wewnątrz `<body>`:
* **Sekcja główna (`<main>`)** – reprezentuje główną sekcję strony i zawiera istotne treści główne[cite: 3]. Może być użyta tylko raz w obrębie elementu `<body>`[cite: 3].
* **Artykuł (`<article>`)** – niezależna, samodzielna treść nadająca się do dystrybucji lub publikacji jako całość (artykuł, post na blogu, recenzja, komentarz, raport)[cite: 3].
* **Nagłówek (`<header>`)** – nagłówek strony lub sekcji; zazwyczaj zawiera tytuł, logo, informacje kontaktowe czy menu[cite: 3].
* **Nawigacja (`<nav>`)** – blok zawierający łącza i linki nawigacyjne do podstron, menu boczne lub kategorie[cite: 3].
* **Stopka (`<footer>`)** – stopka strony lub sekcji z informacjami o autorze, prawach autorskich, datach publikacji czy linkach[cite: 3].
* **Treść poboczna (`<aside>`)** – treść poboczna powiązana tematycznie z głównym wątkiem (widgety, najnowsze wpisy, reklamy, menu boczny)[cite: 3].

---

## 7. Historia i rozwój wersji HTML oraz CSS

### Historia HTML
* **1989 rok** – powstanie języka HTML z inicjatywy Tima Bernersa-Lee do oznaczania dokumentów tekstowych.
* **1993 rok** – ogłoszenie pierwszej oficjalnej specyfikacji HTML.
* **2014 rok (HTML5)** – wydanie standardu HTML5, który zrewolucjonizował strony internetowe wprowadzając elementy semantyczne, wbudowane multimedia i zaawansowane API[cite: 3].

### Historia CSS
* **1996 rok** – ogłoszenie CSS w celu rozdzielenia warstwy treści (HTML) od warstwy prezentacji wizualnej.
* **CSS3** – podział specyfikacji na niezależne moduły (animacje, flexbox, grid, Media Queries).

---

## 8. Przegląd wersji HTML i CSS

### Wersje HTML

| Wersja HTML | Rok wydania | Najważniejsze nowości |
| :--- | :---: | :--- |
| **HTML 2.0** | 1995 | Wsparcie dla tabel i formularzy |
| **HTML 3.2** | 1997 | Pierwsze oficjalne wsparcie dla arkuszy stylów |
| **HTML 4.01** | 1999 | Wsparcie dla warstw (CSS) oraz ramek (*frames*) |
| **XHTML 1.0** | 2000 | Ścisła składnia XML |
| **HTML5** | 2014 | Multimedia, znaczniki semantyczne (`header`, `footer`, `nav`), nowe API[cite: 3] |

### Wersje CSS

| Wersja CSS | Rok wydania | Najważniejsze nowości |
| :--- | :---: | :--- |
| **CSS 1** | 1996 | Pierwsza specyfikacja, kaskadowość, podstawy stylizowania |
| **CSS 2** | 1998 | Pozycjonowanie elementów, media dla druku |
| **CSS 2.1** | 2004 | Poprawki błędów i standaryzacja specyfikacji CSS 2 |
| **CSS 3** | 1999+ | Modułowość, Media Queries, cienie, gradienty, flexbox, animacje |

---


## 9. Sposoby dołączania CSS do HTML

1. **Zewnętrzny plik CSS (zalecane):** Podłączenie w sekcji `<head>` za pomocą znacznika `<link>`:
   ```html
   <link rel="stylesheet" href="style.css">
   ```
2. **Wewnętrzne style:** Umieszczenie reguł w znaczniku `<style>` w sekcji `<head>`:
   ```html
   <style>
     body { background-color: #f5f5f5; }
   </style>
   ```
3. **Style liniowe (inline):** Dopisanie stylu bezpośrednio do danego znacznika:
   ```html
   <p style="color: blue;">Przykładowy tekst</p>
