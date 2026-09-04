 Wprowadzenie do CSS

### CSS: Sposoby umieszczenia kodu
Style CSS można dodawać do dokumentu HTML na trzy główne sposoby: jako arkusz zewnętrzny, arkusz wewnętrzny lub w postaci stylów inline (liniowych).

#### 1. Zewnętrzny arkusz stylów
Największą zaletą wykorzystania zewnętrznego arkusza stylów jest możliwość zmiany w jednym miejscu wyglądu danego elementu w całej witrynie. 

Aby wykorzystać zewnętrzny arkusz stylów, należy go dołączyć do sekcji `<head>` każdej podstrony naszej witryny za pomocą znacznika `<link>`:

```html
<head>
   <link rel="stylesheet" type="text/css" href="/css/style.css">
</head>
```

#### 2. Wewnętrzny arkusz stylów
Istnieje również możliwość wprowadzenia stylów bez dodawania osobnego pliku zewnętrznego. Deklaracje umieszcza się bezpośrednio w elemencie `<head>` strony wewnątrz znacznika `<style>`:

```html
<head>
    <style>
        body {
          background: #ff0000;
        }
        h1 {
          color: #00ff00;
          margin: 40px;
          border: 1px solid #0000ff;
        } 
    </style>
</head>
```

#### 3. Style znaczników (inline)
Styl można przypisać bezpośrednio do konkretnego elementu HTML za pomocą atrybutu `style`. Rozwiązanie to ma najwyższą specyficzność, ale jest trudniejsze w utrzymaniu przy większych projektach:

```html
<h1 style="color: #00ff00; margin: 40px; border: 1px solid #0000ff;">Nagłówek 1</h1>
```

### CSS: Selektory
Selektory to wzorce używane do wskazania elementów HTML, do których mają zostać przypisane reguły stylu. Do najpopularniejszych należą selektory elementów (np. `p`, `h1`), selektory klas (np. `.klasa`), selektory identyfikatorów (np. `#identyfikator`), a także selektory atrybutów i potomków.

### CSS: Pseudoklasy
Pseudoklasy definiują specjalny stan elementów HTML. Pozwalają na stylowanie elementów w zależności od interakcji użytkownika lub ich pozycji w drzewie DOM. Przykładem są `:hover` (najechanie kursorem), `:focus` (aktywacja pola formularza) czy `:nth-child()` (wybieranie konkretnych elementów potomnych).

### CSS: Jednostki
W CSS wartości wymiarów i odległości mogą być wyrażane za pomocą jednostek miary. Dzielimy je na:
* **Jednostki względne:** zależne od innych wartości (np. `em`, `rem`, `%`, `vw`, `vh`).
* **Jednostki bezwzględne:** o stałej wielkości niezależnie od ekranu (np. piksele – `px`, centymetry – `cm`).

### CSS: Kolory
Kolory w CSS można definiować na kilka sposobów:
* Za pomocą nazw słownych (np. `red`, `blue`).
* W zapisie szesnastkowym (hex), np. `#ff0000`.
* Za pomocą modeli funkcyjnych `rgb()` / `rgba()` oraz `hsl()` / `hsla()`, które pozwalają określić stopień nasycenia barw oraz przezroczystość (kanał alfa).

### CSS: Elementy pływające
Właściwość `float` (wraz z właściwością `clear`) historycznie służyła do ustawiania elementów obok siebie oraz oblewania tekstu wokół grafik (np. `float: left;` lub `float: right;`). Współcześnie w nowoczesnym layoutcie webowym jej rola została w dużej mierze wyparta przez zaawansowane modele układu, takie jak Flexbox i Grid.

### CSS: Formatowanie tekstu
CSS oferuje szeroki wachlarz właściwości do zarządzania wyglądem tekstu i czcionek, w tym:
* `font-family` – rodzaj kroju pismo.
* `font-size` – wielkość czcionki.
* `font-weight` – grubość czcionki.
* `text-align` – wyrównanie tekstu (`left`, `right`, `center`, `justify`).
* `text-decoration` – dekoracja tekstu (np. `underline`, `none`).
* `line-height` – wysokość wiersza.

### CSS: Responsywny układ strony
Responsywny design (RWD) pozwala na dostosowanie wyglądu i układu strony do różnych rozdzielczości ekranów urządzeń (od smartfonów po komputery stacjonarne). Podstawowym narzędziem w CSS są zapytania o media (*Media Queries*), które pozwalają aplikować różne reguły stylów w zależności od parametrów urządzenia, np.:
```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

---
