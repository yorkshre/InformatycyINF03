# Przewodnik po CSS Flexbox: Od podstaw do praktyki

Flexbox (Flexible Box Layout) to jeden z najważniejszych i najbardziej użytecznych modułów w CSS. Został zaprojektowany jako jednowymiarowy model tworzenia układów elementów oraz skuteczna metoda dystrybucji przestrzeni i wyrównywania obiektów w interfejsie. Dzięki niemu z łatwością zaprojektujesz elastyczne i responsywne layouty, rezygnując ze starszych, przestarzałych metod opartych na `float` czy `position`.

---

## 1. Jak zacząć? Definiowanie kontenera

Aby skorzystać z Flexboxa, musisz zdefiniować element nadrzędny, który stanie się **kontenerem flex**, opakowującym elementy potomne (dzieci):

```html
<div class="container"> 
  <div>1</div> 
  <div>2</div> 
  <div>3</div> 
</div>
```

Kontener staje się elastyczny dzięki ustawieniu właściwości `display` na wartość `flex`:

```css
.container { 
  display: flex; 
  background-color: #ff7675; 
} 
.container div { 
  background-color: #f1f1f1; 
  margin: 10px; 
  padding: 20px; 
  font-size: 30px; 
}
```

Po ustawieniu `display: flex;` elementy potomne automatycznie układają się w elastyczny wiersz. Możesz teraz zarządzać ich pozycją za pomocą właściwości kontenera i dzieci.

---

## 2. Właściwości kontenera (rodzica)

### Kierunek układu: `flex-direction`
Określa, w jakim kierunku ustawiają się elementy potomne.
* `row` – poziomo od lewej do prawej (domyślnie).
* `row-reverse` – poziomo od prawej do lewej.
* `column` – pionowo od góry do dołu.
* `column-reverse` – pionowo od dołu do góry.

```css
.container {
  display: flex;
  flex-direction: column; /* Układa elementy w kolumnie */
}
```

### Zawijanie elementów: `flex-wrap`
Decyduje, czy elementy mają próbować zmieścić się w jednej linii, czy zawijać do kolejnej, gdy zabraknie miejsca.
* `nowrap` – elementy nie są zawijane (domyślnie, mogą się zmniejszać).
* `wrap` – elementy zawijają się do następnej linii, gdy brakuje miejsca.
* `wrap-reverse` – elementy zawijają się, ale w kierunku przeciwnym.

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

### Wyrównanie wzdłuż osi głównej: `justify-content`
Odpowiada za pozycjonowanie elementów wzdłuż osi głównej (poziomo, jeśli kierunkiem jest `row`).
* `flex-start` – wyrównanie do początku osi.
* `flex-end` – wyrównanie do końca osi.
* `center` – wyśrodkowanie elementów.
* `space-between` – równomierne rozłożenie; pierwszy element dotyka początku, ostatni końca, a wolna przestrzeń dzielona jest *pomiędzy* nimi.
* `space-around` – równomierne rozłożenie z równego rozmiaru odstępami wokół każdego elementu.
* `space-evenly` – idealnie równe odstępy między wszystkimi elementami oraz od krawędzi kontenera.

### Wyrównanie wzdłuż osi poprzecznej: `align-items`
Odpowiada za pozycjonowanie elementów wzdłuż osi poprzecznej (pionowo przy `row`). Posiada analogiczne wartości do `justify-content`, a także dodatkowe:
* `stretch` – elementy rozciągają się na całą wysokość kontenera (domyślnie).
* `flex-start` / `flex-end` / `center` / `baseline`.

---

## 3. Właściwości elementów potomnych (dzieci)

Zanim przejdziesz do zadań, poznaj kluczową trójcę właściwości odpowiedzialnych za to, jak elementy dzielą wolne miejsce:

* **`flex-basis`**: Określa bazowy (początkowy) rozmiar elementu przed rozdysponowaniem wolnego miejsca.
* **`flex-grow`**: Określa, jak bardzo element może **urosnąć** względem innych dzieci, jeśli w kontenerze jest wolna przestrzeń (np. `1` pozwala rosnąć, `0` blokuje wzrost).
* **`flex-shrink`**: Określa, jak bardzo element może się **zmniejszyć**, gdy brakuje miejsca w kontenerze (domyślnie `1`).
* **`order`**: Zmienia domyślną kolejność wyświetlania elementów (im mniejsza liczba, tym wcześniej element się pojawia).
* **`align-self`**: Pozwala nadpisać globalne `align-items` dla konkretnego, pojedynczego elementu potomnego.

---
## 4 Jak Flexbox wspiera responsywność? (Kluczowe informacje)

Flexbox został zaprojektowany z myślą o urządzeniach różnej wielkości. Aby Twoje projekty były w pełni responsywne, warto pamiętać o kilku mechanizmach:

* **Automatyczne dopasowanie i elastyczność (`flex-grow`, `flex-shrink`)**: Zamiast podawać sztywne szerokości w pikselach (`width: 300px`), elementy mogą automatycznie rozszerzać się lub kurczyć w zależności od dostępnego miejsca w oknie przeglądarki[cite: 1].  
* **Zawijanie elementów (`flex-wrap: wrap`)**: Domyślnie Flexbox próbuje zmieścić wszystko w jednej linii, co na małych ekranach telefonów mogłoby zniszczyć układ. Użycie `flex-wrap: wrap` sprawia, że elementy automatycznie wskakują do kolejnego wiersza, gdy zabraknie miejsca[cite: 1].  
* **Kombinacja z zapytaniami o media (`@media queries`)**: Flexbox ułatwia zmianę kierunku układu (np. z poziomego `row` na pionowy `column`) za pomocą jednego zapytania w CSS, co idealnie sprawdza się przy przechodzeniu z widoku desktopowego na mobilny[cite: 1].
## 5. Ćwiczenia z rozwiązaniami

### Ćwiczenie 1: Paski nawigacji (menu rozłożone na boki)
**Zadanie:** Stwórz pasek nawigacji, w którym logo znajduje się po lewej stronie, a linki menu po prawej.

**Rozwiązanie:**
```html
<nav class="navbar">
  <div class="logo">Logo</div>
  <ul class="menu">
    <li>Start</li>
    <li>O nas</li>
    <li>Kontakt</li>
  </ul>
</nav>
```
```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #333;
  color: white;
}
.menu {
  display: flex;
  gap: 20px;
  list-style: none;
}
```

### Ćwiczenie 2: Wycentrowanie elementu na środku ekranu
**Zadanie:** Umieść kwadrat o wymiarach 200x200 px dokładnie na środku pełnego ekranu (zarówno w pionie, jak i w poziomie).

**Rozwiązanie:**
```html
<div class="screen">
  <div class="box">Środek</div>
</div>
```
```css
.screen {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f4f4f4;
}
.box {
  width: 200px;
  height: 200px;
  background-color: #3498db;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
```

---

## 5. Zadania do samodzielnego wykonania (7 zadań)

Wykonaj poniższe zadania w edytorze kodu, łącząc plik HTML z arkuszem stylów CSS.

### Zadanie 1: Układ pionowy
* **Treść:** Stwórz kontener flex, który ułoży trzy elementy w kolumnie (jeden pod drugim) od góry do dołu. Użyj właściwości `flex-direction`.

### Zadanie 2: Zawijanie elementów
* **Treść:** Przygotuj kontener zawierający 8 małych kwadratów. Ustaw właściwość `flex-wrap` tak, aby elementy automatycznie przenosiły się do nowej linii, gdy zabraknie szerokości w kontenerze.

### Zadanie 3: Rozmieszczenie z odstępami (`space-between`)
* **Treść:** Umieść 3 karty produktów w kontenerze flex. Użyj odpowiedniej właściwości, aby rozmieścić je w poziomie z równymi odstępami pomiędzy nimi, tak aby pierwszy i ostatni element dotykały krawędzi kontenera.

### Zadanie 4: Wyrównanie do prawego dolnego rogu
* **Treść:** W kontenerze flex o wysokości 400px umieść przycisk i wyrównaj go tak, aby znajdował się w **prawym dolnym rogu** kontenera (skorzystaj z `justify-content` oraz `align-items`).

### Zadanie 5: Zmiana kolejności (`order`)
* **Treść:** Stwórz 4 ponumerowane elementy (`1`, `2`, `3`, `4`). Używając właściwości `order` na wybranym elemencie, spraw, aby element z numerem `3` wyświetlał się jako pierwszy na ekranie.

### Zadanie 6: Elastyczne powiększanie (`flex-grow`)
* **Treść:** Stwórz kontener z trzema elementami potomnymi (lewy, środkowy, prawy). Nadaj skrajnym elementom stałą szerokość (np. `150px`), a środkowemu ustaw `flex-grow: 1`, aby zajął całą dostępną wolną przestrzeń w wierszu.

### Zadanie 7: Niezależne wyrównanie (`align-self`)
* **Treść:** W kontenerze flex o wysokości 250px umieść trzy elementy o różnej wysokości. Użyj właściwości `align-self` na drugim elemencie tak, aby wyrównał się on do **dolnej krawędzi** kontenera, podczas gdy pozostałe dwa pozostały na górze.
