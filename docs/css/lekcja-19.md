# Lekcja 19. Kaskadowość, dziedziczenie i specyficzność

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- przewidzieć, która reguła zadziała, gdy kilka reguł dotyczy tego samego elementu,
- obliczyć specyficzność selektora,
- wyjaśnić, które właściwości są dziedziczone.

## Wprowadzenie

### Kaskada: kto wygrywa?

Gdy kilka reguł ustawia tę samą właściwość tego samego elementu, przeglądarka sprawdza po kolei:

1. **`!important`**: deklaracja z tym dopiskiem wygrywa (używaj wyjątkowo).
2. **Specyficzność**: wygrywa bardziej szczegółowy selektor.
3. **Kolejność**: przy równej specyficzności wygrywa reguła zapisana **później**.

### Specyficzność

Liczymy trzy liczby (a, b, c):

| Składnik selektora | Dodaje |
|---|---|
| styl liniowy `style="…"` | wygrywa z każdym selektorem |
| identyfikator `#id` | a + 1 |
| klasa `.klasa`, pseudoklasa `:hover`, atrybut `[type]` | b + 1 |
| znacznik `p`, pseudoelement `::before` | c + 1 |

| Selektor | Specyficzność |
|---|---|
| `p` | (0, 0, 1) |
| `.tekst` | (0, 1, 0) |
| `p.tekst` | (0, 1, 1) |
| `#opis p` | (1, 0, 1) |
| `nav ul li a` | (0, 0, 4) |

Porównujesz od lewej: (1, 0, 0) wygrywa z (0, 9, 9).

### Dziedziczenie

Niektóre właściwości elementy **dziedziczą** od rodzica, np. `color`, `font-family`, `font-size`, `line-height`, `text-align`. Dlatego czcionkę ustawia się raz, dla `body`.

Inne nie są dziedziczone, np. `margin`, `padding`, `border`, `background`, `width`.

!!! tip "Narzędzia deweloperskie"
    W panelu **Styles** (++f12++) reguły, które przegrały, są **przekreślone**. Zakładka **Computed** pokazuje ostateczną wartość właściwości.

## Zadanie główne (25 min)

Pobierz [kaskada.html](../pliki/lekcja-19/kaskada.html){ download } (style są w sekcji `head`). Odpowiedzi zapisz w pliku `lekcja-19/odpowiedzi.txt`.

1. **Bez otwierania pliku w przeglądarce** przewidź kolor tekstu każdego z sześciu akapitów (A–F). Zapisz przewidywania.
2. Oblicz specyficzność wszystkich selektorów z sekcji `style`. Zapisz je w postaci (a, b, c).
3. Otwórz stronę w przeglądarce i porównaj z przewidywaniami. Dla każdej pomyłki wyjaśnij jednym zdaniem, co zdecydowało.
4. W narzędziach deweloperskich sprawdź akapit F: która reguła jest przekreślona?
5. Dopisz na końcu sekcji `style` **jedną** regułę, która zmieni kolor akapitu C na `orange` bez użycia `!important` i bez zmiany HTML.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź, jak działają wartości `inherit`, `initial` i `unset`. Na przykładzie odnośnika pokaż, jak sprawić, by dziedziczył kolor tekstu od rodzica (`color: inherit`).

## Czy potrafię…?

- [ ] wymienić kolejność rozstrzygania konfliktów w kaskadzie
- [ ] obliczyć specyficzność selektora
- [ ] podać dwie właściwości dziedziczone i dwie niedziedziczone
- [ ] znaleźć przegraną regułę w narzędziach deweloperskich
