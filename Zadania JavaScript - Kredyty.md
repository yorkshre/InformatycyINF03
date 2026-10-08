# Ćwiczenia JavaScript: Instrukcje warunkowe i Operator Trójskładnikowy (Tematyka Kredytowa)

Ten zestaw zadań pozwala przećwiczyć logikę decyzyjną oraz operator trójskładnikowy w kontekście systemów finansowych i bankowych (np. ocena zdolności kredytowej).

---

## Zadanie 1: Sprawdzenie zdolności kredytowej (`if...else`)

**Treść:**
Napisz skrypt w JavaScript, który ocenia, czy klient może otrzymać kredyt hipoteczny. 

1. Zdefiniuj następujące zmienne:
   * `zarobki` (np. `5000`)
   * `miesieczneWydatki` (np. `2000`)
   * `historiaKredytowa` (`true` dla dobrej historii, `false` dla złej)
2. Oblicz dochód rozporządzalny jako różnicę zarobków i wydatków.
3. Za pomocą rozbudowanej instrukcji `if...else` sprawdź warunki:
   * Jeśli historia kredytowa jest zła (`false`), wypisz w konsoli: `"Kredyt odrzucony: zła historia kredytowa."`
   * Jeśli historia jest dobra, ale dochód rozporządzalny jest mniejszy niż `2500`, wypisz: `"Kredyt odrzucony: zbyt niska zdolność kredytowa."`
   * W każdym innym przypadku wypisz: `"Gratulacje! Kredyt został wstępnie zatwierdzony."`

---

## Zadanie 2: Oprocentowanie pożyczki (Operator trójskładnikowy)

**Treść:**
Stwórz skrypt obliczający oprocentowanie pożyczki gotówkowej.

1. Zdefiniuj zmienną `kwotaKredytu` (np. `60000`).
2. Użyj **operatora trójskładnikowego**, aby przypisać odpowiednie oprocentowanie do zmiennej `oprocentowanie`:
   * Jeśli kwota kredytu jest większa niż `50000`, oprocentowanie wynosi `7.5`.
   * W przeciwnym razie oprocentowanie wynosi `9.0`.
3. Wyświetl w konsoli komunikat w formacie szablonu tekstu (template literal): 
   `"Przy wnioskowanej kwocie oprocentowanie wynosi: [wartość]%"`

---

## Zadanie 3: Status wniosku i zagnieżdżony operator trójskładnikowy

**Treść:**
Napisz skrypt symulujący automatyczną decyzję systemową na podstawie punktacji w BIK.

1. Zdefiniuj zmienną `punktyBik` (np. `650`).
2. Użyj **zagnieżdżonego operatora trójskładnikowego**, aby przypisać do zmiennej `status` odpowiedni komunikat:
   * Jeśli punkty są większe lub równe `700`: `"Szybka ścieżka (akceptacja automatyczna)"`
   * Jeśli punkty są w przedziale od `550` do `699`: `"Wymagana weryfikacja analityka"`
   * Poniżej `550`: `"Odrzucone automatycznie"`
3. Wyświetl wynik w konsoli.
```
