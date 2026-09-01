# Lekcja: Zaawansowane Elementy Semantyczne HTML5 w Praktyce - Inf.03

Lepsze pozycjonowanie w wyszukiwarkach (SEO), wyższy poziom dostępności (WCAG) oraz czytelność kodu w dużych zespołach programistycznych zależą od poprawnego doboru znaczników. Semantyka w HTML5 odpowiada na pytanie: **„Czym jest ta treść i jaka jest jej rola?”**, a nie „Jak ma wyglądać?”.

---

## 1. Zbiór Zaawansowanych Znaczników Semantycznych

Poniższe zestawienie przedstawia znaczniki HTML5 dedykowane do konkretnych zastosowań biznesowych:

| Znacznik | Przeznaczenie i rola w aplikacji | Przykład zastosowania |
| :--- | :--- | :--- |
| `<article>` | Niezależny, powtarzalny blok treści gotowy do dystrybucji. | Wpis na blogu, wiadomość w portalu, karta produktu w sklepie. |
| `<section>` | Tematyczna sekcja dokumentu gromadząca powiązane treści. | Sekcja zalet, sekcja opinii, rozdział w dokumentacji. |
| `<aside>` | Treść poboczna, uzupełniająca wątek główny. | Panel boczny, powiązane linki, słowniczek pojęć. |
| `<figure>` + `<figcaption>` | Samodzielny bloki graficzny/kodowy wraz z oficjalnym podpisem. | Zdjęcia w portfolio, wykresy w raporcie, przykłady kodu. |
| `<details>` + `<summary>` | Natywny widget interaktywny typu "rozwiń/zwiń" bez JavaScriptu. | Sekcje FAQ, rozwijane listy wymagań, szczegóły techniczne. |
| `<time>` | Zapis daty/czasu jednoznaczny dla robotów sieciowych (SEO). | Data publikacji wpisu, termin wydarzenia. |
| `<meter>` | Prezentacja wartości w znanym, stałym zakresie. | Poziom naładowania baterii, stan magazynowy, ocena (np. 4.5/5). |
| `<progress>` | Pasek postępu wykonywania danego procesu. | Postęp wgrywania pliku, krok wypełniania formularza. |
| `<kbd>`, `<code>`, `<samp>` | Oznaczenie elementów technicznych, komend i wyników. | Dokumentacja API, instrukcje skrótów klawiszowych. |

---

## 2. Pytania Kontrolne

1. **Kiedy należy zastosować znacznik `<article>`, a kiedy `<section>`?**
2. **Dlaczego podawanie daty w znaczniku `<time datetime="YYYY-MM-DD">` jest lepsze dla SEO niż zwykły sam tekst w `<span>`?**
3. **Czym różni się zastosowanie znacznika `<meter>` od znacznika `<progress>`?**
4. **Dlaczego użycie `<details>` i `<summary>` do tworzenia FAQ jest bardziej korzystne z punktu widzenia dostępności (WCAG) niż skrypt w JavaScript na kontenerach `<div>`?**
5. **Jaka jest relacja pomiędzy znacznikami `<figure>` i `<figcaption>`?**

---

## 3. Szybkie Ćwiczenia Praktyczne

### Ćwiczenie 1: Naprawa struktury opinii klienta
Przebuduj poniższy fragment oparty na niesemantycznych znacznikach `<div>` na strukturę wykorzystującą znaczniki `<figure>`, `<blockquote>` oraz `<figcaption>`:

```html
<!-- Zły kod -->
<div class="review">
  <div class="text">"Świetny kurs, bardzo mi pomógł!"</div>
  <div class="author">Jan Kowalski, Junior Developer</div>
</div>
```

<details>
<summary><b>Rozwiązanie (kliknij, aby rozwinąć)</b></summary>

```html
<figure class="review">
  <blockquote cite="https://example.com/opinie">
    <p>"Świetny kurs, bardzo mi pomógł!"</p>
  </blockquote>
  <figcaption>Jan Kowalski, Junior Developer</figcaption>
</figure>
```
</details>

---

### Ćwiczenie 2: Semantyczna instrukcja skrótu klawiszowego
Stwórz zdanie z instrukcją: *"Aby zapisać plik, naciśnij Ctrl + S w edytorze"*, używając odpowiednich znaczników semantycznych do oznaczenia klawiszy oraz programu.

<details>
<summary><b>Rozwiązanie (kliknij, aby rozwinąć)</b></summary>

```html
<p>
  Aby zapisać plik, naciśnij <kbd>Ctrl</kbd> + <kbd>S</kbd> w edytorze <code class="app-name">VS Code</code>.
</p>
```
</details>

---

### Ćwiczenie 3: Pasek poziomu magazynowego i postępu
Napisz dwa elementy:
1. Pasek stanu magazynowego towaru (dostępne 15 sztuk z 100).
2. Pasek postępu pobierania pliku (pobrano 60%).

<details>
<summary><b>Rozwiązanie (kliknij, aby rozwinąć)</b></summary>

```html
<!-- Stan magazynowy (zakres znany) -->
<label for="stock">Stan magazynowy:</label>
<meter id="stock" value="15" min="0" max="100" low="20" high="80" optimum="90">15 z 100</meter>

<!-- Postęp pobierania (proces w toku) -->
<label for="download">Pobieranie pliku:</label>
<progress id="download" value="60" max="100">60%</progress>
```
</details>

---

## 4. Zaawansowane Zadania Projektowe (Scenariusze Biznesowe)

### Zadanie 1: Portal Informacyjny - Semantyka Strony Głównej i Artykułu
**Opis z życia:**  
Pracujesz jako Frontend Developer w portalu informacyjnym. Zespół SEO zauważył, że roboty Google źle indeksują artykuły, traktując całą stronę jako jeden duży blok tekstu. Twój lider projektu prosi Cię o przygotowanie semantycznego szablonu strony głównej portalu.

**Wymagania:**
* Strona ma posiadać jeden główny kontener treści (`<main>`).
* Sekcja głównych newsów z dnia powinna być zgrupowana w `<section>`.
* Każda wiadomość musi być osobnym elementem `<article>` posiadającym własny nagłówek (`<header>`), stopkę z autorem/datą (`<footer>`) oraz czas publikacji czytelny dla maszyn (`<time datetime="...">`).
* Boczne kalendarium / skrót wiadomości branżowych ma być umieszczony w elemencie `<aside>`.
* Stopka główna portalu ma zawierać dane kontaktowe i prawne (`<footer>`).

---

### Zadanie 2: Platforma E-learningowa - Moduł FAQ i Dostępność
**Opis z życia:**  
Aplikacja e-learningowa, nad którą pracujesz, przechodzi audyt dostępności (WCAG) przed sprzedażą do sektora publicznego. Dotychczasowa sekcja FAQ opierała się na skomplikowanym kodzie JavaScript z masą znaczników `<div>`. Masz zastąpić go rozwiązaniem natywnym w HTML5, które działa bez skryptów i jest w pełni dostępne dla czytników ekranowych.

**Wymagania:**
* Stwórz sekcję FAQ z wykorzystaniem natywnych znaczników interaktywnych `<details>` oraz `<summary>`.
* Umieść w niej co najmniej 3 pytania dotyczące kursu (np. wymagania sprzętowe, czas trwania, certyfikat).
* W odpowiedziach do pytań użyj podświetlenia dla kluczowych pojęć (`<mark>`) oraz osadź fragment przykładowego kodu źródłowego (`<code>`).
* Zadbaj o to, aby pierwsze pytanie z listy było domyślnie rozwijane/otwarte przy ładowaniu strony (atrybut `open`).

---

### Zadanie 3: Dokumentacja Techniczna API - Prezentacja Kodów i Wyników
**Opis z życia:**  
Twoja firma buduje narzędzie dla programistów. Dział Technical Writing przygotował tekst dokumentacji, ale strona wygląda mało czytelnie. Twoim zadaniem jest ustrukturyzowanie fragmentu dokumentacji tak, aby wyraźnie odróżniała pojęcia techniczne, wyniki zwracane przez serwer oraz komendy terminala.

**Wymagania:**
* Zaprojektuj sekcję dokumentacji opisaną wewnątrz elementu `<article>`.
* Wprowadź przykład instrukcji dla użytkownika używając znacznika klawiatury (`<kbd>`) dla skrótów klawiszowych (np. `Ctrl + C`).
* Zaprezentuj przykładową odpowiedź zwracaną przez serwer za pomocą znacznika `<samp>` ujętego w blok tekstu preformatowanego (`<pre>`).
* Wprowadź zmienne systemowe w kodzie za pomocą znacznika `<var>`.

---

### Zadanie 4: Portfolio Fotografa - Grafika i Podpisy pod SEO
**Opis z życia:**  
Znany fotograf zamówił nowoczesną stronę ze swoim portfolio. Kluczowym wymogiem jest bezbłędny układ semantyczny dla wyszukiwarek grafik (Google Images), w którym każde zdjęcie ma przypisany jednoznaczny opis i jest traktowane jako niezależny zasób.

**Wymagania:**
* Przygotuj galerię 3 zdjęć osadzonych w strukturze `<figure>`.
* Każde zdjęcie musi posiadać podłączony znacznik `<figcaption>` stanowiący jego oficjalny tytuł i opis.
* W opisie przynajmniej jednego zdjęcia użyj znacznika `<time>` wskazującego dokładną datę zrobienia fotografii.
* Zgrupuj całą galerię w sekcji tematycznej (`<section>`) i dodaj do niej nagłówek.

---

### Zadanie 5: Sklep Internetowy - Karta Produktu i Pasek Postępu Promocji
**Opis z życia:**  
Podczas wyprzedaży "Flash Sale" w sklepie e-commerce trzeba wygenerować unikalną kartę oferty. Zespół marketingu wymaga pokazania limitu dostępności towaru oraz specyfikacji technicznej w formie tabelarycznej i mierników graficznych.

**Wymagania:**
* Stwórz kartę produktu zamkniętą w kontenerze `<article>`.
* Zastosuj znacznik `<meter>` do pokazania poziomu naładowania baterii/oceny produktu lub stanu magazynowego.
* Zastosuj znacznik `<progress>` do pokazania postępu wyprzedaży (np. "Sprzedano 75% puli promocyjnej").
* Dołącz specyfikację w postaci semantycznej tabeli (`<table>`, `<thead>`, `<tbody>`), zawierającej parametry sprzętu.
