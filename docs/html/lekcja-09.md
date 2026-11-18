# Lekcja 9. Tabele

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować tabelę z wierszy i komórek,
- oznaczyć komórki nagłówkowe,
- dodać tytuł tabeli,
- podzielić tabelę na nagłówek, treść i stopkę.

## Wprowadzenie

Tabela służy do pokazywania **danych w wierszach i kolumnach**: wyników, cenników, planów. Nie używa się jej do układania wyglądu strony.

```html
<table>
    <caption>Wyniki szkolnego turnieju</caption>
    <thead>
        <tr>
            <th>Miejsce</th>
            <th>Drużyna</th>
            <th>Punkty</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>2TP</td>
            <td>15</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="3">Stan na 18.11.2026</td>
        </tr>
    </tfoot>
</table>
```

| Znacznik | Znaczenie |
|---|---|
| `table` | cała tabela |
| `caption` | tytuł tabeli (zaraz po `<table>`) |
| `tr` | wiersz (*table row*) |
| `th` | komórka nagłówkowa (*table header*), domyślnie pogrubiona i wyśrodkowana |
| `td` | zwykła komórka (*table data*) |
| `thead`, `tbody`, `tfoot` | grupy wierszy: nagłówek, treść, stopka |

!!! info "Obramowanie tabeli"
    Domyślnie tabela nie ma krawędzi. Dopóki nie poznamy CSS, wklej do sekcji `head` ten fragment:

    ```html
    <style>
        table, th, td { border: 1px solid black; border-collapse: collapse; padding: 4px; }
    </style>
    ```

## Zadanie główne (25 min)

Utwórz stronę `tabele.html` (tytuł karty: **Tabele**) z obramowaniem tabel jak w ramce powyżej.

**Tabela 1. Plan dnia**

1. Tytuł tabeli: **Mój plan dnia**.
2. Kolumny: **Godzina**, **Zajęcie**, **Miejsce**. Komórki nagłówkowe w `thead`.
3. Co najmniej 5 wierszy danych w `tbody`.

**Tabela 2. Cennik** (dane z pliku [cennik.txt](../pliki/lekcja-09/cennik.txt){ download })

1. Tytuł tabeli: **Cennik kawiarni szkolnej**.
2. Kolumny: **Produkt**, **Rozmiar**, **Cena [zł]**.
3. Nazwy produktów w pierwszej kolumnie mają być komórkami nagłówkowymi `th` (nagłówki wierszy).
4. W stopce tabeli (`tfoot`) umieść wiersz: **Ceny zawierają VAT** w pierwszej komórce i dwie puste komórki.
5. Sprawdź stronę w walidatorze W3C.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do komórek nagłówkowych atrybut `scope="col"` (kolumny) lub `scope="row"` (wiersze). Dowiedz się, komu ten atrybut pomaga i dlaczego.

## Czy potrafię…?

- [ ] zbudować tabelę z nagłówkiem i wierszami danych
- [ ] wyjaśnić różnicę między `th` a `td`
- [ ] dodać tytuł tabeli
- [ ] podzielić tabelę na `thead`, `tbody` i `tfoot`
