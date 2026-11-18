# Lekcja 33. CSS Grid: siatka strony

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (6) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować siatkę kolumn i wierszy (`display: grid`),
- używać jednostki `fr`,
- rozmieszczać bloki strony za pomocą nazwanych obszarów (`grid-template-areas`).

## Wprowadzenie

Flexbox układa elementy w **jednym** kierunku. Grid układa je w **dwóch** kierunkach naraz: w wierszach i kolumnach.

```css
.galeria {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;      /* 3 równe kolumny */
    gap: 10px;
}
```

| Zapis | Znaczenie |
|---|---|
| `grid-template-columns: 200px 1fr` | kolumna 200px i kolumna na resztę miejsca |
| `grid-template-columns: repeat(4, 1fr)` | 4 równe kolumny |
| `grid-template-columns: repeat(auto-fill, minmax(150px, 1fr))` | tyle kolumn, ile się zmieści, każda min. 150px |
| `grid-column: span 2` | element zajmuje 2 kolumny |
| `fr` | ułamek wolnego miejsca |

### Układ strony z obszarów

```css
body {
    display: grid;
    grid-template-columns: 20% 60% 20%;
    grid-template-rows: 100px 450px auto;
    grid-template-areas:
        "baner  baner  baner"
        "lewy   glowny prawy"
        "stopka stopka stopka";
}
#baner  { grid-area: baner; }
#lewy   { grid-area: lewy; }
#glowny { grid-area: glowny; }
#prawy  { grid-area: prawy; }
#stopka { grid-area: stopka; }
```

Zapis `grid-template-areas` jest jak rysunek układu z arkusza egzaminacyjnego.

!!! info "Gra na rozgrzewkę"
    [Grid Garden](https://cssgridgarden.com/#pl): podlewasz marchewki właściwościami siatki.

## Zadanie główne (25 min)

Skopiuj swoją stronę schroniska z lekcji 29 do folderu `lekcja-33`.

1. Usuń z CSS wszystkie `float`, `clear` i szerokości paneli w procentach.
2. Zbuduj ten sam układ za pomocą `grid-template-areas` (jak we wprowadzeniu). Strona ma wyglądać tak samo jak w lekcji 29.
3. Zmień układ, zmieniając **tylko** właściwości `grid-template-…` (obszary, kolumny i wiersze):
    1. panel prawy pod panelem głównym, panel lewy na całą wysokość obu,
    2. zapisz ten wariant w komentarzu i wróć do układu z punktu 2.
4. Dodaj w panelu głównym galerię 6 obrazów `lapa.png` w siatce `repeat(auto-fill, minmax(100px, 1fr))` z odstępem 8px. Obrazy mają szerokość 100% komórki.
5. Pierwszy obraz galerii zajmuje 2 kolumny i 2 wiersze.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Przejdź 28 poziomów [Grid Garden](https://cssgridgarden.com/#pl). Dowiedz się, czym jest `subgrid`.

## Czy potrafię…?

- [ ] zbudować siatkę 3 równych kolumn
- [ ] wyjaśnić, czym jest jednostka `fr`
- [ ] zbudować układ strony z nazwanych obszarów
- [ ] sprawić, by element zajmował kilka kolumn
