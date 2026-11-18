# Lekcja 32. Flexbox, część 2: menu, karty, układ strony

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (6) · <span class="zakres zakres-p">INF.03</span> <span class="zakres zakres-gw">P+</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- sterować rozmiarem elementów elastycznych (`flex-grow`, `flex-shrink`, `flex-basis`),
- zbudować menu z logo po lewej i odnośnikami po prawej,
- ułożyć karty o równej wysokości,
- zbudować układ strony z paneli bez `float`.

## Wprowadzenie

### Właściwości elementów (dzieci)

| Właściwość | Działanie |
|---|---|
| `flex-grow: 1` | element „rośnie”, zajmując wolne miejsce (proporcjonalnie do liczby) |
| `flex-shrink: 0` | element się nie zmniejsza |
| `flex-basis: 200px` | rozmiar wyjściowy elementu |
| `flex: 1` | skrót: `flex-grow: 1; flex-shrink: 1; flex-basis: 0` |
| `flex: 0 0 250px` | stała szerokość 250px |
| `align-self` | wyrównanie jednego elementu na osi poprzecznej |
| `order` | kolejność wyświetlania |

```css
/* panel boczny stały, treść zajmuje resztę */
#strona  { display: flex; }
#boczny  { flex: 0 0 250px; }
#tresc   { flex: 1; }

/* menu: logo po lewej, odnośniki po prawej */
nav      { display: flex; justify-content: space-between; align-items: center; }
```

!!! info "Flexbox na egzaminie"
    Arkusze INF.03 opisują wygląd strony (szerokości, kolory), a nie metodę. Układ paneli możesz wykonać `float` albo flexboxem. Ważne, żeby efekt był zgodny z rysunkiem.

## Zadanie główne (25 min)

Pobierz [sklep.html](../pliki/lekcja-32/sklep.html){ download }. Utwórz `styl.css` i dołącz go. Nie używaj `float`.

1. `* { box-sizing: border-box; }`, `body`: marginesy 0, czcionka `Arial`.
2. **Menu** (`nav`): flexbox, logo `.logo` po lewej, lista odnośników po prawej, wyrównane w pionie do środka. Tło `#212121`, biały tekst, margines wewnętrzny 10px 20px. Lista odnośników: flexbox, bez punktorów, odstęp 20px między odnośnikami.
3. **Układ** (`#strona`): flexbox. Panel `aside`: stała szerokość 220px, tło `#f5f5f5`, margines wewnętrzny 15px. Sekcja `main`: zajmuje całą resztę szerokości, margines wewnętrzny 15px.
4. **Karty** (`.produkty`): flexbox z zawijaniem, odstęp 15px. Każda `.karta`: rozmiar wyjściowy 200px, może rosnąć, obramowanie 1px `#e0e0e0`, zaokrąglenie 8px, margines wewnętrzny 15px.
5. Wnętrze karty: flexbox w kolumnie; przycisk `.kup` zawsze na dole karty, nawet gdy opisy mają różną długość (wskazówka: `margin-top: auto`).
6. Karta `.polecana`: wyświetlana jako pierwsza (`order`), obramowanie 2px `#ff9800`.
7. **Stopka**: flexbox, trzy kolumny o równej szerokości (`flex: 1` dla każdej), tło `#212121`, biały tekst, margines wewnętrzny 20px.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Strona ma tylko jeden ekran treści, a stopka „wisi” w połowie okna. Spraw, by stopka była zawsze na dole okna: `body { display: flex; flex-direction: column; min-height: 100vh; }` i odpowiednia właściwość dla `#strona`. Którą?

## Czy potrafię…?

- [ ] ustawić element o stałej szerokości obok elementu zajmującego resztę miejsca
- [ ] zbudować menu z logo i odnośnikami po przeciwnych stronach
- [ ] ustawić przycisk na dole karty
- [ ] zmienić kolejność wyświetlania elementu bez zmiany HTML
