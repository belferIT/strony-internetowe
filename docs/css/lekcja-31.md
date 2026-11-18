# Lekcja 31. Flexbox, część 1: osie i wyrównanie

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span> <span class="zakres zakres-gw">P+</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- włączyć układ elastyczny (`display: flex`),
- zmienić kierunek osi głównej,
- wyrównać elementy wzdłuż osi głównej i poprzecznej,
- zawijać elementy do nowego wiersza i ustawić odstępy między nimi.

## Wprowadzenie

Flexbox układa **dzieci** kontenera w jednym kierunku: w wierszu lub w kolumnie.

```css
.kontener {
    display: flex;
    flex-direction: row;            /* oś główna: poziomo */
    justify-content: space-between; /* rozkład wzdłuż osi głównej */
    align-items: center;            /* wyrównanie na osi poprzecznej */
    gap: 10px;                      /* odstęp między elementami */
}
```

```text
flex-direction: row
oś główna  ──────────────────────────────►
 ┌─────┐ ┌─────┐ ┌─────┐
 │  1  │ │  2  │ │  3  │      │ oś poprzeczna
 └─────┘ └─────┘ └─────┘      ▼
```

| Właściwość (kontener) | Wartości |
|---|---|
| `flex-direction` | `row`, `row-reverse`, `column`, `column-reverse` |
| `justify-content` | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` |
| `align-items` | `stretch` (domyślnie), `flex-start`, `center`, `flex-end` |
| `flex-wrap` | `nowrap` (domyślnie), `wrap` |
| `gap` | `10px`, `10px 20px` (wiersze, kolumny) |

!!! tip "Wyśrodkowanie w pionie i poziomie"
    Najprostszy sposób na wyśrodkowanie czegokolwiek:
    ```css
    .rodzic { display: flex; justify-content: center; align-items: center; }
    ```

!!! info "Gra na rozgrzewkę"
    [Flexbox Froggy](https://flexboxfroggy.com/#pl) to gra po polsku, w której ustawiasz żaby na liściach właściwościami flexboxa.

## Zadanie główne (25 min)

Pobierz [flex.html](../pliki/lekcja-31/flex.html){ download }. Na stronie jest 6 kontenerów `.box` (A–F), w każdym kilka kwadratów `.el`. Wspólne style są już w pliku. Utwórz `styl.css` i dołącz go. Dla każdego kontenera osiągnij opisany efekt:

1. **A**: elementy obok siebie, wyrównane do prawej.
2. **B**: elementy obok siebie, równe odstępy między nimi, pierwszy przy lewej, ostatni przy prawej krawędzi.
3. **C**: jeden element wyśrodkowany w pionie i poziomie w kontenerze o wysokości 200px.
4. **D**: elementy jeden pod drugim (kolumna), wyśrodkowane w poziomie, odstęp 8px.
5. **E**: 10 elementów; zawijają się do następnego wiersza, odstęp 10px.
6. **F**: elementy w odwrotnej kolejności (od prawej do lewej), wyrównane do dołu kontenera o wysokości 150px.

Po każdym punkcie zmień szerokość okna przeglądarki i sprawdź, jak zachowuje się układ.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Przejdź wszystkie 24 poziomy gry [Flexbox Froggy](https://flexboxfroggy.com/#pl). Zrób zrzut ekranu z ostatniego poziomu.

## Czy potrafię…?

- [ ] włączyć flexbox i zmienić kierunek osi
- [ ] wyjaśnić różnicę między `justify-content` a `align-items`
- [ ] wyśrodkować element w pionie i poziomie
- [ ] sprawić, by elementy zawijały się do nowego wiersza
