# Lekcja 20. Kolory i jednostki

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zapisać kolor jako nazwę, HEX, RGB i HSL,
- ustawić przezroczystość koloru,
- dobrać jednostkę: `px`, `%`, `em`, `rem`, `vw`, `vh`.

## Wprowadzenie

### Zapis kolorów

| Zapis | Przykład (ten sam kolor) | Uwagi |
|---|---|---|
| nazwa | `teal` | ok. 140 nazw angielskich |
| HEX | `#008080` | `#RRGGBB`, każda składowa 00–FF |
| HEX skrócony | `#0F8` = `#00FF88` | gdy cyfry w parach są takie same |
| RGB | `rgb(0, 128, 128)` | składowe 0–255 |
| RGBA | `rgba(0, 128, 128, 0.5)` | ostatnia liczba to krycie: 0 (przezroczysty) – 1 (pełny) |
| HSL | `hsl(180, 100%, 25%)` | odcień 0–360°, nasycenie, jasność |

!!! info "Jak czytać HEX?"
    `#FF0000`: czerwony na maksimum (FF = 255), zielony i niebieski 0, czyli czerwień. `#000000` to czerń, `#FFFFFF` biel, `#808080` szarość. Na egzaminie kolory podawane są najczęściej w zapisie HEX.

### Jednostki

| Jednostka | Względem czego | Przykład użycia |
|---|---|---|
| `px` | piksel ekranu | obramowania, stałe wymiary z polecenia |
| `%` | rozmiar rodzica | szerokość bloków układu: `width: 30%` |
| `em` | rozmiar czcionki **elementu** (lub rodzica dla `font-size`) | odstępy zależne od tekstu |
| `rem` | rozmiar czcionki **elementu `html`** (zwykle 16px) | rozmiary czcionek |
| `vw`, `vh` | 1% szerokości / wysokości okna przeglądarki | baner na całą wysokość ekranu: `height: 100vh` |

!!! warning "Pułapka em"
    `em` się kumuluje: lista w liście z `font-size: 1.2em` ma czcionkę 1,2 × 1,2 = 1,44 razy większą. `rem` nie ma tego problemu.

## Zadanie główne (25 min)

Pobierz [paleta.html](../pliki/lekcja-20/paleta.html){ download }. Utwórz `styl.css` i dołącz go. Każdy blok `.probka` ma wysokość 80px i szerokość 200px (zapisz to jedną regułą).

1. Blok `#k1`: tło `crimson` (nazwa).
2. Blok `#k2`: tło w zapisie HEX: czerwony 0, zielony 150, niebieski 136 (przelicz na system szesnastkowy).
3. Blok `#k3`: tło `rgb(255, 193, 7)`.
4. Blok `#k4`: tło `hsl(210, 80%, 40%)`.
5. Blok `#k5`: tło czarne z kryciem 50% (`rgba`). Zobacz, jak prześwituje tło strony; ustaw dla `body` tło `#ffe0b2`.
6. Nagłówek `h1`: rozmiar `2rem`. Akapit `.duzy`: `1.5rem`. Akapit `.maly`: `0.8rem`.
7. Blok `#pasek`: szerokość `50%`, wysokość 20px, tło `#455a64`. Zmień szerokość okna przeglądarki: co się dzieje z paskiem?
8. Blok `#ekran`: szerokość `50vw`, wysokość 20px, tło `#8d6e63`. Czym różni się od `#pasek`? (Wskazówka: pasek jest w bloku `#kontener` o szerokości 600px.) Odpowiedź zapisz w komentarzu w CSS.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wejdź na [coolors.co](https://coolors.co/generate) i wygeneruj paletę 5 kolorów. Użyj jej dla bloków `#k1`–`#k5`. Sprawdź kontrast czarnego tekstu na każdym kolorze w [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/).

## Czy potrafię…?

- [ ] zamienić kolor RGB na HEX i odwrotnie
- [ ] ustawić półprzezroczysty kolor
- [ ] wyjaśnić różnicę między `em` a `rem`
- [ ] wyjaśnić różnicę między `%` a `vw`
