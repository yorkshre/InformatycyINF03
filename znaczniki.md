# Kompendium Znaczników HTML
**Ściąga dla Technika Informatyka/Programisty (INF.03)**

---

## 1. Podstawowe znaczniki strukturalne

Służą do budowy szkieletu dokumentu HTML oraz zdefiniowania podstawowych elementów tekstu.

| Znacznik | Opis |
| :--- | :--- |
| `<!DOCTYPE>` | Deklaracja typu dokumentu (w HTML5: `<!DOCTYPE html>`). |
| `<html>` | Główny element korzenny (*root*) zawierający cały dokument HTML. |
| `<head>` | Nagłówek dokumentu – zawiera metadane, tytuł oraz odnośniki do zasobów. |
| `<title>` | Tytuł dokumentu wyświetlany na karcie przeglądarki. |
| `<body>` | Ciało dokumentu – zawiera całą widoczną treść strony. |
| `<h1>` do `<h6>` | Nagłówki tekstu hierarchiczne (od najważniejszego `<h1>` do najmniej ważnego `<h6>`). |
| `<p>` | Akapit (paragraf) tekstu. |
| `<br>` | Wymuszenie złamania linii (przejście do nowej linii). |
| `<hr>` | Pozioma linia podziału (tematyczny podział sekcji). |
| `<!-- ... -->` | Komentarz w kodzie (niewidoczny dla użytkownika). |

---

## 2. Formatowanie i semantyka tekstu

Znaczniki pozwalające nadawać znaczenie semantyczne oraz stylizować fragmenty tekstu.

| Znacznik | Opis |
| :--- | :--- |
| `<abbr>` | Skrót lub akronim (z atrybutem `title` wyświetla pełne rozwinięcie). |
| `<address>` | Dane kontaktowe do autora lub właściciela dokumentu. |
| `<b>` | Pogrubienie tekstu (wizualne, bez znaczenia semantycznego). |
| `<strong>` | Wyróżnienie tekstu o dużym znaczeniu (semantyczne pogrubienie). |
| `<i>` | Tekst pochylony (np. pojęcia techniczne, zwroty w innym języku). |
| `<em>` | Uwypuklenie / akcentowanie tekstu (semantyczna inskrypcja). |
| `<small>` | Tekst pomniejszony (np. zastrzeżenia prawne, prawne stopki). |
| `<mark>` | Zakreślenie / wyróżnienie tekstu tłem. |
| `<code>` | Wstawka kodu źródłowego (czcionka monotypowa). |
| `<pre>` | Tekst preformatowany (zachowuje spacje, tabulatory i znaki nowej linii). |
| `<kbd>` | Oznaczenie tekstu wprowadzanego przez użytkownika z klawiatury (np. skróty klawiszowe). |
| `<samp>` | Przykładowy wynik wyjściowy z programu komputerowego. |
| `<var>` | Zmienna w matematyce lub programowaniu. |
| `<sub>` | Indeks dolny (np. w wzorach chemicznych $H_2O$). |
| `<sup>` | Indeks górny (np. w potęgach $m^2$). |
| `<del>` | Tekst usunięty / nieaktualny (najczęściej przekreślony). |
| `<ins>` | Tekst dodany do dokumentu (często podkreślony). |
| `<s>` | Tekst, który przekroczył ważność lub nie jest już poprawny. |
| `<u>` | Podkreślenie tekstu wyróżniającego się od reszty. |
| `<blockquote>` | Dłuższy cytat blokowy z innego źródła. |
| `<cite>` | Tytuł cytowanej pracy, książki lub artykułu. |
| `<dfn>` | Definiowane pojęcie. |
| `<bdi>` | Izolacja kierunku tekstu (przydatne przy łączeniu języków LTR i RTL). |
| `<bdo>` | Nadpisanie bieżącego kierunku tekstu (np. `<bdo dir="rtl">`). |
| `<meter>` | Pasek pomiarowy w znanym przedziale (np. zużycie dysku). |
| `<progress>` | Pasek postępu wykonywanego zadania. |
| `<time>` | Określenie daty lub godziny w formacie czytelnym dla maszyn. |
| `<template>` | Szablon HTML ukryty podczas renderowania, używany przez JavaScript. |
| `<wbr>` | Sugestia miejsca złamania długiego słowa przy krawędzi ekranu. |

---

## 3. Formularze i interakcja z użytkownikiem

Elementy służące do zbierania danych od użytkowników.

| Znacznik | Opis |
| :--- | :--- |
| `<form>` | Kontener definiujący formularz HTML. |
| `<input>` | Uniwersalne pole wprowadzania danych (zależne od atrybutu `type`). |
| `<textarea>` | Wielowierszowe pole tekstowe. |
| `<button>` | Klikalny przycisk. |
| `<select>` | Lista rozwijana (*dropdown*). |
| `<optgroup>` | Grupowanie powiązanych opcji na liście rozwijanej. |
| `<option>` | Pojedyncza opcja wewnątrz `<select>` lub `<datalist>`. |
| `<label>` | Etykieta powiązana z polem formularza (poprawia dostępność). |
| `<fieldset>` | Grupowanie powiązanych pól w formularzu w jedną ramkę. |
| `<legend>` | Tytuł / podpis grupy pól `<fieldset>`. |
| `<datalist>` | Lista podpowiedzi dla pola `<input>` (autouzupełnianie). |
| `<output>` | Wynik obliczeń wykonywanych na formularzu (np. przez JS). |

---

## 4. Obrazy i grafika

Znaczniki używane do osadzania oraz obsługi zasobów graficznych.

| Znacznik | Opis |
| :--- | :--- |
| `<img>` | Osadzenie obrazu w dokumencie. |
| `<picture>` | Kontener wielorazowych źródeł obrazów (dla ułatwienia RWD). |
| `<figure>` | Samodzielny blok treści (obraz, wykres, kod) z opcjonalnym podpisem. |
| `<figcaption>` | Podpis / opis do elementu `<figure>`. |
| `<svg>` | Kontener na wektorowe grafiki dwuwymiarowe SVG. |
| `<canvas>` | Płótno renderowane dynamicznie za pomocą skryptów JavaScript. |
| `<map>` | Mapa odsyłaczy wewnątrz obrazu graficznego. |
| `<area>` | Klikalny obszar na mapie obrazu `<map>`. |

---

## 5. Media (Audio i Wideo)

Służą do odtwarzania nagrań dźwiękowych oraz materiałów wideo.

| Znacznik | Opis |
| :--- | :--- |
| `<audio>` | Odtwarzacz plików dźwiękowych. |
| `<video>` | Odtwarzacz materiałów wideo. |
| `<source>` | Wskazanie ścieżki i formatu pliku dla multimediów (`<audio>`, `<video>`, `<picture>`). |
| `<track>` | Ścieżka tekstowa (np. napisy, audiodeskrypcja) dla mediów. |

---

## 6. Odnośniki i nawigacja

| Znacznik | Opis |
| :--- | :--- |
| `<a>` | Hiperłącze (odnośnik do innej strony, pliku lub sekcji). |
| `<link>` | Połączenie z zewnętrznymi zasobami (np. arkusz CSS, favicon). |
| `<nav>` | Sekcja nawigacyjna zawierająca menu odnośników. |

---

## 7. Listy

Służą do prezentacji danych w formie wypunktowanej lub numerowanej.

| Znacznik | Opis |
| :--- | :--- |
| `<ul>` | Lista nieuporządkowana (punktowana). |
| `<ol>` | Lista uporządkowana (numerowana). |
| `<li>` | Pojedynczy element listy (`<ul>` lub `<ol>`). |
| `<dl>` | Lista definicji / opisowa. |
| `<dt>` | Termin / pojęcie na liście definicji. |
| `<dd>` | Opis / wyjaśnienie pojęcia z `<dt>`. |

---

## 8. Tabele

Elementy do reprezentacji danych w strukturze wierszy i kolumn.

| Znacznik | Opis |
| :--- | :--- |
| `<table>` | Kontener definiujący tabelę. |
| `<caption>` | Tytuł / nagłówek tabeli. |
| `<thead>` | Sekcja nagłówkowa tabeli. |
| `<tbody>` | Główna sekcja z danymi tabeli. |
| `<tfoot>` | Sekcja stopki tabeli (np. podsumowanie). |
| `<tr>` | Wiersz tabeli. |
| `<th>` | Komórka nagłówkowa (tekst pogrubiony, wyśrodkowany). |
| `<td>` | Standardowa komórka danych. |
| `<colgroup>` | Grupuje strukturalnie kolumny w celu ich wspólnego stylizowania. |
| `<col>` | Definiuje właściwości dla pojedynczej kolumny w `<colgroup>`. |

---

## 9. Layout, sekcje i struktura (Semantyka HTML5)

Znaczniki grupujące i dzielące układ strony na czytelne bloki.

| Znacznik | Opis |
| :--- | :--- |
| `<div>` | Uniwersalny kontener blokowy (brak własnego znaczenia semantycznego). |
| `<span>` | Uniwersalny kontener liniowy (*inline*). |
| `<header>` | Nagłówek witryny lub sekcji. |
| `<main>` | Główna, unikalna zawartość strony. |
| `<section>` | Wyodrębniona sekcja tematyczna dokumentu. |
| `<article>` | Samodzielna, niezależna treść (np. artykuł, post). |
| `<aside>` | Treść poboczna (np. panel boczny, reklama). |
| `<footer>` | Stopka strony lub sekcji. |
| `<details>` | Interaktywny rozwijany kontener treści. |
| `<summary>` | Tytuł/nagłówek rozwijanego elementu `<details>`. |
| `<dialog>` | Okno dialogowe / modalne. |
| `<style>` | Wewnętrzne reguły i style CSS. |

---

## 10. Metadane i konfiguracja strony

| Znacznik | Opis |
| :--- | :--- |
| `<head>` | Sekcja konfiguracji i metadanych. |
| `<meta>` | Metadane strony (kodowanie znaków, opis, autor, viewport dla RWD). |
| `<base>` | Adres bazowy dla wszystkich względnych ścieżek na stronie. |

---

## 11. Ramki i osadzanie elementów zewnętrznych

| Znacznik | Opis |
| :--- | :--- |
| `<iframe>` | Osadzona ramka zewnętrznej strony www. |
| `<script>` | Skrypt wykonywalny (np. JavaScript). |
| `<noscript>` | Treść alternatywna wyświetlana, gdy przeglądarka ma wyłączony JS. |
| `<embed>` | Osadzenie zewnętrznego zasobu (np. aplikacji zewnętrznej, wtyczki). |
| `<object>` | Osadzenie zasobu zewnętrznego (obraz, wideo, dokument PDF). |
| `<param>` | Parametry przekazywane do obiektu `<object>`. |
