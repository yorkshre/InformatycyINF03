# Wprowadzenie do HTML i CSS

## Definicja HTML i CSS

### **HTML (HyperText Markup Language)**
Język znaczników wykorzystywany do tworzenia stron internetowych. HTML służy do definiowania struktury i zawartości strony, takiej jak nagłówki, akapity, obrazy oraz odnośniki (linki). Znaczniki HTML są umieszczane w kodzie źródłowym dokumentu, co pozwala przeglądarkom internetowym na interpretowanie i wyświetlanie zawartości w sposób zrozumiały dla użytkowników.

> **Ciekawostka:** *Pierwsze przeglądarki internetowe (w latach 1991–1992) wyświetlały wyłącznie prosty, sformatowany tekst z podstawowymi odnośnikami, bez skomplikowanych układów graficznych czy stylów.*

### **CSS (Cascading Style Sheets)**
Kaskadowe Arkusze Stylów to język arkuszy stylów wykorzystywany do definiowania wyglądu i układu elementów na stronie internetowej. CSS pozwala na określenie koloru, czcionki, marginesów, obramowań oraz wielu innych właściwości wizualnych dla elementów strukturalnych HTML.

---

## Historia powstania HTML i CSS

Historia HTML i CSS jest długa i niezwykle ciekawa. 

### Rozwój języka HTML
* **1989 rok** – HTML powstał jako prosty język znaczników do oznaczania dokumentów tekstowych.
* **1993 rok** – Ogłoszono pierwszą oficjalną specyfikację HTML. W kolejnych latach powstawały nowe wersje, w których dodawano nowe tagi oraz usprawnienia funkcjonalne.
* **2014 rok (HTML5)** – Wprowadzenie standardu HTML5, który przyniósł rewolucję w tworzeniu nowoczesnych aplikacji internetowych.

#### **Najważniejsze nowości w HTML5:**
1. **Semantyczne znaczniki:** Wprowadzono znaczniki takie jak `<header>`, `<nav>`, `<section>`, `<article>`, `<aside>` oraz `<footer>`. Ułatwiają one opisywanie struktury dokumentu i jego zrozumienie przez przeglądarki oraz roboty indeksujące wyszukiwarek (SEO).
2. **Wsparcie dla multimediów:** Natywne wsparcie dla elementów wideo (`<video>`) i audio (`<audio>`) bez potrzeby stosowania zewnętrznych wtyczek (np. Adobe Flash).
3. **Nowe atrybuty formularzy:** Wprowadzenie atrybutów ułatwiających walidację i wypełnianie formularzy, np. `placeholder`, `autocomplete`, `required`.
4. **Grafika wektorowa:** Możliwość bezpośredniego osadzania grafiki wektorowej (SVG) oraz rysowania za pomocą elementu `<canvas>`.
5. **Nowe API i funkcjonalności:** Wprowadzenie geolokalizacji, Web Storage (Local Storage / Session Storage) i innych interfejsów do tworzenia dynamicznych aplikacji.
6. **Responsywność (Responsive Web Design):** Funkcjonalności wspomagające dostosowywanie stron do różnych ekranów i urządzeń mobilnych.

### Rozwój języka CSS
* **1996 rok** – Powstanie CSS jako języka do opisu prezentacji dokumentów HTML. Umożliwiło to rozdzielenie warstwy zawartości (HTML) od warstwy prezentacji (CSS).
* **CSS3** – Najnowszy etap rozwoju, który przyniósł znaczne usprawnienia, takie jak transformacje 2D/3D, gradienty, cienie, zaokrąglone rogi, animacje oraz przejścia (*transitions*).

> **Uwaga:** CSS3 nie stanowi jednej monolitycznej wersji, lecz zbiór niezależnie rozwijanych i publikowanych modułów.

---

## Przegląd wersji HTML i CSS

### **Wersje HTML**

| Wersja HTML | Rok wydania | Najważniejsze nowości |
| :--- | :---: | :--- |
| **HTML 2.0** | 1995 | Wsparcie dla tabel i formularzy |
| **HTML 3.2** | 1997 | Pierwsze oficjalne wsparcie dla arkuszy stylów |
| **HTML 4.01** | 1999 | Wsparcie dla warstw (CSS) oraz ramek (*frames*) |
| **XHTML 1.0** | 2000 | Strict rozszerzenie HTML oparte na ścisłej składni XML |
| **HTML5** | 2014 | Wbudowane multimedia, znaczniki semantyczne, nowe API |

---

### **Wersje CSS**

| Wersja CSS | Rok wydania | Najważniejsze nowości |
| :--- | :---: | :--- |
| **CSS 1** | 1996 | Pierwsza specyfikacja, wprowadzenie kaskadowości i podstawowych stylów |
| **CSS 2** | 1998 | Wprowadzenie pozycjonowania elementów, mediów dla druku, lepsza kontrola tekstu |
| **CSS 2.1** | 2004 | Udoskonalenie CSS 2, standaryzacja i poprawki błędów |
| **CSS 3** | 1999–2012+ | Podział na moduły, selektory CSS3, Media Queries, cienie, gradienty, animacje |

---

## Zastosowanie i współpraca HTML i CSS

HTML i CSS są kluczowymi technologiami stanowiącymi fundament sieci Web. Bez nich strony internetowe byłyby jedynie zbiorami nieuporządkowanych danych tekstowych.

### **Podstawowe pojęcia**

* **W HTML:**
  * **Znaczniki (tagi)** – elementy oznaczające strukturę (np. `<h1>`, `<p>`, `<a>`).
  * **Atrybuty i wartości** – dodatkowe właściwości elementów (np. `href="..."`, `src="..."`, `class="..."`).
  * **Struktura dokumentu** – hierarchiczne ułożenie elementów na stronie.

* **W CSS:**
  * **Selektory** – wskazują, które elementy HTML mają zostać ostylowane (np. `p`, `.klasa`, `#id`).
  * **Właściwości** – cechy wyglądu, które zmieniamy (np. `color`, `font-size`, `margin`).
  * **Wartości** – konkretne ustawienia właściwości (np. `red`, `16px`, `10px auto`).

---

### **Sposoby dołączania CSS do HTML**

CSS można powiązać z kodem HTML na trzy sposoby:

1. **Zewnętrzny plik CSS (zalecane):** Podłączenie pliku `.css` w sekcji `<head>` za pomocą znacznika `<link>`:
   ```html
   <link rel="stylesheet" href="style.css">
