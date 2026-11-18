# Lekcja 10. Scalanie komórek tabeli. Zadanie w stylu egzaminu

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- scalać komórki w poziomie i w pionie,
- zaplanować tabelę ze scalonymi komórkami na podstawie rysunku,
- wykonać zadanie sformułowane jak na egzaminie INF.03.

## Wprowadzenie

| Atrybut | Działanie | Przykład |
|---|---|---|
| `colspan="n"` | komórka zajmuje **n kolumn** (w poziomie) | `<td colspan="2">` |
| `rowspan="n"` | komórka zajmuje **n wierszy** (w pionie) | `<td rowspan="3">` |

```text
+-----------+-----------+
|   Imię i nazwisko     |   <- jedna komórka, colspan="2"
+-----------+-----------+
|  Jan      | Kowalski  |
+-----------+-----------+
```

```text
+--------+-----------+
|        | Polski    |
| Środa  +-----------+   <- "Środa": rowspan="2"
|        | Fizyka    |
+--------+-----------+
```

!!! tip "Metoda: licz komórki w wierszach"
    1. Narysuj tabelę na kartce i policz, ile kolumn ma najszerszy wiersz.
    2. Komórka z `rowspan` „zabiera” miejsce w wierszach poniżej. W tych wierszach piszesz o jedną komórkę `td` **mniej**.
    3. Suma komórek w każdym wierszu (licząc `colspan` i komórki „zabrane” przez `rowspan` z góry) musi być taka sama.

## Zadanie główne (25 min)

!!! note "Polecenie (styl arkusza INF.03)"
    Utwórz stronę internetową `plan.html`. Tytuł widoczny na karcie przeglądarki: **Plan zajęć dodatkowych**. Strona zawiera nagłówek pierwszego stopnia o treści **Zajęcia dodatkowe – semestr zimowy** oraz tabelę zgodną z rysunkiem 1.

    W sekcji `head` umieść styl obramowania tabeli: `table, th, td { border: 1px solid black; border-collapse: collapse; padding: 6px; }`

```text
Rysunek 1. Tabela do odwzorowania

+------------+---------------------------+-------------+
|  Dzień     |  Zajęcia                  |  Sala       |   <- komórki nagłówkowe th
+------------+---------------------------+-------------+
|            |  Koło informatyczne       |  12         |
| Poniedział.+---------------------------+-------------+
|            |  Szkolny klub filmowy     |  Aula       |
+------------+---------------------------+-------------+
|  Wtorek    |  Siatkówka                |  Hala       |
+------------+---------------------------+-------------+
|            |  Grafika komputerowa      |             |
|  Środa     +---------------------------+  14         |
|            |  Montaż wideo             |             |
+------------+---------------------------+-------------+
|  Czwartek  |  Brak zajęć – wycieczka klasowa         |
+------------+-----------------------------------------+
|  Liczba zajęć w tygodniu: 5                           |   <- stopka tfoot
+-------------------------------------------------------+
```

Wymagania:

1. Tabela ma tytuł `caption`: **Plan na listopad 2026**.
2. Pierwszy wiersz zawiera komórki nagłówkowe, umieszczone w `thead`.
3. Komórki z nazwami dni tygodnia są komórkami nagłówkowymi `th`.
4. Scalenia komórek dokładnie jak na rysunku 1.
5. Ostatni wiersz znajduje się w stopce tabeli `tfoot`.
6. Kod jest poprawny w walidatorze W3C, a wcięcia czytelne.

Masz **20 minut**. Ostatnie 5 minut: sprawdzenie w parach. Zamieńcie się miejscami i sprawdźcie pracę kolegi lub koleżanki z listą wymagań 1–6.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Odwzoruj fragment planu lekcji swojej klasy (2 dni) z wykorzystaniem `colspan` dla lekcji dwugodzinnych i `rowspan` dla przerw obiadowych. Ustal z nauczycielem, jak ma wyglądać wzór.

## Czy potrafię…?

- [ ] scalić komórki w poziomie (`colspan`)
- [ ] scalić komórki w pionie (`rowspan`)
- [ ] policzyć, ile komórek `td` napisać w wierszu pod komórką z `rowspan`
- [ ] odwzorować tabelę z rysunku w zadaniu egzaminacyjnym
