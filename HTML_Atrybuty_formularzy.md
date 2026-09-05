# HTML – Atrybuty formularzy (`<form>`)

## 1. Wprowadzenie

Formularze HTML służą do pobierania danych od użytkownika. Mogą być wykorzystywane między innymi do:

- rejestracji użytkownika,
- logowania,
- wysyłania wiadomości,
- wyszukiwania informacji,
- składania zamówień,
- przesyłania plików.

Podstawowym elementem formularza jest znacznik:

```html
<form>
    ...
</form>
```

Sam znacznik `<form>` może posiadać szereg **atrybutów**, które określają sposób przesyłania danych, miejsce ich wysłania, sposób walidacji oraz zachowanie przeglądarki.

---

## 2. Atrybut `action`

Atrybut `action` określa **adres, do którego zostaną wysłane dane formularza** po jego zatwierdzeniu.

### Przykład

```html
<form action="/action_page.php">
    <label>Imię:</label>
    <input type="text" name="imie">

    <input type="submit" value="Wyślij">
</form>
```

Po kliknięciu przycisku **Wyślij** dane zostaną przesłane do:

```text
/action_page.php
```

Najczęściej `action` wskazuje na skrypt znajdujący się na serwerze, który przetwarza przesłane dane. Jeżeli atrybut `action` nie zostanie podany, formularz domyślnie zostanie wysłany do bieżącej strony.

---

## 3. Atrybut `target`

Atrybut `target` określa, **gdzie zostanie wyświetlona odpowiedź otrzymana po wysłaniu formularza**.

Najważniejsze wartości:

| Wartość | Znaczenie |
|---|---|
| `_self` | otwarcie odpowiedzi w bieżącym oknie/kartce |
| `_blank` | otwarcie odpowiedzi w nowej karcie lub oknie |
| `_parent` | otwarcie w ramce nadrzędnej |
| `_top` | otwarcie w całym obszarze okna |
| `framename` | otwarcie w określonej ramce |

Domyślną wartością jest `_self`.

### Przykład

```html
<form action="/action_page.php" target="_blank">
    <input type="text" name="imie">
    <input type="submit" value="Wyślij">
</form>
```

W tym przypadku wynik przesłania formularza zostanie otwarty w **nowej karcie**.

---

## 4. Atrybut `method`

Atrybut `method` określa **sposób przesłania danych formularza**.

Najczęściej stosowane są dwie wartości:

```html
method="get"
```

oraz:

```html
method="post"
```

### GET

Przykład:

```html
<form action="/search.php" method="get">
```

Dane są przekazywane jako część adresu URL.

Przykładowo:

```text
search.php?imie=Anna&nazwisko=Kowalska
```

Metoda GET jest przydatna między innymi w przypadku formularzy wyszukiwania.

### POST

Przykład:

```html
<form action="/register.php" method="post">
```

Dane są przesyłane w treści żądania HTTP, a nie jako część adresu URL.

POST jest często stosowany przy:

- rejestracji,
- logowaniu,
- przesyłaniu większej ilości danych,
- przesyłaniu danych, których nie chcemy umieszczać w adresie URL.

Jeżeli `method` nie zostanie określony, domyślnie stosowana jest metoda GET.

> **Ważne:** użycie POST samo w sobie nie szyfruje danych. Przy przesyłaniu danych wrażliwych należy stosować połączenie HTTPS.

---

## 5. Atrybut `autocomplete`

Atrybut `autocomplete` określa, czy przeglądarka może **automatycznie uzupełniać wartości wpisywane przez użytkownika**.

### Włączenie

```html
<form autocomplete="on">
```

### Wyłączenie

```html
<form autocomplete="off">
```

### Przykład

```html
<form action="/register.php" method="post" autocomplete="on">

    <label for="name">Imię:</label>
    <input type="text" id="name" name="name">

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email">

    <input type="submit" value="Zarejestruj">
</form>
```

Przy włączonym autouzupełnianiu przeglądarka może proponować wartości, które użytkownik wcześniej wprowadzał.

---

## 6. Atrybut `novalidate`

`novalidate` jest **atrybutem typu boolean**.

Jeżeli zostanie dodany do formularza, wyłącza wbudowaną w przeglądarkę walidację formularza podczas jego wysyłania.

### Przykład

```html
<form action="/action_page.php" novalidate>
    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email">

    <input type="submit" value="Wyślij">
</form>
```

W normalnym przypadku przeglądarka sprawdzi m.in. poprawność pola typu `email`.

Po zastosowaniu:

```html
novalidate
```

ta automatyczna walidacja formularza zostaje pominięta.

---

## 7. Atrybut `enctype`

Atrybut `enctype` określa **sposób zakodowania danych formularza podczas ich wysyłania**. Jest szczególnie istotny przy metodzie `POST`.

### `application/x-www-form-urlencoded`

Jest to standardowy sposób kodowania danych formularza.

```html
<form method="post"
      enctype="application/x-www-form-urlencoded">
```

### `multipart/form-data`

Stosuje się go przede wszystkim wtedy, gdy formularz umożliwia **przesyłanie plików**.

```html
<form method="post"
      enctype="multipart/form-data">
```

### Przykład przesyłania pliku

```html
<form action="/upload.php"
      method="post"
      enctype="multipart/form-data">

    <label for="plik">Wybierz plik:</label>
    <input type="file" id="plik" name="plik">

    <input type="submit" value="Wyślij">
</form>
```

### `text/plain`

Dane są przesyłane jako zwykły tekst.

```html
<form method="post" enctype="text/plain">
```

---

## 8. Atrybut `name`

Atrybut `name` pozwala nadać formularzowi nazwę.

```html
<form name="formularzRejestracji">
```

Nazwa może być wykorzystywana między innymi przez skrypty JavaScript do identyfikowania formularza.

### Przykład

```html
<form name="formularzKontaktowy">
    <input type="text" name="imie">
    <input type="email" name="email">
</form>
```

---

## 9. Atrybut `accept-charset`

`accept-charset` określa **kodowanie znaków używane podczas przesyłania danych formularza**.

### Przykład

```html
<form action="/action.php"
      method="post"
      accept-charset="UTF-8">
```

UTF-8 jest obecnie podstawowym i powszechnie stosowanym kodowaniem znaków w dokumentach internetowych.

---

## 10. Atrybut `rel`

Atrybut `rel` określa **relację pomiędzy bieżącym dokumentem a zasobem powiązanym z formularzem**.

Przykładowe wartości to między innymi:

```text
external
help
license
next
nofollow
noopener
noreferrer
opener
prev
search
```

W praktycznych zastosowaniach należy dobierać wartość `rel` odpowiednio do charakteru powiązania.

---

## 11. Kompletny przykład formularza

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Formularz rejestracyjny</title>
</head>

<body>

<h1>Formularz rejestracyjny</h1>

<form
    action="/register.php"
    method="post"
    target="_self"
    autocomplete="on"
    accept-charset="UTF-8">

    <label for="imie">Imię:</label>
    <input type="text" id="imie" name="imie">

    <br><br>

    <label for="nazwisko">Nazwisko:</label>
    <input type="text" id="nazwisko" name="nazwisko">

    <br><br>

    <label for="email">Adres e-mail:</label>
    <input type="email" id="email" name="email">

    <br><br>

    <label for="haslo">Hasło:</label>
    <input type="password" id="haslo" name="haslo">

    <br><br>

    <input type="submit" value="Zarejestruj">

</form>

</body>
</html>
```

### Jak działa ten formularz?

1. `action="/register.php"` – określa miejsce przesłania danych.
2. `method="post"` – dane są wysyłane metodą POST.
3. `target="_self"` – odpowiedź zostanie otwarta w bieżącej karcie.
4. `autocomplete="on"` – przeglądarka może pomagać w uzupełnianiu danych.
5. `accept-charset="UTF-8"` – określa kodowanie znaków.
6. `name` przy poszczególnych polach umożliwia identyfikację przesyłanych wartości.

---

## 12. Najważniejsze atrybuty – tabela podsumowująca

| Atrybut | Do czego służy? | Przykład |
|---|---|---|
| `action` | Określa miejsce wysłania danych | `action="send.php"` |
| `method` | Określa sposób przesłania danych | `method="post"` |
| `target` | Określa miejsce wyświetlenia odpowiedzi | `target="_blank"` |
| `autocomplete` | Włącza/wyłącza autouzupełnianie | `autocomplete="on"` |
| `novalidate` | Wyłącza walidację formularza | `novalidate` |
| `enctype` | Określa sposób kodowania danych | `enctype="multipart/form-data"` |
| `name` | Nadaje formularzowi nazwę | `name="kontakt"` |
| `accept-charset` | Określa kodowanie znaków | `accept-charset="UTF-8"` |
| `rel` | Określa relację z powiązanym zasobem | `rel="noopener"` |

---

# 13. Ćwiczenia dla studentów

## Ćwiczenie 1 – formularz kontaktowy

Utwórz formularz zawierający:

- imię,
- nazwisko,
- adres e-mail,
- numer telefonu,
- wiadomość,
- przycisk „Wyślij”.

Zastosuj:

```html
method="post"
```

oraz:

```html
autocomplete="on"
```

---

## Ćwiczenie 2 – metoda GET

Utwórz formularz wyszukiwarki:

```html
<form action="/search.php" method="get">
```

Dodaj pole:

```html
<input type="search" name="q">
```

oraz przycisk wyszukiwania.

### Pytanie

Co pojawi się w adresie URL po wysłaniu formularza?

---

## Ćwiczenie 3 – przesyłanie pliku

Utwórz formularz umożliwiający przesłanie zdjęcia.

Wykorzystaj:

```html
method="post"
```

oraz:

```html
enctype="multipart/form-data"
```

---

## Ćwiczenie 4 – walidacja

Utwórz formularz z polem:

```html
<input type="email" required>
```

Sprawdź działanie formularza bez `novalidate`, a następnie dodaj:

```html
novalidate
```

### Pytanie

Jak zmieniło się zachowanie formularza?

---

# 14. Pytania kontrolne

1. Do czego służy atrybut `action`?
2. Czym różnią się metody `GET` i `POST`?
3. Jaka jest domyślna metoda formularza?
4. Do czego służy `target="_blank"`?
5. Co umożliwia `autocomplete`?
6. Do czego służy `novalidate`?
7. Kiedy należy stosować `multipart/form-data`?
8. Do czego służy atrybut `name`?
9. Czym zajmuje się `accept-charset`?
10. Jakie atrybuty można zastosować do elementu `<form>`?

---

# 15. Najważniejsze informacje do zapamiętania

- **`action` → gdzie wysyłamy dane**
- **`method` → jak wysyłamy dane**
- **`target` → gdzie pokazujemy odpowiedź**
- **`autocomplete` → czy przeglądarka podpowiada dane**
- **`novalidate` → czy wyłączamy walidację**
- **`enctype` → jak kodujemy dane**
- **`name` → nazwa formularza**
- **`accept-charset` → kodowanie znaków**
- **`rel` → relacja z powiązanym zasobem**

## Źródło

Materiał opracowany na podstawie:

[W3Schools – HTML Form Attributes](https://www.w3schools.com/html/html_forms_attributes.asp)
