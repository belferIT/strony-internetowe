# Lekcja 60. Sprawdzian praktyczny: JavaScript

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Zasady

- Czas: **40 minut** na pracę, 5 minut na przygotowanie i oddanie.
- Możesz korzystać z dokumentacji [MDN](https://developer.mozilla.org/pl/) i konsoli przeglądarki. Nie możesz korzystać z narzędzi AI, materiałów z lekcji ani pomocy innych osób.
- Strona HTML i style są gotowe. Piszesz tylko skrypt.
- Pracę oddajesz jako spakowany folder `Nazwisko_Imie`.

## Materiały

Pobierz [silownia.html](../pliki/lekcja-60/silownia.html){ download }. Nie zmieniaj w nim nic poza dołączeniem skryptu.

## Zadanie

!!! note "Polecenie"
    Utwórz skrypt `skrypt.js` obsługujący kalkulator karnetu na siłownię.

**Część 1. Kalkulator (grupa A i B).** Po kliknięciu przycisku **Oblicz** skrypt:

1. Pobiera rodzaj karnetu z listy `karnet` (wartość opcji to cena za miesiąc).
2. Pobiera liczbę miesięcy z pola `miesiace`.
3. Jeśli liczba miesięcy nie mieści się w zakresie 1–12, wypisuje w akapicie `wynik` tekst **Liczba miesięcy musi być od 1 do 12** i kończy działanie.
4. Oblicza koszt: cena × liczba miesięcy.
5. Rabat zależny od liczby miesięcy:

    | | Grupa A | Grupa B |
    |---|---|---|
    | 6–11 miesięcy | 10% | 5% |
    | 12 miesięcy | 20% | 15% |

6. Jeśli zaznaczone jest pole `trener`, dolicza **50 zł** za każdy miesiąc (bez rabatu).
7. Jeśli wybrany jest przycisk radio `status` o wartości `uczen`, odejmuje od całości **30 zł**.
8. Wypisuje w akapicie `wynik`: **Koszt karnetu: X zł** (dwa miejsca po przecinku).

**Część 2. Interakcja.**

- **Grupa A:** po najechaniu kursorem na dowolny wiersz tabeli cennika `#cennik` wiersz dostaje klasę `podswietl`, a po zjechaniu ją traci.
- **Grupa B:** kliknięcie przycisku **Pokaż regulamin** przełącza widoczność akapitu `#regulamin` (klasa `ukryty`) i zmienia napis przycisku na **Ukryj regulamin** / **Pokaż regulamin**.

## Dane testowe (grupa A)

| Karnet | Miesiące | Trener | Status | Wynik |
|---|---|---|---|---|
| Standard (99 zł) | 1 | nie | normalny | 99.00 zł |
| Standard (99 zł) | 6 | tak | uczeń | 804.60 zł |
| Premium (149 zł) | 12 | nie | normalny | 1430.40 zł |
| dowolny | 13 | – | – | komunikat o błędzie |

## Kryteria oceny (20 pkt)

| Kryterium | Punkty |
|---|---|
| Obsługa kliknięcia przycisku | 2 |
| Poprawny odczyt listy, pola liczbowego, checkboxa i radia | 4 |
| Sprawdzenie zakresu miesięcy z komunikatem | 2 |
| Poprawne obliczenia: rabat, trener, zniżka uczniowska | 6 |
| Wynik w podanym formacie | 2 |
| Część 2 | 3 |
| Czytelny kod: nazwy zmiennych, wcięcia, brak błędów w konsoli | 1 |

Progi ocen ustala nauczyciel zgodnie z WSO.
