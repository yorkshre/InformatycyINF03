# Instrukcja wykonania zadania praktycznego (Arkusz INF.03)
## Projekt: Gen Z Slang Translator

---

## 1. Struktura i znaczniki (Plik `index.html`)

* **Struktura dokumentu:** Utwórz plik HTML5 z poprawnym nagłówkiem (`<!DOCTYPE html>`, sekcja `<head>` z kodowaniem `UTF-8` i znacznikiem `viewport`).
* **Sekcje semantyczne:** Wewnątrz elementu `<body>` zaplanuj:
  * Nagłówek strony (`<header>`) zawierający główny tytuł aplikacji oraz podtytuł.
  * Blok szybkiego wyboru (`<section>`) z elementami (tagami) do szybkiego wstawiania predefiniowanych słów.
  * Formularz lub sekcję interaktywną (`<section class="card">`) zawierającą etykietę (`<label>`), wielowierszowe pole tekstowe (`<textarea>`) oraz przycisk wyzwalający akcję (`<button>`).
  * Sekcję wyników (`<section>`) z kontenerem (`<div>`) posiadającym unikalny identyfikator (np. `id="outputContent"`), w którym będą wyświetlane rezultaty działania skryptu.
* **Powiązania:** Dołącz arkusz stylów CSS oraz plik skryptu JavaScript w odpowiednich miejscach dokumentu.

---

## 2. Stylizacja, wygląd i wymagania dotyczące kolorów (Plik `style.css`)

### Zmienne globalne w sekcji `:root` (Ścisła paleta kolorów)
Zdefiniuj w bloku `:root` następujące zmienne kolorystyczne i stosuj je konsekwentnie w całym arkuszu:
* `--bg-color: #0d0d0d;` – głębokie, ciemne tło strony
* `--card-bg: #161616;` – nieco jaśniejszy odcień tła dla kontenerów/kart
* `--accent-green: #CCFF00;` – jaskrawa, neonowa zieleń jako główny kolor akcentu i przycisków
* `--accent-pink: #FF007F;` – intensywny neonowy róż do cieni i wyróżnień tagów
* `--accent-cyan: #00F0FF;` – neonowy błękit/cyjan do obramowań i podpowiedzi
* `--text-color: #F0F0F0;` – jasny, niemal biały kolor dla czytelności tekstu podstawowego
* `--border-color: #FFFFFF;` – czysta biel dla grubych, wyrazistych ramek elementów

### Układ i ostylowanie elementów
* **Element `<body>`:** Ustaw jako tło zmienną `--bg-color`, a jako kolor tekstu `--text-color`.
* **Kontenery (Karty):** Zaprojektuj z grubymi ramkami o szerokości minimum `3px` w kolorze `--border-color` oraz z przesuniętymi, ostrymi cieniami (np. `box-shadow: 5px 5px 0px var(--accent-green)` lub `--accent-pink`).
* **Pole tekstowe (`textarea`):** Musi posiadać czarne tło (`#000000`), ramkę o grubości `2px` w kolorze `--border-color` oraz tekst w kolorze `--text-color`. W stanie `:focus` ramka powinna zmieniać kolor na `--accent-pink`.
* **Przycisk (`button`):** Musi mieć tło w kolorze `--accent-green`, czarny kolor napisu (`#000000`), grubą ramkę `--border-color` oraz widoczny cień. Po najechaniu kursorem (`:hover`) tło przycisku musi zmieniać się na `--accent-cyan`.
* **Tagi szybkiego wyboru:** Powinny mieć czarne tło, ramkę `--border-color`, cień w kolorze `--accent-pink`, a po najechaniu (`:hover`) zmieniać tło na `--accent-pink` przy jednoczesnej zmianie koloru tekstu na czarny.
* **Sekcja wyników:** Kontener wynikowy powinien posiadać czarne tło oraz ramkę w stylu linii przerywanej (*dashed*) o grubości `2px` w kolorze `--accent-cyan`.

---

## 3. Logika i działanie skryptu (Plik `script.js`)

* **Obsługa tagów szybkiego wyboru:** 
  * Napisz funkcję (np. `selectTag(text)`), która przyjmuje przekazany ciąg znaków i automatycznie wstawia go jako wartość do pola tekstowego (`textarea`), odwołując się do elementu poprzez jego identyfikator.
* **Walidacja formularza i przetwarzanie:**
  * Utwórz główną funkcję wywoływaną po kliknięciu przycisku (np. `handleTranslate()`).
  * Pobierz wartość z pola tekstowego i zastosuj metodę `.trim()` w celu usunięcia zbędnych spacji.
  * Zaimplementuj instrukcję warunkową (`if`) sprawdzającą, czy pole nie jest puste. W przypadku wykrycia pustego pola, wyświetl komunikat o błędzie (np. z użyciem koloru `--accent-pink` lub `#FF007F`) i przerwij działanie skryptu.
* **Generowanie i wyświetlanie wyniku:**
  * W przypadku prawidłowych danych, wstaw sformatowany rezultat do kontenera wyników za pomocą właściwości `innerHTML`.
