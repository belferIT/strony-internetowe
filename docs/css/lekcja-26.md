# Lekcja 26. Stylowanie tabel

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- ustawić obramowanie tabeli i scalić krawędzie komórek,
- wyrównać zawartość komórek w poziomie i w pionie,
- wyróżnić nagłówek, wiersze naprzemienne i wiersz pod kursorem.

## Wprowadzenie

```css
table {
    border-collapse: collapse;   /* jedna linia zamiast podwójnej */
    width: 100%;
}
th, td {
    border: 1px solid #b0bec5;
    padding: 8px;
}
th { background-color: #455a64; color: white; }
tr:nth-child(even) { background-color: #eceff1; }
tr:hover { background-color: #fff9c4; }
```

| Właściwość | Wartości | Działanie |
|---|---|---|
| `border-collapse` | `separate`, `collapse` | oddzielne lub wspólne krawędzie komórek |
| `border-spacing` | `5px` | odstęp między komórkami (gdy `separate`) |
| `text-align` | `left`, `center`, `right` | wyrównanie poziome |
| `vertical-align` | `top`, `middle`, `bottom` | wyrównanie pionowe w komórce |
| `caption-side` | `top`, `bottom` | położenie tytułu tabeli |

!!! tip "Liczby do prawej"
    Kolumny z liczbami (ceny, wyniki) wyrównuje się do prawej, żeby cyfry jedności były jedna pod drugą. Możesz wybrać ostatnią kolumnę selektorem `td:last-child`.

## Zadanie główne (25 min)

Pobierz [cennik.html](../pliki/lekcja-26/cennik.html){ download } (tabela z lekcji 9). Utwórz `styl.css` i dołącz go.

1. Tabela: szerokość 600px, wyśrodkowana na stronie, scalone krawędzie, czcionka `Verdana`.
2. Wszystkie komórki: obramowanie 1px ciągłe `#bdbdbd`, margines wewnętrzny 10px.
3. Tytuł tabeli: pod tabelą, kursywa, kolor `#757575`, margines górny 8px.
4. Wiersz nagłówka (`thead th`): tło `#6d4c41`, biały tekst, wielkie litery, rozmiar 14px.
5. Nagłówki wierszy (`tbody th`): wyrównane do lewej, tło `#efebe9`.
6. Wiersze parzyste w `tbody`: tło `#fafafa`; wiersz pod kursorem: tło `#ffecb3`.
7. Ostatnia kolumna (cena): wyrównana do prawej, pogrubiona.
8. Stopka (`tfoot`): rozmiar czcionki 12px, kolor `#9e9e9e`, tekst wyśrodkowany.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Spraw, by nagłówek tabeli był „przyklejony” przy przewijaniu: ogranicz wysokość bloku z tabelą (`max-height: 200px; overflow-y: auto;`) i nadaj komórkom `thead th` `position: sticky; top: 0;`. Dopisz do tabeli kilka wierszy, żeby to sprawdzić.

## Czy potrafię…?

- [ ] scalić krawędzie komórek tabeli
- [ ] wyrównać zawartość komórki w poziomie i w pionie
- [ ] zrobić wiersze naprzemiennie kolorowane
- [ ] wybrać ostatnią kolumnę tabeli
