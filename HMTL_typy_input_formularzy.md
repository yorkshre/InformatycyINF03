# HTML – Typy elementu `<input>`

## 1. Wprowadzenie

Element `<input>` jest jednym z najważniejszych elementów formularzy HTML. Za pomocą atrybutu `type` można określić, jaki rodzaj danych użytkownik ma wprowadzić.

Składnia:

```html
<input type="typ">
```

Jeżeli atrybut `type` nie zostanie określony, domyślnie stosowany jest typ `text`.

Współczesny HTML udostępnia między innymi typy:

- `button`
- `checkbox`
- `color`
- `date`
- `datetime-local`
- `email`
- `file`
- `hidden`
- `image`
- `month`
- `number`
- `password`
- `radio`
- `range`
- `reset`
- `search`
- `submit`
- `tel`
- `text`
- `time`
- `url`
- `week`

---

# 2. `type="text"` – pole tekstowe

Typ `text` służy do wprowadzania tekstu w jednej linii.

### Przykład

```html
<label for="imie">Imię:</label>
<input type="text" id="imie" name="imie">
```

Pole tekstowe może być używane np. do wpisania:

- imienia,
- nazwiska,
- miejscowości,
- ulicy,
- nazwy użytkownika.

### Ćwiczenie

Utwórz formularz zawierający pola:

- imię,
- nazwisko,
- miejscowość.

Do każdego pola dodaj odpowiedni `<label>`.

---

# 3. `type="password"` – hasło

Typ `password` służy do wprowadzania haseł. Znaki wpisywane przez użytkownika są wizualnie ukrywane, np. za pomocą kropek lub symboli.

### Przykład

```html
<label for="haslo">Hasło:</label>
<input type="password" id="haslo" name="haslo">
```

### Ćwiczenie

Utwórz formularz rejestracyjny zawierający:

```text
Nazwa użytkownika
Hasło
Powtórz hasło
```

Pola haseł powinny używać:

```html
type="password"
```

---

# 4. `type="submit"` – wysłanie formularza

Typ `submit` tworzy przycisk służący do przesłania formularza.

### Przykład

```html
<form action="/action.php">

    <label for="imie">Imię:</label>
    <input type="text" id="imie" name="imie">

    <input type="submit" value="Wyślij">

</form>
```

Po kliknięciu przycisku dane formularza są wysyłane do miejsca określonego przez atrybut `action`.

### Ćwiczenie

Utwórz formularz zawierający:

- imię,
- nazwisko,
- e-mail,
- przycisk „Wyślij”.

---

# 5. `type="reset"` – wyczyszczenie formularza

Typ `reset` tworzy przycisk, który przywraca wartości pól formularza do ich wartości początkowych.

### Przykład

```html
<form>

    <input type="text" name="imie" value="Anna">

    <input type="submit" value="Wyślij">
    <input type="reset" value="Wyczyść">

</form>
```

Po zmianie wartości i kliknięciu **Wyczyść** pola zostaną przywrócone do wartości początkowych.

### Ćwiczenie

Dodaj do formularza kontaktowego dwa przyciski:

```text
Wyślij
Wyczyść
```

---

# 6. `type="radio"` – wybór jednej opcji

Radio button pozwala użytkownikowi wybrać **jedną opcję z określonej grupy**.

### Przykład

```html
<p>Wybierz płeć:</p>

<input type="radio" id="kobieta" name="plec" value="kobieta">
<label for="kobieta">Kobieta</label>

<input type="radio" id="mezczyzna" name="plec" value="mezczyzna">
<label for="mezczyzna">Mężczyzna</label>
```

### Ważne

Aby przyciski radio tworzyły jedną grupę, powinny mieć taką samą wartość `name`:

```html
name="plec"
```

Dzięki temu użytkownik może zaznaczyć tylko jedną opcję.

### Ćwiczenie

Utwórz pytanie:

> Jaki jest Twój ulubiony język programowania?

Opcje:

- HTML
- CSS
- JavaScript
- Python
- C++

Użyj `type="radio"`.

---

# 7. `type="checkbox"` – wybór wielu opcji

Checkbox umożliwia zaznaczenie **zera, jednej lub wielu opcji**.

### Przykład

```html
<p>Zainteresowania:</p>

<input type="checkbox" id="sport" name="zainteresowania" value="sport">
<label for="sport">Sport</label>

<input type="checkbox" id="muzyka" name="zainteresowania" value="muzyka">
<label for="muzyka">Muzyka</label>

<input type="checkbox" id="podroze" name="zainteresowania" value="podroze">
<label for="podroze">Podróże</label>
```

### Ćwiczenie

Utwórz listę zainteresowań:

- sport,
- muzyka,
- książki,
- programowanie,
- fotografia,
- podróże.

Użytkownik powinien móc zaznaczyć kilka odpowiedzi.

---

# 8. `type="button"` – zwykły przycisk

Typ `button` tworzy przycisk, który sam w sobie nie przesyła formularza.

Może być wykorzystany np. razem z JavaScript.

### Przykład

```html
<input
    type="button"
    onclick="alert('Witaj!')"
    value="Kliknij mnie">
```

Po kliknięciu zostanie wykonana instrukcja JavaScript.

### Ćwiczenie

Utwórz przycisk:

```text
Pokaż komunikat
```

Po kliknięciu powinien pojawić się komunikat:

```text
Witaj w formularzu!
```

---

# 9. `type="color"` – wybór koloru

Typ `color` służy do wyboru koloru. Przeglądarka może wyświetlić specjalny próbnik kolorów.

### Przykład

```html
<label for="kolor">Wybierz kolor:</label>
<input type="color" id="kolor" name="kolor">
```

### Ćwiczenie

Utwórz formularz zawierający:

- imię,
- ulubiony kolor,
- przycisk „Wyślij”.

Kolor wybieraj za pomocą:

```html
<input type="color">
```

---

# 10. `type="date"` – wybór daty

Typ `date` pozwala użytkownikowi wybrać datę.

### Przykład

```html
<label for="urodziny">Data urodzenia:</label>
<input type="date" id="urodziny" name="urodziny">
```

Przeglądarka może udostępnić użytkownikowi kalendarz.

Można również ograniczyć zakres dat za pomocą `min` i `max`.

### Przykład

```html
<input
    type="date"
    id="data"
    name="data"
    min="2026-01-01"
    max="2026-12-31">
```

### Ćwiczenie

Utwórz formularz rejestracyjny zawierający pole:

> Data urodzenia

Zastosuj:

```html
type="date"
```

---

# 11. `type="datetime-local"` – data i godzina

Typ `datetime-local` pozwala wybrać **datę oraz godzinę**, bez określania strefy czasowej.

### Przykład

```html
<label for="spotkanie">Termin spotkania:</label>
<input
    type="datetime-local"
    id="spotkanie"
    name="spotkanie">
```

### Ćwiczenie

Utwórz formularz rezerwacji wizyty zawierający:

- imię,
- nazwisko,
- datę i godzinę wizyty,
- przycisk „Zarezerwuj”.

---

# 12. `type="email"` – adres e-mail

Typ `email` służy do wprowadzania adresów e-mail.

Przeglądarka może automatycznie sprawdzać podstawową poprawność wprowadzonego adresu podczas wysyłania formularza.

### Przykład

```html
<label for="email">Adres e-mail:</label>
<input type="email" id="email" name="email">
```

### Ćwiczenie

Utwórz formularz kontaktowy zawierający:

- imię,
- nazwisko,
- e-mail,
- wiadomość.

Pole e-mail musi mieć:

```html
type="email"
```

---

# 13. `type="file"` – wybór pliku

Typ `file` pozwala użytkownikowi wybrać plik z urządzenia.

### Przykład

```html
<label for="plik">Wybierz plik:</label>
<input type="file" id="plik" name="plik">
```

Może być wykorzystywany np. do przesyłania:

- zdjęć,
- dokumentów,
- plików PDF,
- innych plików.

### Ćwiczenie

Utwórz formularz:

> Dodaj zdjęcie profilowe

Formularz powinien zawierać pole:

```html
<input type="file">
```

---

# 14. `type="hidden"` – ukryte pole

Typ `hidden` tworzy pole, które **nie jest widoczne w normalnym widoku strony**.

### Przykład

```html
<input
    type="hidden"
    id="userId"
    name="userId"
    value="12345">
```

Ukryte pola mogą służyć do przekazywania dodatkowych informacji razem z formularzem.

> **Ważne:** wartość pola `hidden` nie jest zabezpieczona. Użytkownik może ją zobaczyć i zmienić za pomocą narzędzi deweloperskich przeglądarki. Nie należy wykorzystywać pól `hidden` jako mechanizmu bezpieczeństwa.

### Ćwiczenie

Dodaj do formularza ukryte pole:

```text
ID użytkownika = 1001
```

Sprawdź wartość tego pola za pomocą narzędzi deweloperskich przeglądarki.

---

# 15. `type="image"` – obraz jako przycisk

Typ `image` pozwala wykorzystać obraz jako przycisk wysyłający formularz.

### Przykład

```html
<input
    type="image"
    src="przycisk.png"
    alt="Wyślij"
    width="48"
    height="48">
```

Atrybut `src` wskazuje plik graficzny.

### Ćwiczenie

Przygotuj własną grafikę i wykorzystaj ją jako przycisk wysyłania formularza.

---

# 16. `type="month"` – miesiąc i rok

Typ `month` pozwala wybrać **miesiąc oraz rok**.

### Przykład

```html
<label for="miesiac">Wybierz miesiąc:</label>
<input type="month" id="miesiac" name="miesiac">
```

### Ćwiczenie

Utwórz formularz zawierający pytanie:

> W którym miesiącu planujesz urlop?

Zastosuj:

```html
<input type="month">
```

---

# 17. `type="number"` – liczba

Typ `number` służy do wprowadzania wartości liczbowych.

Można określić zakres za pomocą `min` i `max`.

### Przykład

```html
<label for="ilosc">Liczba sztuk:</label>

<input
    type="number"
    id="ilosc"
    name="ilosc"
    min="1"
    max="10">
```

Można również określić krok za pomocą `step`.

### Przykład

```html
<input
    type="number"
    min="0"
    max="100"
    step="10"
    value="30">
```

Wartości mogą być wtedy wybierane np. co 10.

### Ćwiczenie

Utwórz pole:

> Liczba biletów

Ustaw:

- minimum: `1`,
- maksimum: `10`,
- wartość domyślną: `2`.

---

# 18. `type="range"` – suwak

Typ `range` tworzy suwak umożliwiający wybór wartości z określonego zakresu.

### Przykład

```html
<label for="glosnosc">Głośność:</label>

<input
    type="range"
    id="glosnosc"
    name="glosnosc"
    min="0"
    max="100">
```

Można wykorzystać również `step`.

### Przykład

```html
<input
    type="range"
    min="0"
    max="100"
    step="10">
```

### Ćwiczenie

Utwórz suwak:

> Ocena produktu

Zakres:

```text
1–10
```

---

# 19. `type="search"` – wyszukiwanie

Typ `search` służy do tworzenia pola wyszukiwania.

### Przykład

```html
<label for="szukaj">Szukaj:</label>
<input type="search" id="szukaj" name="szukaj">
```

Pole zachowuje się podobnie do zwykłego pola tekstowego, ale wskazuje przeglądarce, że jest przeznaczone do wyszukiwania.

### Ćwiczenie

Utwórz formularz wyszukiwarki zawierający:

```html
<input type="search">
```

oraz przycisk:

```text
Szukaj
```

---

# 20. `type="tel"` – numer telefonu

Typ `tel` jest przeznaczony do wprowadzania numerów telefonicznych.

### Przykład

```html
<label for="telefon">Numer telefonu:</label>

<input
    type="tel"
    id="telefon"
    name="telefon">
```

Można zastosować `pattern`, aby określić wymagany format.

### Przykład

```html
<input
    type="tel"
    id="telefon"
    name="telefon"
    pattern="[0-9]{3}-[0-9]{3}-[0-9]{3}">
```

Przykładowy poprawny format:

```text
123-456-789
```

### Ćwiczenie

Utwórz pole numeru telefonu wymagające formatu:

```text
123-456-789
```

---

# 21. `type="time"` – godzina

Typ `time` pozwala użytkownikowi wybrać godzinę bez określania strefy czasowej.

### Przykład

```html
<label for="godzina">Godzina wizyty:</label>
<input type="time" id="godzina" name="godzina">
```

### Ćwiczenie

Utwórz formularz rezerwacji:

- data,
- godzina,
- imię,
- nazwisko.

Do godziny zastosuj:

```html
type="time"
```

---

# 22. `type="url"` – adres URL

Typ `url` służy do wprowadzania adresu strony internetowej.

### Przykład

```html
<label for="strona">Adres strony:</label>

<input
    type="url"
    id="strona"
    name="strona">
```

Przeglądarka może sprawdzić podstawową poprawność adresu URL podczas wysyłania formularza.

### Ćwiczenie

Utwórz formularz zawierający pole:

> Twoja strona internetowa

Zastosuj:

```html
<input type="url">
```

---

# 23. `type="week"` – tydzień

Typ `week` pozwala wybrać **tydzień i rok**.

### Przykład

```html
<label for="tydzien">Wybierz tydzień:</label>

<input
    type="week"
    id="tydzien"
    name="tydzien">
```

### Ćwiczenie

Utwórz formularz planowania zajęć, w którym użytkownik wybiera tydzień roku.

---

# 24. Tabela wszystkich typów `input`

| Typ | Zastosowanie |
|---|---|
| `text` | jednoliniowe pole tekstowe |
| `password` | hasło |
| `submit` | wysłanie formularza |
| `reset` | przywrócenie wartości początkowych |
| `radio` | wybór jednej opcji |
| `checkbox` | wybór wielu opcji |
| `button` | zwykły przycisk |
| `color` | wybór koloru |
| `date` | wybór daty |
| `datetime-local` | data i godzina |
| `email` | adres e-mail |
| `file` | wybór pliku |
| `hidden` | ukryta wartość |
| `image` | obraz jako przycisk wysyłania |
| `month` | miesiąc i rok |
| `number` | liczba |
| `range` | wartość wybierana suwakiem |
| `search` | pole wyszukiwania |
| `tel` | numer telefonu |
| `time` | godzina |
| `url` | adres URL |
| `week` | tydzień i rok |

---

# 25. Najważniejsze atrybuty używane z `input`

Typ elementu określa atrybut:

```html
type="..."
```

Jednak pola `<input>` mogą mieć także inne przydatne atrybuty.

| Atrybut | Znaczenie |
|---|---|
| `id` | identyfikator elementu |
| `name` | nazwa wartości przesyłanej z formularzem |
| `value` | wartość początkowa |
| `min` | wartość minimalna |
| `max` | wartość maksymalna |
| `step` | odstęp pomiędzy wartościami |
| `required` | pole obowiązkowe |
| `disabled` | pole nieaktywne |
| `readonly` | pole tylko do odczytu |
| `checked` | domyślne zaznaczenie radio/checkbox |
| `maxlength` | maksymalna liczba znaków |
| `pattern` | wzorzec wymagany dla wartości |
| `placeholder` | tekst podpowiedzi |

---

# 26. Przykład kompletnego formularza

```html
<!DOCTYPE html>
<html lang="pl">

<head>
    <meta charset="UTF-8">
    <title>Formularz rejestracyjny</title>
</head>

<body>

<h1>Formularz rejestracyjny</h1>

<form>

    <label for="imie">Imię:</label>
    <input type="text" id="imie" name="imie" required>

    <br><br>

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email" required>

    <br><br>

    <label for="haslo">Hasło:</label>
    <input type="password" id="haslo" name="haslo" required>

    <br><br>

    <label for="urodziny">Data urodzenia:</label>
    <input type="date" id="urodziny" name="urodziny">

    <br><br>

    <label for="telefon">Telefon:</label>
    <input type="tel" id="telefon" name="telefon">

    <br><br>

    <p>Poziom znajomości HTML:</p>

    <input type="radio" id="poczatkujacy"
           name="poziom" value="poczatkujacy">
    <label for="poczatkujacy">Początkujący</label>

    <input type="radio" id="sredni"
           name="poziom" value="sredni">
    <label for="sredni">Średniozaawansowany</label>

    <input type="radio" id="zaawansowany"
           name="poziom" value="zaawansowany">
    <label for="zaawansowany">Zaawansowany</label>

    <br><br>

    <p>Zainteresowania:</p>

    <input type="checkbox" id="sport"
           name="zainteresowania" value="sport">
    <label for="sport">Sport</label>

    <input type="checkbox" id="muzyka"
           name="zainteresowania" value="muzyka">
    <label for="muzyka">Muzyka</label>

    <input type="checkbox" id="programowanie"
           name="zainteresowania" value="programowanie">
    <label for="programowanie">Programowanie</label>

    <br><br>

    <label for="kolor">Ulubiony kolor:</label>
    <input type="color" id="kolor" name="kolor">

    <br><br>

    <label for="doswiadczenie">
        Lata doświadczenia:
    </label>

    <input
        type="number"
        id="doswiadczenie"
        name="doswiadczenie"
        min="0"
        max="50">

    <br><br>

    <input type="submit" value="Zarejestruj">
    <input type="reset" value="Wyczyść">

</form>

</body>
</html>
```

---

# 27. Ćwiczenie kompleksowe

## Formularz rejestracji użytkownika

Zaprojektuj kompletny formularz rejestracyjny.

Formularz powinien zawierać:

### Dane podstawowe

- imię – `text`,
- nazwisko – `text`,
- e-mail – `email`,
- hasło – `password`,
- telefon – `tel`,
- data urodzenia – `date`.

### Preferencje

Użytkownik powinien wybrać:

- jeden poziom znajomości HTML – `radio`,
- kilka zainteresowań – `checkbox`,
- ulubiony kolor – `color`.

### Dodatkowe dane

Dodaj:

- liczbę lat doświadczenia – `number`,
- stronę internetową – `url`,
- zdjęcie – `file`.

### Przyciski

Dodaj:

```html
<input type="submit">
```

oraz:

```html
<input type="reset">
```

---

# 28. Ćwiczenie – rozpoznaj typ

Dopasuj odpowiedni typ `input` do zastosowania:

| Zastosowanie | Typ |
|---|---|
| Hasło | ? |
| Adres e-mail | ? |
| Data urodzenia | ? |
| Numer telefonu | ? |
| Wybór jednej odpowiedzi | ? |
| Wybór wielu odpowiedzi | ? |
| Przesłanie zdjęcia | ? |
| Wybór koloru | ? |
| Liczba produktów | ? |
| Wyszukiwanie | ? |
| Adres strony internetowej | ? |
| Godzina | ? |

---

# 29. Ćwiczenie – popraw błędny formularz

Poniższy kod zawiera błędy:

```html
<form>

    <label for="email">E-mail:</label>
    <input type="text" id="mail" name="email">

    <p>Wybierz język:</p>

    <input type="radio" name="html" value="HTML">
    <label>HTML</label>

    <input type="radio" name="css" value="CSS">
    <label>CSS</label>

    <input type="submit" value="Wyślij">

</form>
```

### Zadanie

Popraw kod tak, aby:

1. `<label>` był prawidłowo połączony z polem e-mail.
2. Pole e-mail miało właściwy typ.
3. Przyciski radio pozwalały wybrać tylko jedną odpowiedź.
4. Każdy przycisk radio posiadał odpowiednią etykietę.

---

# 30. Pytania kontrolne

1. Do czego służy atrybut `type`?
2. Jaki jest domyślny typ elementu `<input>`?
3. Do czego służy `type="text"`?
4. Jakiego typu używamy do hasła?
5. Czym różnią się `radio` i `checkbox`?
6. Do czego służy `type="email"`?
7. Do czego służy `type="file"`?
8. Czy `hidden` jest mechanizmem bezpieczeństwa?
9. Do czego służy `type="number"`?
10. Jak ograniczyć zakres wartości pola liczbowego?
11. Do czego służy `type="range"`?
12. Kiedy wykorzystujemy `type="date"`?
13. Do czego służy `type="datetime-local"`?
14. Do czego służy `type="tel"`?
15. Do czego służy `type="url"`?
16. Jaka jest różnica między `submit` i `reset`?
17. Do czego służy `type="color"`?
18. Do czego służy `type="search"`?
19. Jak utworzyć pole wyboru tygodnia?
20. Jak utworzyć pole wyboru miesiąca i roku?

---

# 31. Najważniejsze informacje do zapamiętania

- `text` → tekst
- `password` → hasło
- `email` → e-mail
- `number` → liczba
- `date` → data
- `datetime-local` → data i godzina
- `time` → godzina
- `month` → miesiąc i rok
- `week` → tydzień i rok
- `tel` → telefon
- `url` → adres URL
- `search` → wyszukiwanie
- `file` → plik
- `color` → kolor
- `radio` → jedna opcja
- `checkbox` → wiele opcji
- `range` → suwak
- `submit` → wysłanie formularza
- `reset` → reset formularza
- `button` → zwykły przycisk
- `hidden` → ukryta wartość
- `image` → obraz jako przycisk wysyłania


