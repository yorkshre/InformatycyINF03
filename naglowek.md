# Lekcja: Nagłówek strony – sekcja `<head>` w HTML

Sekcja `<head>` jest kluczowym elementem każdego dokumentu HTML. Działa jak „mózg” strony internetowej – zawiera metadane, czyli informacje o dokumencie, które opisują jego właściwości, sterują zachowaniem w przeglądarce i pomagają robotom indeksującym (SEO).

Z wyjątkiem tytułu widocznego na karcie przeglądarki, treści zawarte w sekcji `<head>` nie są bezpośrednio renderowane w oknie strony.

---

## 1. Główni mieszkańcy sekcji `<head>`

Poniżej znajduje się zestawienie podstawowych znaczników umieszczanych wewnątrz `<head>`:

| Znacznik | Rola / Przeznaczenie |
| :--- | :--- |
| `<title>` | Wymagany tytuł dokumentu (widoczny na karcie przeglądarki i w wynikach Google). |
| `<meta>` | Metadane strony (kodowanie znaków, opis dla wyszukiwarek, ustawienia RWD). |
| `<link>` | Łączenie dokumentu z zewnętrznymi zasobami (np. plikami CSS, ikonami favicon). |
| `<style>` | Wewnętrzny arkusz stylów CSS. |
| `<script>` | Skrypty wykonywalne (np. w języku JavaScript). |
| `<base>` | Bazowy adres URL dla wszystkich relatywnych odnośników na stronie. |

---

## 2. Szczegółowe omówienie elementów

### A. Tytuł strony - `<title>`
Jest to element obligatoryjny według standardu W3C. Tekst zawarty w tym znaczniku jest wykorzystywany w trzech kluczowych miejscach:
1. Na karcie (zakładce) w przeglądarce internetowej.
2. Jako nagłówek wyniku wyszukiwania w wyszukiwarkach (np. Google).
3. Jako domyślna nazwa zakładki po dodaniu strony do ulubionych.

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <title>Kurs HTML – Sekcja Head</title>
</head>
<body>
    <p>Zawartość witryny...</p>
</body>
</html>
```

### B. Znaczniki metadanych – `<meta>`
Znaczniki `<meta>` są elementami samozamykającymi się (nie wymagają znacznika zamykającego `</meta>`).

1. **Kodowanie znaków:**
   ```html
   <meta charset="UTF-8">
   ```
   *Wskazówka:* Zawsze umieszczaj ten znacznik na samym początku `<head>`, aby uniknąć błędów w wyświetlaniu polskich znaków (`ą, ę, ś, ć...`).

2. **Skalowanie na urządzeniach mobilnych (Viewport):**
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
   Niezbędny element dla stron responsywnych (RWD). Dopasowuje szerokość strony do ekranu smartfona lub tabletu.

3. **SEO i opis strony:**
   ```html
   <meta name="description" content="Profesjonalny kurs HTML i CSS od podstaw. Naucz się tworzyć responsywne strony WWW.">
   <meta name="keywords" content="kurs html, css, nauka programowania, webdev">
   <meta name="author" content="szkoleniowcy tinf.pl">
   ```

4. **Automatyczne odświeżenie strony (np. po 5 sekundach):**
   ```html
   <meta http-equiv="refresh" content="5">
   ```

---

### C. Style CSS i dołączanie zewnętrznych plików

1. **Dołączenie zewnętrznego arkusza stylów - `<link>`:**
   To rekomendowana i najpopularniejsza metoda dodawania stylów CSS do strony.
   ```html
   <link rel="stylesheet" href="/css/style.css">
   ```

2. **Wewnętrzne style CSS - `<style>`:**
   Używane głównie przy mniejszych projektach lub w celach testowych.
   ```html
   <style>
       body {
           font-family: Arial, sans-serif;
           background-color: #f4f4f4;
           margin: 0;
       }
       .news {
           background-color: #ff0000;
           color: #ffffff;
           padding: 10px;
       }
       #newest {
           border: 2px dashed #ffd700;
       }
   </style>
   ```

---

### D. Skrypty JavaScript - `<script>`
Znacznik ten służy do wstawiania kodu JavaScript bezpośrednio w dokumencie lub podłączania zewnętrznych plików `.js`.

```html
<!-- Skrypt wewnętrzny -->
<script>
    function mojaFunkcja() {
        document.getElementById("demo").innerHTML = "Cześć JavaScript!";
    }
</script>

<!-- Skrypt zewnętrzny (zalecana praktyka) -->
<script src="app.js" defer></script>
```

---

### E. Adres bazowy - `<base>`
Określa domyślny adres URL oraz domyślny cel (`target`) dla wszystkich linków relatywnych znajdujących się w dokumencie. W dokumencie może wystąpić tylko **jeden** znacznik `<base>`.

```html
<head>
    <base href="https://www.tinf.pl/" target="_blank">
</head>
<body>
    <!-- Ten link otworzy się jako https://www.tinf.pl/kursy/html pod podaną domeną -->
    <a href="kursy/html">Przejdź do kursu HTML</a>
</body>
```

---

## 3. Pytania kontrolne

1. **Dlaczego znacznik `<meta charset="UTF-8">` powinien znajdować się jak najbliżej początku sekcji `<head>`?**
2. **Czym różni się podłączanie CSS za pomocą `<link>` od stosowania znacznika `<style>` i która metoda jest preferowana w dużych projektach?**
3. **Za co odpowiada parametr `name="viewport"` w znaczniku `<meta>` i dlaczego jest kluczowy dla urządzeń mobilnych?**
4. **Gdzie w oknie przeglądarki użytkownik zobaczy tekst wpisany wewnątrz znacznika `<title>`?**
5. **Jak działa znacznik `<base>` na linki relatywne umieszczone w sekcji `<body>`?**

---

## 4. Ćwiczenia praktyczne

### Ćwiczenie 1: Szablon nowej strony
Stwórz pełny dokument HTML5 zawierający w sekcji `<head>`:
* Poprawne kodowanie znaków UTF-8.
* Tytuł strony: „*Moje Portfolio – Jan Kowalski*”.
* Metadane z opisem strony oraz autorem.
* Odpowiedni `viewport` dla urządzeń mobilnych.
* Podłączony zewnętrzny plik stylów `main.css`.

<details>
<summary><b>Rozwiązanie (kliknij, aby rozwinąć)</b></summary>

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portfolio koncepcji i projektów webowych Jana Kowalskiego.">
    <meta name="author" content="Jan Kowalski">
    <title>Moje Portfolio – Jan Kowalski</title>
    <link rel="stylesheet" href="main.css">
</head>
<body>
    <h1>Witaj na mojej stronie!</h1>
</body>
</html>
```
</details>

---

### Ćwiczenie 2: Znajdź i popraw błędy
Przeanalizuj poniższy kod, znajdź błędy związane z sekcją `<head>` i zapisz poprawioną wersję:

```html
<!DOCTYPE html>
<html>
    <title>Strona testowa</title>
    <meta charset="UTF-8">
    <head>
        <link rel="stylesheet" style.css>
        <meta name="description" content="Opis">
    </head>
    <body>
        <p>Treść strony</p>
    </body>
</html>
```

<details>
<summary><b>Rozwiązanie (kliknij, aby rozwinąć)</b></summary>

**Błędy w kodzie:**
1. `<title>` i `<meta charset>` zostały umieszczone poza sekcją `<head>`.
2. Brakuje atrybutu `href=` w znaczniku `<link>` (użyto samego słowa `style.css`).
3. Brakuje atrybutu `lang="pl"` w elemencie `<html>`.

**Poprawny kod:**
```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Strona testowa</title>
    <meta name="description" content="Opis">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <p>Treść strony</p>
</body>
</html>
```
</details>
