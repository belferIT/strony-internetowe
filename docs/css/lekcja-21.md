# Lekcja 21. Tekst i czcionki

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- ustawić krój, rozmiar, grubość i styl czcionki,
- wyrównać tekst, ustawić wcięcie, interlinię i odstępy między literami,
- dołączyć czcionkę z Google Fonts.

## Wprowadzenie

### Właściwości czcionki (`font-…`)

| Właściwość | Przykładowe wartości |
|---|---|
| `font-family` | `Arial, Helvetica, sans-serif` (lista: jeśli nie ma pierwszej, użyj następnej) |
| `font-size` | `16px`, `1.2rem` |
| `font-weight` | `normal`, `bold`, `300`, `700` |
| `font-style` | `normal`, `italic` |
| `font-variant` | `small-caps` (kapitaliki) |

!!! tip "Rodziny ogólne"
    Listę czcionek zawsze kończ rodziną ogólną: `serif` (szeryfowa), `sans-serif` (bezszeryfowa), `monospace` (o stałej szerokości). Nazwy wieloczłonowe zapisuj w cudzysłowie: `"Times New Roman"`.

### Właściwości tekstu (`text-…` i inne)

| Właściwość | Przykładowe wartości | Działanie |
|---|---|---|
| `text-align` | `left`, `center`, `right`, `justify` | wyrównanie |
| `text-indent` | `30px` | wcięcie pierwszego wiersza |
| `text-decoration` | `none`, `underline`, `line-through` | podkreślenie, przekreślenie |
| `text-transform` | `uppercase`, `lowercase`, `capitalize` | wielkość liter |
| `text-shadow` | `2px 2px 4px gray` | cień tekstu |
| `line-height` | `1.5` | interlinia (wysokość wiersza) |
| `letter-spacing` | `2px` | odstęp między literami |
| `word-spacing` | `5px` | odstęp między wyrazami |

### Czcionka z Google Fonts

1. Wejdź na [fonts.google.com](https://fonts.google.com/), wybierz czcionkę z polskimi znakami (filtr *Language: Polish*).
2. Kliknij *Get font → Get embed code*, skopiuj znaczniki `<link>` do sekcji `head`.
3. W CSS użyj nazwy czcionki: `font-family: "Lato", sans-serif;`

## Zadanie główne (25 min)

Pobierz [artykul.html](../pliki/lekcja-21/artykul.html){ download }. Utwórz `styl.css` i dołącz go. Nie zmieniaj treści HTML (wolno tylko dodać `<link>` w `head`).

1. `body`: czcionka `Georgia, "Times New Roman", serif`, rozmiar 18px, interlinia 1.6, kolor `#212121`.
2. `h1`: czcionka **Montserrat** z Google Fonts (dołącz tylko grubość 700, bo używa jej tylko ten nagłówek), wyśrodkowany, wielkie litery (`text-transform`, bez zmiany treści w HTML), odstęp między literami 3px.
3. `h2`: czcionka bezszeryfowa `Arial`, kursywa, kolor `#5d4037`.
4. Akapity: wyjustowane, wcięcie pierwszego wiersza 40px.
5. `.lead` (pierwszy akapit): rozmiar 22px, kursywa, bez wcięcia (nadpisz regułę z punktu 4).
6. Odnośniki: bez podkreślenia, kolor `#00695c`, pogrubione.
7. `.autor`: wyrównany do prawej, kapitaliki.
8. `.przekreslone`: przekreślenie, kolor `#9e9e9e`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do nagłówka `h1` cień tekstu w dwóch warstwach (wartości oddzielasz przecinkiem), np. jasny i ciemny, tak by uzyskać efekt wypukłości.

## Czy potrafię…?

- [ ] ustawić krój czcionki z listą zapasową
- [ ] dołączyć czcionkę z Google Fonts
- [ ] wyjustować tekst i ustawić wcięcie
- [ ] usunąć podkreślenie z odnośników
