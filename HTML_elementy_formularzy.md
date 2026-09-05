# HTML – Elementy formularzy (`<form>`)

## 1\. Wprowadzenie

Formularze HTML służą do umożliwienia użytkownikowi wprowadzania i przesyłania danych. Mogą być wykorzystywane między innymi w:

* formularzach kontaktowych,
* rejestracji użytkowników,
* logowaniu,
* ankietach,
* wyszukiwarkach,
* zamówieniach internetowych,
* formularzach przesyłania plików.

Element `<form>` może zawierać różne elementy formularza, między innymi:

* `<input>`
* `<label>`
* `<select>`
* `<textarea>`
* `<button>`
* `<fieldset>`
* `<legend>`
* `<datalist>`
* `<output>`
* `<option>`
* `<optgroup>`
* 

\---

# 2\. Element `<input>`

Element `<input>` jest jednym z najczęściej używanych elementów formularzy.

Jego wygląd i sposób działania zależy przede wszystkim od atrybutu `type`.

### Przykład

```html
<label for="imie">Imię:</label>
<input type="text" id="imie" name="imie">
```

W tym przykładzie:

* `type="text"` – tworzy jednoliniowe pole tekstowe,
* `id="imie"` – identyfikuje element,
* `name="imie"` – określa nazwę przesyłanej wartości,
* `for="imie"` w `<label>` łączy etykietę z polem.

### Przykładowe typy `input`

|Typ|Zastosowanie|
|-|-|
|`text`|tekst|
|`email`|adres e-mail|
|`password`|hasło|
|`number`|liczba|
|`date`|data|
|`radio`|wybór jednej opcji|
|`checkbox`|wybór wielu opcji|
|`file`|wybór pliku|
|`submit`|wysłanie formularza|
|`reset`|wyczyszczenie formularza|
|`range`|wybór wartości z zakresu|

Szczegółowe typy elementu `<input>` są omawiane w osobnym zagadnieniu dotyczącym HTML Input Types. citeturn0view0

\---

# 3\. Element `<label>`

Element `<label>` definiuje **etykietę opisującą pole formularza**.

### Przykład

```html
<label for="nazwisko">Nazwisko:</label>
<input type="text" id="nazwisko" name="nazwisko">
```

Atrybut `for` elementu `<label>` powinien odpowiadać wartości `id` elementu formularza.

Czyli:

```html
<label for="email">E-mail:</label>
<input type="email" id="email" name="email">
```

### Dlaczego `<label>` jest ważny?

`<label>`:

* ułatwia użytkownikowi zrozumienie, jakie dane należy wpisać,
* poprawia dostępność formularza,
* jest pomocny dla użytkowników korzystających z czytników ekranu,
* pozwala między innymi kliknąć tekst etykiety przy polach wyboru, takich jak checkbox lub radio.

Właściwe powiązanie `for` z `id` jest ważnym elementem poprawnej konstrukcji formularza. citeturn0view0

\---

# 4\. Element `<select>`

Element `<select>` tworzy **listę rozwijaną**.

### Przykład

```html
<label for="miasto">Wybierz miasto:</label>

<select id="miasto" name="miasto">
    <option value="gdansk">Gdańsk</option>
    <option value="gdynia">Gdynia</option>
    <option value="sopot">Sopot</option>
    <option value="warszawa">Warszawa</option>
</select>
```

Użytkownik może wybrać jedną z dostępnych pozycji.

\---

## 4.1. Element `<option>`

Element `<option>` definiuje pojedynczą opcję znajdującą się wewnątrz `<select>`.

```html
<option value="gdynia">Gdynia</option>
```

* `value` – wartość przekazywana podczas wysyłania formularza,
* tekst `Gdynia` – tekst widoczny dla użytkownika.

Domyślnie zaznaczona jest pierwsza opcja. Można jednak wskazać inną opcję za pomocą `selected`. citeturn0view0

### Przykład

```html
<select name="miasto">
    <option value="gdansk">Gdańsk</option>
    <option value="gdynia" selected>Gdynia</option>
    <option value="sopot">Sopot</option>
</select>
```

\---

## 4.2. Atrybut `size`

Atrybut `size` pozwala określić liczbę widocznych pozycji.

```html
<select name="miasto" size="3">
    <option>Gdańsk</option>
    <option>Gdynia</option>
    <option>Sopot</option>
    <option>Warszawa</option>
</select>
```

W tym przypadku jednocześnie widoczne są trzy pozycje. citeturn0view0

\---

## 4.3. Atrybut `multiple`

Atrybut `multiple` pozwala użytkownikowi wybrać więcej niż jedną opcję.

```html
<select name="miasta" size="4" multiple>
    <option>Gdańsk</option>
    <option>Gdynia</option>
    <option>Sopot</option>
    <option>Warszawa</option>
</select>
```

Jest to przydatne wtedy, gdy użytkownik może zaznaczyć kilka odpowiedzi. citeturn0view0

\---

# 5\. Element `<textarea>`

Element `<textarea>` tworzy **wieloliniowe pole tekstowe**.

Jest przydatny między innymi do:

* wiadomości,
* komentarzy,
* opisów,
* uwag,
* odpowiedzi ankietowych.

### Przykład

```html
<label for="wiadomosc">Wiadomość:</label>

<textarea id="wiadomosc" name="wiadomosc" rows="5" cols="40"></textarea>
```

\---

## 5.1. Atrybut `rows`

`rows` określa liczbę widocznych wierszy pola.

```html
<textarea rows="5"></textarea>
```

\---

## 5.2. Atrybut `cols`

`cols` określa widoczną szerokość pola tekstowego.

```html
<textarea cols="40"></textarea>
```

Rozmiar `<textarea>` można również określić za pomocą CSS. citeturn0view0

### Przykład z CSS

```html
<textarea
    name="wiadomosc"
    style="width: 300px; height: 150px;">
</textarea>
```

\---

# 6\. Element `<button>`

Element `<button>` tworzy **klikalny przycisk**.

### Przykład

```html
<button type="button">Kliknij mnie</button>
```

Przycisk może wykonywać różne działania, np. uruchamiać JavaScript lub przesyłać formularz.

### Przykład

```html
<button type="button" onclick="alert('Witaj!')">
    Kliknij mnie
</button>
```

W formularzach warto zawsze jawnie określać atrybut `type`, ponieważ przyciski mogą mieć różne zastosowania. citeturn0view0

Najczęściej spotykane wartości:

```html
<button type="button">Zwykły przycisk</button>

<button type="submit">Wyślij</button>

<button type="reset">Wyczyść</button>
```

\---

# 7\. Element `<fieldset>`

`<fieldset>` służy do **grupowania powiązanych elementów formularza**.

Jest szczególnie przydatny w większych formularzach.

### Przykład

```html
<form>

    <fieldset>
        <legend>Dane osobowe</legend>

        <label for="imie">Imię:</label>
        <input type="text" id="imie" name="imie">

        <br><br>

        <label for="nazwisko">Nazwisko:</label>
        <input type="text" id="nazwisko" name="nazwisko">
    </fieldset>

</form>
```

Dzięki `<fieldset>` pola związane z danym zagadnieniem można logicznie pogrupować. citeturn0view0

\---

# 8\. Element `<legend>`

`<legend>` określa **tytuł/opis grupy utworzonej przez `<fieldset>`**.

### Przykład

```html
<fieldset>
    <legend>Dane kontaktowe</legend>

    <label for="email">E-mail:</label>
    <input type="email" id="email" name="email">

    <label for="telefon">Telefon:</label>
    <input type="tel" id="telefon" name="telefon">
</fieldset>
```

W tym przypadku tekst:

```text
Dane kontaktowe
```

jest opisem grupy pól.

\---

# 9\. Element `<datalist>`

`<datalist>` umożliwia przygotowanie **listy wcześniej zdefiniowanych propozycji dla pola `<input>`**.

Użytkownik może rozpocząć wpisywanie danych, a przeglądarka może wyświetlić dostępne propozycje.

### Przykład

```html
<label for="przegladarka">Wybierz przeglądarkę:</label>

<input list="przegladarki" id="przegladarka" name="przegladarka">

<datalist id="przegladarki">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Edge">
    <option value="Opera">
    <option value="Safari">
</datalist>
```

Ważne jest powiązanie:

```html
<input list="przegladarki">
```

z:

```html
<datalist id="przegladarki">
```

Wartość `list` musi odpowiadać wartości `id` elementu `<datalist>`. citeturn0view0

\---

# 10\. Element `<output>`

`<output>` służy do **prezentowania wyniku obliczenia**, np. wykonanego za pomocą JavaScript.

### Przykład

```html
<form oninput="wynik.value=parseInt(a.value)+parseInt(b.value)">

    <input type="number" id="a" name="a" value="10">

    +

    <input type="number" id="b" name="b" value="20">

    =

    <output name="wynik" for="a b"></output>

</form>
```

Po zmianie wartości pól wynik może być automatycznie aktualizowany.

Element `<output>` jest szczególnie przydatny w formularzach zawierających obliczenia. citeturn0view0

\---

# 11\. Element `<optgroup>`

`<optgroup>` pozwala **grupować opcje znajdujące się w elemencie `<select>`**.

### Przykład

```html
<label for="samochod">Wybierz samochód:</label>

<select id="samochod" name="samochod">

    <optgroup label="Niemieckie">
        <option value="audi">Audi</option>
        <option value="bmw">BMW</option>
        <option value="mercedes">Mercedes</option>
    </optgroup>

    <optgroup label="Japońskie">
        <option value="toyota">Toyota</option>
        <option value="honda">Honda</option>
        <option value="mazda">Mazda</option>
    </optgroup>

</select>
```

Dzięki temu duża liczba opcji może zostać uporządkowana w logiczne grupy.

\---

# 12\. Kompletny przykład formularza

Poniższy przykład wykorzystuje wiele elementów omawianych w tym materiale:

```html
<!DOCTYPE html>
<html lang="pl">

<head>
    <meta charset="UTF-8">
    <title>Formularz kontaktowy</title>
</head>

<body>

<h1>Formularz kontaktowy</h1>

<form>

    <fieldset>
        <legend>Dane osobowe</legend>

        <label for="imie">Imię:</label>
        <input type="text" id="imie" name="imie">

        <br><br>

        <label for="nazwisko">Nazwisko:</label>
        <input type="text" id="nazwisko" name="nazwisko">

        <br><br>

        <label for="email">E-mail:</label>
        <input type="email" id="email" name="email">
    </fieldset>

    <br>

    <fieldset>
        <legend>Dodatkowe informacje</legend>

        <label for="miasto">Miasto:</label>

        <select id="miasto" name="miasto">
            <option value="gdansk">Gdańsk</option>
            <option value="gdynia">Gdynia</option>
            <option value="sopot">Sopot</option>
        </select>

        <br><br>

        <label for="wiadomosc">Wiadomość:</label><br>

        <textarea
            id="wiadomosc"
            name="wiadomosc"
            rows="6"
            cols="40"></textarea>

    </fieldset>

    <br>

    <button type="submit">Wyślij</button>
    <button type="reset">Wyczyść</button>

</form>

</body>
</html>
```

\---

# 13\. Podsumowanie elementów formularza

|Element|Zastosowanie|
|-|-|
|`<form>`|definiuje formularz|
|`<input>`|tworzy różnego rodzaju pola wejściowe|
|`<label>`|tworzy etykietę pola|
|`<select>`|tworzy listę rozwijaną|
|`<option>`|definiuje pojedynczą opcję|
|`<optgroup>`|grupuje opcje w `<select>`|
|`<textarea>`|tworzy wieloliniowe pole tekstowe|
|`<button>`|tworzy przycisk|
|`<fieldset>`|grupuje powiązane pola|
|`<legend>`|nadaje nazwę grupie `<fieldset>`|
|`<datalist>`|tworzy listę propozycji dla `<input>`|
|`<output>`|prezentuje wynik obliczenia|

Zestawienie odpowiada elementom formularzy wymienionym w materiale W3Schools. citeturn0view0

\---

# 14\. Ćwiczenia

## Ćwiczenie 1 – formularz danych osobowych

Utwórz formularz zawierający:

* imię,
* nazwisko,
* adres e-mail,
* numer telefonu,
* datę urodzenia.

Wymagania:

1. Do każdego pola dodaj `<label>`.
2. Każdy `<label>` połącz z odpowiednim polem za pomocą `for` i `id`.
3. Zastosuj odpowiednie typy `input`.

### Cel ćwiczenia

Nauczenie się tworzenia podstawowych pól formularza i prawidłowego stosowania `<label>`.

\---

## Ćwiczenie 2 – lista rozwijana

Utwórz formularz zawierający listę rozwijaną z wyborem województwa.

Lista powinna zawierać co najmniej 8 województw.

Wykorzystaj:

```html
<select>
```

oraz:

```html
<option>
```

### Zadanie dodatkowe

Ustaw województwo pomorskie jako domyślnie wybrane.

\---

## Ćwiczenie 3 – wybór wielu elementów

Utwórz listę zainteresowań:

* programowanie,
* muzyka,
* sport,
* fotografia,
* podróże,
* książki.

Użytkownik powinien mieć możliwość wybrania **więcej niż jednej pozycji**.

Wykorzystaj:

```html
<select multiple>
```

\---

## Ćwiczenie 4 – wiadomość

Utwórz pole umożliwiające wpisanie wiadomości.

Pole powinno:

* mieć 6 widocznych wierszy,
* mieć około 50 znaków szerokości,
* posiadać etykietę „Wiadomość”.

Wykorzystaj `<textarea>`.

\---

## Ćwiczenie 5 – grupowanie formularza

Utwórz formularz rejestracyjny podzielony na dwie grupy:

### Dane osobowe

* imię,
* nazwisko,
* data urodzenia.

### Dane kontaktowe

* e-mail,
* telefon,
* miasto.

Wykorzystaj:

```html
<fieldset>
```

oraz:

```html
<legend>
```

\---

## Ćwiczenie 6 – lista propozycji

Utwórz pole „Wybierz język programowania”.

Użytkownik powinien móc wpisać własną wartość, ale jednocześnie otrzymywać propozycje:

* HTML,
* CSS,
* JavaScript,
* Python,
* C++,
* Java.

Wykorzystaj:

```html
<input list="...">
```

oraz:

```html
<datalist>
```

\---

## Ćwiczenie 7 – formularz zamówienia

Utwórz formularz zamówienia produktu.

Formularz powinien zawierać:

* imię i nazwisko,
* e-mail,
* wybór produktu,
* liczbę sztuk,
* sposób dostawy,
* dodatkowe uwagi,
* przycisk „Zamów”,
* przycisk „Wyczyść”.

Wykorzystaj co najmniej:

* `<input>`,
* `<label>`,
* `<select>`,
* `<option>`,
* `<textarea>`,
* `<button>`,
* `<fieldset>`,
* `<legend>`.

\---

## Ćwiczenie 8 – obliczenie

Utwórz formularz obliczający cenę produktu.

Formularz powinien zawierać:

* cenę produktu,
* liczbę sztuk,
* wynik końcowy.

Wykorzystaj element:

```html
<output>
```

### Wskazówka

Możesz wykorzystać zdarzenie:

```html
oninput
```

oraz prostą operację:

```javascript
cena \* ilosc
```

\---

# 15\. Zadanie projektowe

## Projekt – Formularz rejestracyjny użytkownika

Stwórz kompletny formularz rejestracyjny.

Formularz powinien zawierać:

### Dane użytkownika

* imię,
* nazwisko,
* e-mail,
* hasło,
* datę urodzenia.

### Adres

* ulica,
* numer domu,
* kod pocztowy,
* miasto,
* województwo.

### Dodatkowe informacje

* zainteresowania,
* preferowany język programowania,
* krótki opis użytkownika.

### Przyciski

* **Zarejestruj**
* **Wyczyść**

### Wymagania techniczne

W projekcie należy zastosować co najmniej:

* `<form>`,
* `<input>`,
* `<label>`,
* `<select>`,
* `<option>`,
* `<textarea>`,
* `<button>`,
* `<fieldset>`,
* `<legend>`,
* `<datalist>`.

\---

# 16\. Pytania kontrolne

1. Do czego służy element `<form>`?
2. Jakie zastosowanie ma `<input>`?
3. Dlaczego warto stosować `<label>`?
4. Jak połączyć `<label>` z polem `<input>`?
5. Do czego służy `<select>`?
6. Jak definiujemy pojedynczą opcję w `<select>`?
7. Do czego służy atrybut `selected`?
8. Do czego służy `multiple`?
9. Kiedy wykorzystujemy `<textarea>`?
10. Co określają `rows` i `cols`?
11. Do czego służy `<button>`?
12. Dlaczego warto określać `type` przy `<button>`?
13. Do czego służy `<fieldset>`?
14. Jaką funkcję pełni `<legend>`?
15. Do czego służy `<datalist>`?
16. Jak połączyć `<input>` z `<datalist>`?
17. Do czego służy `<output>`?
18. Do czego służy `<optgroup>`?

\---

# 17\. Zadanie sprawdzające

Uzupełnij brakujący kod:

```html
<form>

    <label for="\_\_\_\_\_\_">Imię:</label>
    <input type="\_\_\_\_\_\_" id="\_\_\_\_\_\_" name="imie">

    <br><br>

    <label for="miasto">Miasto:</label>

    <select id="miasto" name="miasto">
        <option value="gdansk">Gdańsk</option>
        <option value="gdynia">Gdynia</option>
        <option value="sopot">Sopot</option>
    </select>

    <br><br>

    <label for="wiadomosc">Wiadomość:</label>

    <textarea
        id="wiadomosc"
        name="wiadomosc"
        rows="5"
        cols="40"></textarea>

    <br><br>

    <button type="\_\_\_\_\_\_">Wyślij</button>

</form>
```

### Zadanie

Uzupełnij wszystkie miejsca oznaczone `\_\_\_\_\_\_` tak, aby formularz działał prawidłowo.

\---

# 18\. Najważniejsze informacje do zapamiętania

> \*\*`<form>`\*\* – kontener formularza.

> \*\*`<input>`\*\* – pole do wprowadzania danych.

> \*\*`<label>`\*\* – opis pola formularza.

> \*\*`<select>`\*\* – lista rozwijana.

> \*\*`<option>`\*\* – pojedyncza opcja listy.

> \*\*`<textarea>`\*\* – wieloliniowe pole tekstowe.

> \*\*`<button>`\*\* – przycisk.

> \*\*`<fieldset>`\*\* – grupa powiązanych pól.

> \*\*`<legend>`\*\* – opis grupy `<fieldset>`.

> \*\*`<datalist>`\*\* – lista podpowiedzi dla pola wejściowego.

> \*\*`<output>`\*\* – wynik obliczenia.

> \*\*`<optgroup>`\*\* – grupa opcji w `<select>`.

\---

## 

