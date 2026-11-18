# Lekcja 28. Wyświetlanie elementów i opływanie

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- odróżnić elementy blokowe i liniowe,
- zmienić sposób wyświetlania elementu właściwością `display`,
- opływać obraz tekstem (`float`) i zatrzymać opływanie (`clear`),
- ukryć element na dwa sposoby.

## Wprowadzenie

### Elementy blokowe i liniowe

| | Blokowe (`block`) | Liniowe (`inline`) | `inline-block` |
|---|---|---|---|
| Przykłady | `div`, `p`, `h1`, `ul`, `section` | `span`, `a`, `strong`, `img` | (ustawiane w CSS) |
| Nowy wiersz | tak, zajmuje całą szerokość | nie, układa się w wierszu tekstu | nie |
| `width`, `height` | działają | **nie działają** | działają |

```css
nav a { display: inline-block; width: 120px; }   /* obok siebie, ale z wymiarami */
.ukryty { display: none; }                       /* znika, nie zajmuje miejsca */
.niewidoczny { visibility: hidden; }             /* niewidoczny, ale zajmuje miejsce */
```

### Opływanie: `float`

```css
img.lewy {
    float: left;          /* obraz do lewej, tekst opływa go z prawej */
    margin: 0 15px 10px 0;
}
.stopka { clear: both; }  /* ten element zaczyna się pod elementami opływanymi */
```

!!! warning "Rodzic „nie widzi” elementów opływanych"
    Gdy wszystkie dzieci bloku mają `float`, blok rodzica ma wysokość 0 (np. znika jego tło). Rozwiązanie: rodzicowi nadaj `overflow: auto;` albo `display: flow-root;`.

## Zadanie główne (25 min)

Pobierz i rozpakuj [float.zip](../pliki/lekcja-28/float.zip){ download }. Utwórz `styl.css` w folderze `float` i dołącz go.

1. `#menu a`: wyświetlane jako `inline-block`, szerokość 120px, tekst wyśrodkowany, tło `#00796b`, biały tekst bez podkreślenia, margines wewnętrzny 8px 0.
2. Obraz `.lewy`: opływany z lewej, szerokość 250px, margines prawy i dolny 15px.
3. Obraz `.prawy`: opływany z prawej, szerokość 200px, margines lewy i dolny 15px, obramowanie 4px białe z cieniem `0 2px 6px gray`.
4. Nagłówek `h2.nowa-sekcja` (**Trasa nad jeziorem**) musi zaczynać się **pod** pierwszym obrazem, a nie obok niego.
5. `#galeria`: tło `#e0f2f1`, margines wewnętrzny 10px. Trzy miniatury w środku są opływane z lewej, szerokość 30%, margines prawy 3%. Tło galerii zniknie: napraw to.
6. Element `.reklama`: ukryj tak, aby nie zajmował miejsca.
7. Element `.spoiler`: niewidoczny, ale zajmujący miejsce. Po najechaniu na `#zagadka` spoiler ma się pojawić (`#zagadka:hover .spoiler`).

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj obrazowi `.lewy` zaokrąglenie 50% i właściwość `shape-outside: circle();`. Jak teraz tekst opływa obraz?

## Czy potrafię…?

- [ ] podać po trzy elementy blokowe i liniowe
- [ ] wyjaśnić działanie `inline-block`
- [ ] opłynąć obraz tekstem i zatrzymać opływanie
- [ ] wyjaśnić różnicę między `display: none` a `visibility: hidden`
