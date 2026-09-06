# Lekcja: Kaskadowe Arkusze Stylów (CSS)

**Cel lekcji:** Opanowanie kluczowych zagadnień z zakresu CSS wymaganych na egzaminie zawodowym INF.03 (*Tworzenie i administrowanie stronami i aplikacjami internetowymi oraz bazami danych*).

---

## Moduł 1: Sposoby Dołączania CSS do Dokumentu HTML

Na egzaminie INF.03 kluczowe jest dokładne czytanie treści zadania – arkusz określa, która metoda jest wymagana.

### 1. Zewnętrzny arkusz stylów (Rekomendowane / Najczęstsze)
Arkusz CSS znajduje się w osobnym pliku (np. `styl.css`) dołączanym w sekcji `<head>`.
```html
<link rel="stylesheet" href="styl.css">
```

### 2. Wewnętrzny arkusz stylów
Deklaracja stylów bezpośrednio w sekcji `<head>` pliku HTML.
```html
<style>
  body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
  }
</style>
```

### 3. Styl lokalny (Inline)
Wpisywany bezpośrednio w atrybucie `style` danego znacznika.
```html
<p style="color: red; font-weight: bold;">Tekst wyróżniony</p>
```

---

## Moduł 2: Selektory i Adresowanie Elementów

Precyzyjne stosowanie selektorów pozwala na szybkie nakładanie reguł bez modyfikacji struktury HTML.

* **Selektor znacznika:** Dotyczy wszystkich elementów danego typu.
  ```css
  h1 { color: #2c3e50; }
  ```
* **Selektor klasy (`.`):** Wielokrotnego użytku na stronie.
  ```css
  .wyprojektowany-blok { padding: 15px; }
  ```
* **Selektor identyfikatora (`#`):** Unikalny dla jednego elementu w dokumencie.
  ```css
  #glowny-baner { height: 200px; }
  ```
* **Pseudoklasy stanu (`:hover`, `:active`, `:visited`):**
  ```css
  a:hover {
    color: #e74c3c;
    text-decoration: underline;
  }
  ```
* **Pseudoelementy (`::first-letter`, `::first-line`):**
  ```css
  p::first-letter {
    font-size: 150%;
    font-weight: bold;
  }
  ```

---

## Moduł 3: Typografia i Formatowanie Tekstu

Wymagania arkusza egzaminacyjnego dotyczące tekstu są zawsze precyzyjnie określone (kolory w HEX/RGB, wymiary w px/%/em).

```css
p {
  font-family: Arial, sans-serif; /* Rodzina czcionek z krokiem zapasowym */
  font-size: 14px;                 /* Rozmiar czcionki */
  font-weight: bold;              /* Grubość: normal, bold, 100-900 */
  font-style: italic;             /* Styl: normal, italic */
  color: #333333;                 /* Kolor tekstu */
  text-align: center;             /* Wyrównanie: left, right, center, justify */
  text-decoration: none;          /* Ozdobienie: none, underline, line-through */
  line-height: 1.5;               /* Wysokość linii (interlinia) */
  letter-spacing: 1px;            /* Odstęp między literami */
}
```

---

## Moduł 4: Model Pudełkowy (Box Model)

Model pudełkowy określa rozkład przestrzeni wokół każdego elementu blokowego w HTML.

```
+-----------------------------------+
|              MARGIN               | (Margines zewnętrzny)
|  +-----------------------------+  |
|  |           BORDER            |  | (Obramowanie)
|  |  +-----------------------+  |  |
|  |  |        PADDING        |  |  | (Margines wewnętrzny)
|  |  |  +-----------------+  |  |  |
|  |  |  |     CONTENT     |  |  |  | (Zawartość/Treść)
|  |  |  +-----------------+  |  |  |
|  |  +-----------------------+  |  |
|  +-----------------------------+  |
+-----------------------------------+
```

### Kod przykładowy:
```css
.pudelko {
  width: 300px;
  height: 150px;
  padding: 20px;            /* Wewnątrz ramki */
  border: 2px solid #000;   /* Szerokość, styl, kolor */
  margin: 15px auto;        /* Zewnątrz ramki (auto wyśrodkowuje w poziomie) */
  box-sizing: border-box;   /* Uwzględnia padding i border w szerokości całkowitej */
}
```

> **Skrócona składnia padding/margin:**
> * `margin: 10px;` – góra, prawo, dół, lewo (wszystkie jednakowe)
> * `margin: 10px 20px;` – [góra/dół] [lewo/prawo]
> * `margin: 10px 20px 15px 5px;` – [góra] [prawo] [dół] [lewo] (ruch wskazówek zegara)

---

## Moduł 5: Układy Stron i Flexbox

Elastyczny układ **Flexbox** jest nowoczesnym standardem stosowanym na egzaminie do budowy układów dwu- i wielokolumnowych.

### 1. Podstawowa konfiguracja kontenera:
```css
.kontener-flex {
  display: flex;
  flex-direction: row;            /* Kierunek osi: row (poziomo), column (pionowo) */
  justify-content: space-between; /* Wyrównanie w osi głównej */
  align-items: center;            /* Wyrównanie w osi poprzecznej (pionowo przy row) */
  flex-wrap: wrap;                 /* Zawijanie elementów do nowej linii */
}
```

### 2. Wartości `justify-content` (Oś główna):
* `flex-start` – wyrównanie do początku
* `flex-end` – wyrównanie do końca
* `center` – wyśrodkowanie
* `space-between` – maksymalny odstęp między elementami, skrajne przy krawędziach
* `space-around` – równe odstępy wokół każdego elementu

### 3. Schemat Egzaminacyjny: Układ 2-kolumnowy (Blok lewy i prawy)

**HTML:**
```html
<main class="uklad-strony">
  <section id="blok-lewy">Sekcja lewa (30%)</section>
  <section id="blok-prawy">Sekcja prawa (70%)</section>
</main>
```

**CSS:**
```css
.uklad-strony {
  display: flex;
  justify-content: space-between;
}

#blok-lewy {
  width: 30%;
  background-color: #e0e0e0;
}

#blok-prawy {
  width: 70%;
  background-color: #ffffff;
}
```

### 4. Wyśrodkowanie w pionie i poziomie (Częste zadanie w banerze)
```css
.baner {
  display: flex;
  justify-content: center; /* Środek w poziomie */
  align-items: center;     /* Środek w pionie */
  height: 200px;
}
```

---

## Moduł 6: Wymagania Specjalne Arkuszy Egzaminacyjnych INF.03

### Stylizacja Tabel
```css
table {
  width: 100%;
  border-collapse: collapse; /* Scalanie krawędzi komórek */
}

th, td {
  border: 1px solid #cccccc;
  padding: 8px;
  text-align: left;
}

/* Naprzemienne kolory wierszy (Zebra) */
tr:nth-child(even) {
  background-color: #f2f2f2;
}

tr:hover {
  background-color: #e6f7ff;
}
```

### Stylizacja Formularzy
```css
input[type="text"], input[type="number"], select {
  width: 100%;
  padding: 8px;
  margin: 5px 0 15px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button, input[type="submit"] {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
}

button:hover, input[type="submit"]:hover {
  background-color: #45a049;
}
```

---

## Zadanie Praktyczne Utrwalające

Napisz kod CSS dla układu zawierającego:
1. Baner o wysokości `150px`, tło `#2c3e50`, tekst biały, wyśrodkowany w pionie i poziomie.
2. Główny kontener o układzie Flexbox z dwoma blokami:
   * Blok lewy: szerokość `25%`, tło `#ecf0f1`, padding `10px`.
   * Blok prawy: szerokość `75%`, tło `#ffffff`, padding `10px`.
3. Stopkę z tłem `#34495e`, tekstem wyrównanym do środka i paddingiem `15px`.

### Rozwiązanie:
```css
/* Baner */
header {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 150px;
  background-color: #2c3e50;
  color: #ffffff;
}

/* Układ główny */
main {
  display: flex;
}

#blok-lewy {
  width: 25%;
  background-color: #ecf0f1;
  padding: 10px;
}

#blok-prawy {
  width: 75%;
  background-color: #ffffff;
  padding: 10px;
}

/* Stopka */
footer {
  background-color: #34495e;
  color: #ffffff;
  text-align: center;
  padding: 15px;
}
```
