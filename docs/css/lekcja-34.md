# Lekcja 34. Strona responsywna: viewport i media queries

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (7) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest strona responsywna,
- dodać znacznik `viewport`,
- zmieniać style zależnie od szerokości ekranu (`@media`),
- testować stronę w trybie urządzeń w przeglądarce.

## Wprowadzenie

**Strona responsywna** dopasowuje układ do szerokości ekranu: na komputerze panele obok siebie, na telefonie jeden pod drugim.

### Krok 1. Znacznik viewport

Bez niego telefon pokazuje stronę jak na monitorze, tylko pomniejszoną:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Krok 2. Elastyczne szerokości

Zamiast `width: 1100px` użyj `max-width: 1100px` albo szerokości w `%`.

### Krok 3. Media queries

```css
/* style domyślne: duży ekran */
#kontener { display: flex; }

/* ekran o szerokości do 768px włącznie */
@media (max-width: 768px) {
    #kontener { flex-direction: column; }
    nav { display: none; }
}
```

| Typowe progi (*breakpoints*) | Urządzenie |
|---|---|
| do 576px | telefon |
| 577–768px | duży telefon, mały tablet |
| 769–1024px | tablet, mały laptop |
| powyżej 1024px | komputer |

!!! tip "Tryb urządzeń"
    W narzędziach deweloperskich naciśnij ++ctrl+shift+m++. U góry wybierzesz model telefonu albo przeciągniesz krawędź, żeby zmienić szerokość. Szerokość w pikselach widać na górnym pasku.

## Zadanie główne (25 min)

Pobierz i rozpakuj [blog.zip](../pliki/lekcja-34/blog.zip){ download }. Strona ma stałą szerokość 1100px. Otwórz ją w trybie urządzeń o szerokości 375px: zobaczysz poziomy pasek przewijania.

1. Dodaj do `index.html` znacznik `viewport`.
2. Popraw `styl.css`, żeby strona nie miała przewijania w poziomie:
    1. `#kontener`: maksymalna szerokość 1100px zamiast stałej,
    2. panele boczne: rozmiar wyjściowy 200px, bez zmniejszania (`flex: 0 0 200px`); `main` zajmuje resztę.
3. Dla ekranów **do 900px**: panel prawy pod treścią na całą szerokość (wskazówka: `flex-wrap: wrap` w kontenerze i `flex-basis: 100%` dla panelu).
4. Dla ekranów **do 600px**:
    1. panele jeden pod drugim (`flex-direction: column`), panel lewy pod treścią (`order`),
    2. nagłówek `header`: logo nad menu (kolumna), wyśrodkowane,
    3. rozmiar `h1`: 24px,
    4. odnośniki menu: odstęp 10px.
5. Sprawdź stronę w trybie urządzeń dla szerokości 375px, 768px i 1280px. Zrób zrzut ekranu każdego widoku.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj na małych ekranach przycisk ☰ (hamburger), który pokazuje i ukrywa menu, **bez JavaScriptu**: użyj ukrytego `input type="checkbox"`, etykiety `label` jako przycisku i selektora `#menu-toggle:checked ~ nav`.

## Czy potrafię…?

- [ ] dodać znacznik viewport i wyjaśnić, do czego służy
- [ ] napisać regułę `@media` dla ekranów do 600px
- [ ] ułożyć panele jeden pod drugim na telefonie
- [ ] przetestować stronę w trybie urządzeń
