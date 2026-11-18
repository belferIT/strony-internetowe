# Lekcja 22. Model pudełkowy

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- opisać budowę pudełka: treść, `padding`, `border`, `margin`,
- obliczyć rzeczywistą szerokość elementu,
- ustawić obramowanie, zaokrąglenie narożników i cień,
- wyśrodkować blok na stronie.

## Wprowadzenie

Każdy element na stronie to prostokątne **pudełko**:

```text
+-------------------- margin (margines zewnętrzny) --------------------+
|  +----------------- border (obramowanie) -------------------------+  |
|  |  +-------------- padding (margines wewnętrzny) -------------+  |  |
|  |  |                                                         |  |  |
|  |  |               treść (width × height)                    |  |  |
|  |  |                                                         |  |  |
|  |  +---------------------------------------------------------+  |  |
|  +---------------------------------------------------------------+  |
+---------------------------------------------------------------------+
```

```css
.karta {
    width: 300px;
    padding: 20px;                 /* ze wszystkich stron */
    border: 2px solid #3f51b5;     /* grubość, styl, kolor */
    margin: 10px 20px;             /* góra-dół 10px, lewo-prawo 20px */
}
```

| Zapis skrócony | Znaczenie |
|---|---|
| `margin: 10px;` | wszystkie strony |
| `margin: 10px 20px;` | góra i dół, lewo i prawo |
| `margin: 10px 20px 30px 40px;` | góra, prawo, dół, lewo (zgodnie ze wskazówkami zegara) |
| `margin-top: 10px;` | tylko jedna strona |
| `margin: 0 auto;` | wyśrodkowanie bloku o ustalonej szerokości |

### Ile naprawdę zajmuje element?

Domyślnie (`box-sizing: content-box`) szerokość `width` dotyczy **tylko treści**:

> 300 + 2 × 20 (padding) + 2 × 2 (border) = **344 px**

Po ustawieniu `box-sizing: border-box` szerokość obejmuje też `padding` i `border`: element ma **300 px**, a treść się zmniejsza. Dlatego wiele stron zaczyna się od reguły:

```css
* { box-sizing: border-box; }
```

### Obramowanie, zaokrąglenie, cień

| Właściwość | Przykład |
|---|---|
| `border` | `3px dashed red` (style: `solid`, `dashed`, `dotted`, `double`) |
| `border-bottom` | `1px solid gray` (tylko jedna krawędź) |
| `border-radius` | `10px`, `50%` (koło, gdy element jest kwadratem) |
| `box-shadow` | `0 4px 8px rgba(0,0,0,0.2)` (przesunięcie x, y, rozmycie, kolor) |

## Zadanie główne (25 min)

Pobierz [karty.html](../pliki/lekcja-22/karty.html){ download }. Utwórz `styl.css` i dołącz go.

1. `body`: tło `#eceff1`, marginesy zewnętrzne 0.
2. `#kontener`: szerokość 800px, wyśrodkowany w poziomie, tło białe, margines wewnętrzny 20px.
3. `.karta`: szerokość 300px, margines wewnętrzny 15px, obramowanie 1px ciągłe `#b0bec5`, margines zewnętrzny dolny 20px.
4. `#k1`: zaokrąglenie narożników 10px.
5. `#k2`: tylko lewe obramowanie 6px ciągłe `#ff7043` (pozostałe krawędzie jak w `.karta`).
6. `#k3`: cień `0 4px 10px rgba(0, 0, 0, 0.25)`, bez obramowania.
7. `.awatar`: szerokość i wysokość 80px, tło `#7986cb`, kształt koła.
8. Odczytaj w narzędziach deweloperskich (zakładka **Computed**, schemat pudełka) rzeczywistą szerokość `.karta`. Dodaj `* { box-sizing: border-box; }` na początku pliku. Jak zmieniła się szerokość? Zapisz obie wartości w komentarzu w CSS.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź zjawisko **łączenia marginesów** (*margin collapsing*): ustaw dwóm akapitom jeden pod drugim `margin: 30px`. Jaki jest odstęp między nimi: 30px czy 60px? Sprawdź w narzędziach deweloperskich.

## Czy potrafię…?

- [ ] nazwać cztery warstwy pudełka
- [ ] obliczyć rzeczywistą szerokość elementu
- [ ] wyjaśnić działanie `box-sizing: border-box`
- [ ] wyśrodkować blok w poziomie
