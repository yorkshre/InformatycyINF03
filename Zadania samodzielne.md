# 20 zaawansowanych zadań z JavaScript: Instrukcje warunkowe i operator trójargumentowy

Ten zestaw zawiera 20 trudnych, skomplikowanych logicznie zadań przeznaczonych dla osób, które chcą przetestować swoją wiedzę z zakresu instrukcji warunkowych oraz operatora trójargumentowego w JavaScript. Zadania nie zawierają rozwiązań i opierają się na realistycznych, złożonych scenariuszach biznesowych, systemach walidacji, logice kalendarzowej oraz wielopoziomowych regułach.

---

### 1. Dynamiczny system rabatów lojalnościowych
Napisz skrypt obliczający ostateczną cenę koszyka klienta w sklepie internetowym. 
* **Reguły:**
  - Jeśli wartość koszyka przekracza 500 zł, klient otrzymuje 10% rabatu. Jeśli przekracza 1000 zł, rabat wynosi 20%.
  - Dodatkowo, jeśli klient jest zarejestrowany **i** posiada status VIP, otrzymuje dodatkowe 5% rabatu (sumuje się z podstawowym).
  - Jeśli koszyk zawiera produkt oznaczony jako "gabarytowy", a wartość zamówienia (po rabatach) jest mniejsza niż 300 zł, naliczana jest opłata kurierska w wysokości 50 zł. W przeciwnym razie dostawa jest darmowa.
* **Dane wejściowe do przetestowania logiki:** `wartoscKoszyka`, `czyZarejestrowany`, `czyVip`, `czyGabaryt`.

### 2. Zaawansowana walidacja hasła użytkownika
Stwórz logikę sprawdzającą siłę hasła według restrykcyjnych reguł bezpieczeństwa.
* **Reguły:**
  - Hasło musi mieć co najmniej 10 znaków.
  - Musi zawierać przynajmniej jedną wielką literę, jedną małą literę, jedną cyfrę oraz jeden znak specjalny (`!@#$%^&*`).
  - Hasło **nie może** zawierać słowa "password" ani "admin" (ignorując wielkość liter).
  - Jeśli spełnia wszystkie warunki, zwróć "Silne hasło". Jeśli brakuje tylko znaku specjalnego lub długości (ale ma >= 8 znaków), zwróć "Średnie hasło". W każdym innym przypadku zwróć "Słabe hasło".

### 3. Automatyczny kalendarz: Rok przestępny i dzień tygodnia
Napisz program, który na podstawie podanego dnia, miesiąca i roku sprawdza poprawność daty, uwzględniając lata przestępne (rok podzielny przez 4, ale nie przez 100, chyba że przez 400). Następnie, dla poprawnej daty, określ, czy dany dzień przypada na weekend czy dzień roboczy (użyj wyłącznie zagnieżdżonych `if` lub rozbudowanych warunków logicznych).

### 4. Inteligentny algorytm przydzielania miejsc w pociągu
Napisz system rezerwacji miejsc w wagonie przedziałowym (przedziały 6-osobowe: miejsca od 1 do 6, gdzie 1 i 6 to okno, 2 i 5 to środek, 3 i 4 to korytarz).
* **Reguły:**
  - Pasażer może wybrać preferencję: `"okno"`, `"korytarz"` lub `"obojętnie"`.
  - Jeśli wolne jest preferowane miejsce, przydziel je.
  - Jeśli preferowane miejsce jest zajęte, ale dostępne jest inne w tej samej kategorii (np. inne okno), przydziel je.
  - Jeśli w wybranym przedziale nie ma miejsc spełniających kryteria, sprawdź czy pasażer zgadza się na zmianę przedziału; jeśli tak, przydziel pierwsze wolne miejsce w sąsiednim przedziale, w przeciwnym razie odrzuć rezerwację.

### 5. Algorytm obliczania podatku dochodowego (Skala podatkowa z progami)
Napisz skrypt symulujący dwustopniową skalę podatkową:
* **Reguły:**
  - Pierwszy próg: dochód do 120 000 zł rocznie jest opodatkowany stawką 12% (od nadwyżki ponad kwotę wolną od podatku, np. 30 000 zł, przy czym kwota wolna maleje przy wysokich zarobkach – uprośćmy: stała ulga podatkowa 3600 zł dla dochodu do 120k).
  - Drugi próg: nadwyżka ponad 120 000 zł jest opodatkowana stawką 32%.
  - Dodatkowo, jeśli podatnik rozlicza się samotnie **i** jego roczny dochód mieści się w przedziale [80 000, 100 000], przysługuje mu specjalna ulga pomniejszająca podatek o 1500 zł. Oblicz ostateczny podatek do zapłaty.

### 6. Symulator systemu alarmowego inteligentnego domu
Napisz logikę sterującą stanem uzbrojenia alarmu domowego.
* **Reguły:**
  - Alarm można uzbroić w trybie "Pełnym" lub "Nocnym".
  - W trybie "Pełnym" naruszenie *jakiegokolwiek* czujnika (ruch, okno, drzwi) natychmiast wyzwala syrenę.
  - W trybie "Nocnym" naruszenie czujnika ruchu w strefie dziennej jest ignorowane, ale naruszenie czujnika okna lub drzwi na parterze wyzwala syrenę po 15-sekundowym opóźnieniu na wpisanie kodu PIN.
  - Jeśli wprowadzono poprawny PIN w czasie opóźnienia, alarm nie wyje; w przeciwnym razie włącza się pełna syrena i wysyłane jest powiadomienie do agencji ochrony.

### 7. Automatyczny system doboru opon samochodowych
Napisz program rekomendujący zmianę opon na podstawie warunków pogodowych i typu pojazdu.
* **Reguły:**
  - Jeśli średnia dobowa temperatura spada poniżej 7°C **lub** występuje ryzyko gołoledzi, opony letnie muszą być zmienione na zimowe.
  - Wyjątek: Samochody dostawcze o masie > 3.5 tony muszą posiadać opony zimowe niezależnie od temperatury, jeśli kalendarz wskazuje miesiące od października do marca.
  - Jeśli temperatura przekracza 25°C, a pojazd to samochód sportowy użytkowany na torze, system sugeruje opony typu semi-slick, chyba że pada deszcz (wtedy rekomenduje opony deszczowe).

### 8. Kalkulator dopuszczalnego obciążenia kredytowego (Zdolność kredytowa)
Stwórz skrypt oceniający wniosek o kredyt hipoteczny.
* **Reguły:**
  - Łączny dochód gospodarstwa domowego minus stałe wydatki musi dawać kwotę wolną (dochód rozporządzalny) wyższą niż rata kredytu pomnożona przez współczynnik ryzyka.
  - Współczynnik ryzyka wynosi 1.2 dla stałej stopy oprocentowania i 1.5 dla zmiennej stopy.
  - Jeśli wniosek składa jedna osoba, jej wiek w momencie spłaty ostatniej raty nie może przekraczać 70 lat; dla par limit ten wynosi 75 lat dla starszej osoby.
  - Dodatkowo, historia w BIK musi być "bardzo dobra", chyba że wkład własny przekracza 40% – wtedy dopuszczalna jest historia "dobra".

### 9. Algorytm wyznaczania wygranej w uproszczonej grze karcianej (Blackjack/Oczko)
Napisz logikę porównującą karty gracza i krupiera.
* **Reguły:**
  - As liczy się jako 11 lub 1 (wybierz korzystniejszą opcję dla gracza, tak aby nie przekroczyć 21 punktów).
  - Jeśli suma gracza przekracza 21 ("faule"), gracz przegrywa automatycznie.
  - Jeśli gracz ma dokładnie 21 punktów z dwóch kart ("Blackjack"), wygrywa, chyba że krupier też ma Blackjacka (wtedy remis).
  - W przeciwnym razie wygrywa ten, kto ma bliżej do 21, przy czym przy remisie punktowym wygrywa krupier. Użyj zagnieżdżonych warunków do rozstrzygnięcia wszystkich przypadków.

### 10. Sterownik inteligentnego oświetlenia biurowego
Napisz system zarządzający jasnością i barwą światła w nowoczesnym biurze.
* **Reguły:**
  - Jasność zależy od natężenia światła zewnętrznego (z czujnika) oraz obecności pracowników.
  - Jeśli nikogo nie ma w pomieszczeniu, światło jest wyłączone (0%).
  - Jeśli ktoś jest, a światło zewnętrzne jest mniejsze niż 300 luksów, sztuczne oświetlenie uzupełnia brakującą pulę do poziomu 500 luksów.
  - Wyjątek: Jeśli jest po godzinie 18:00 lub w weekend, system przełącza barwę na ciepłą i ogranicza maksymalną jasność do 30% niezależnie od warunków zewnętrznych, chyba że włączony jest tryb "Praca nocna".

### 11. Walidator harmonogramu spotkań (Wykrywanie konfliktów)
Napisz program sprawdzający, czy nowo planowane spotkanie w kalendarzu nie koliduje z istniejącymi rezerwacjami sal konferencyjnych.
* **Reguły:**
  - Istnieje spotkanie A o godzinie początkowej $S_1$ i końcowej $E_1$. Nowe spotkanie B ma godziny $S_2$ i $E_2$.
  - Konflikt występuje, gdy nowe spotkanie zaczyna się przed końcem starego i kończy się po początku starego ($S_2 < E_1$ oraz $E_2 > S_1$).
  - Dodatkowo uwzględnij 15-minutowy bufor techniczny na przewietrzenie sali, który musi być doliczony do każdego spotkania. Jeśli sala jest rezerwowana bezpośrednio po innej, konflikt występuje ze względu na brak czasu na przygotowanie.

### 12. System awansów i premii w korporacji
Napisz algorytm decydujący o przyznaniu rocznej premii i awansu pracownikowi.
* **Reguły:**
  - Warunek konieczny do awansu: ocena roczna menedżera na poziomie min. 4.5/5.0 oraz staż pracy w obecnej roli wynoszący co najmniej 2 lata.
  - Jeśli pracownik nie spełnia warunku stażu, ale jego ocena wynosi 5.0, może otrzymać awans warunkowy pod warunkiem uzyskania pozytywnej opinii dyrektora działu.
  - Premia finansowa jest obliczana jako % podstawy: 10% przy ocenie >= 4.0, 20% przy ocenie >= 4.5, oraz dodatkowe 5% jeśli projekt kluczowy zakończył się przed czasem.

### 13. System rozliczania nadgodzin w zakładzie pracy
Stwórz skrypt obliczający stawkę za przepracowane godziny w danym dniu.
* **Reguły:**
  - Standardowy dzień roboczy trwa 8 godzin (płatne 100% stawki godzinowej).
  - Pierwsze 2 godziny nadliczbowe są płatne 150% stawki.
  - Każda kolejna godzina ponad 2 godziny nadliczbowe jest płatna 200% stawki.
  - Jeśli praca odbywa się w niedzielę lub święto państwowe, każda godzina jest płatna 200%, a godziny przekraczające 8 godzin są płatne 300%. Wykorzystaj operator trójargumentowy oraz zagnieżdżone warunki.

### 14. Klasyfikacja ryzyka portfela inwestycyjnego
Napisz program przypisujący profil ryzyka inwestorowi na podstawie jego odpowiedzi w ankiecie.
* **Reguły:**
  - Profil może być: Konserwatywny, Zrównoważony, Agresywny.
  - Jeśli horyzont inwestycyjny jest krótszy niż 3 lata, profil automatycznie staje się Konserwatywny, niezależnie od innych odpowiedzi.
  - Jeśli horyzont wynosi 3–7 lat, a akceptacja strat jest niska, profil to Konserwatywny; przy średniej/wysokiej akceptacji strat – Zrównoważony.
  - Jeśli horyzont przekracza 7 lat, a inwestor akceptuje wysokie ryzyko i ma doświadczenie rynkowe > 5 lat, otrzymuje profil Agresywny.

### 15. Algorytm sterowania klimatyzacją w serwerowni
Napisz logikę załączania jednostek chłodzących w serwerowni w zależności od temperatury i wilgotności.
* **Reguły:**
  - Temperatura optymalna to 18-22°C. Wilgotność optymalna to 40-60%.
  - Jeśli temperatura przekroczy 25°C, natychmiast uruchamiany jest drugi stopień chłodzenia (klimatyzator awaryjny).
  - Jeśli wilgotność spadnie poniżej 30% przy temperaturze powyżej 23°C, włączany jest nawilżacz, a główny klimatyzator ogranicza moc o połowę, aby dodatkowo nie wysuszać powietrza.
  - Awaria czujnika głównego (wartość `null` lub poza zakresem fizycznym) wymusza przejście w tryb awaryjny i uruchomienie wentylacji mechanicznej na 100%.

### 16. Walidator poprawności numeru PESEL (Wybrane reguły logiczne)
Napisz program sprawdzający wybrane warunki strukturalne numeru PESEL (w postaci ciągu znaków lub liczby o odpowiedniej długości).
* **Reguły:**
  - Sprawdź, czy długość wynosi dokładnie 11 znaków.
  - Wyciągnij cyfry odpowiedzialne za miesiąc i rok, aby zweryfikować poprawność daty urodzenia (pamiętając o kodowaniu stuleci w numerze miesiąca: np. dodawanie 20, 40, 60 do numeru miesiąca w zależności od roku urodzenia).
  - Określ płeć na podstawie przedostatniej cyfry (parzysta = kobieta, nieparzysta = mężczyzna). Jeśli płeć to kobieta, a wiek przekracza 60 lat, przyznaj status "Senior-K", w przeciwnym razie "Standard".

### 17. System zarządzania ruchem na autostradzie (Zmienne ograniczenia prędkości)
Stwórz logikę ustalającą dynamiczne ograniczenie prędkości na tablicach świetlnych.
* **Reguły:**
  - Standardowy limit to 140 km/h.
  - Jeśli natężenie ruchu przekracza 1500 pojazdów na godzinę, limit spada do 120 km/h. Jeśli przekracza 2500 pojazdów, limit spada do 90 km/h.
  - Jeśli występuje silny wniosek pogodowy (opady deszczu, śnieg lub widzialność poniżej 100 metrów), od standardowego/wyznaczonego limitu odejmuje się dodatkowo 20 km/h.
  - Jeśli na danym odcinku zgłoszono kolizję lub roboty drogowe, niezależnie od warunków ruchowych i pogodowych, maksymalna prędkość zostaje sztywno ograniczona do 50 km/h.

### 18. Zaawansowany kalkulator kosztów przesyłki kurierskiej
Napisz system obliczający koszt wysyłki paczki na podstawie wymiarów, wagi i dodatkowych opcji.
* **Reguły:**
  - Stawka bazowa zależy od wagi (do 2 kg: 15 zł, do 5 kg: 20 zł, powyżej 5 kg: 35 zł).
  - Jeśli którykolwiek z wymiarów paczki (długość, szerokość, wysokość) przekracza 60 cm, paczka traktowana jest jako "niestandardowa", co dolicza 20 zł do kosztu.
  - Jeśli suma wymiarów (dł + szer + wys) przekracza 150 cm, doliczane jest kolejne 30 zł ("gabaryt XXL").
  - Opcje dodatkowe: ubezpieczenie (kosztuje 5 zł dla wartości przedmiotu do 1000 zł lub 15 zł powyżej) oraz przesyłka pobraniowa COD (dodatkowe 10 zł), przy czym opcja COD jest niedostępna dla przesyłek o wartości powyżej 5000 zł (wtedy należy zwrócić błąd walidacji).

### 19. Algorytm przydzielania sali operacyjnej w szpitalu
Napisz logikę decydującą o priorytecie i przydziale sali operacyjnej dla pacjentów trafiających na SOR.
* **Reguły:**
  - Priorytety: Triage Czerwony (zagrożenie życia), Żółty (pilny), Zielony (stabilny).
  - Pacjent z Triage Czerwonym natychmiast otrzymuje wolną salę operacyjną. Jeśli wszystkie sale są zajęte, system analizuje czas trwania trwających operacji: jeśli jakaś operacja jest w fazie zamykania (ostatnie 15 minut) i nie jest to inny przypadek Czerwony, operacja ta jest kontynuowana, ale w skrajnym zagrożeniu życia zarządzane jest natychmiastowe wstrzymanie mniej krytycznego zabiegu.
  - Pacjent z Triage Żółtym czeka w kolejce, chyba że w ciągu 30 minut jego stan nie ulegnie pogorszeniu; w przeciwnym razie jego priorytet rośnie. Użyj zagnieżdżonych struktur decyzyjnych.

### 20. Automatyczny system taryfowy komunikacji miejskiej (Bilet czasowy / Odległościowy)
Napisz skrypt obliczający optymalną cenę przejazdu dla pasażera na podstawie liczby przejechanych przystanków oraz czasu podróży.
* **Reguły:**
  - Przejazd do 3 przystanków kosztuje 3.40 zł (bilet krótkoookresowy).
  - Przejazd od 4 do 10 przystanków kosztuje 5.20 zł.
  - Powyżej 10 przystanków włącza się taryfa odległościowa, gdzie każdy dodatkowy przystanek kosztuje 0.60 zł, ale łączna cena nie może przekroczyć ceny biletu dobowego (18.00 zł).
  - Dodatkowo, jeśli pasażer korzysta z karty miejskiej **i** podróż odbywa się w godzinach szczytu (7:00–9:00 lub 16:00–18:00), otrzymuje 15% zniżki lojalnościowej, chyba że przekroczono limit biletowy dzienny (wtedy płaci stałą stawkę maksymalną).
```eof
