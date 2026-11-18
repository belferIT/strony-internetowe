# Lekcja 24. Listy, odnośniki i pseudoklasy

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zmieniać wygląd punktorów list,
- stylować odnośniki w różnych stanach,
- wybierać elementy pseudoklasami `:hover`, `:first-child`, `:nth-child()`,
- zbudować z listy proste menu.

## Wprowadzenie

### Listy

| Właściwość | Przykładowe wartości |
|---|---|
| `list-style-type` | `disc`, `circle`, `square`, `decimal`, `lower-alpha`, `upper-roman`, `none` |
| `list-style-image` | `url("ikona.png")` |
| `list-style-position` | `outside`, `inside` |

### Pseudoklasy odnośników

Zapisuj je w kolejności **L-V-H-A** (*LoVe HAte*):

```css
a:link    { color: #1565c0; }   /* nieodwiedzony */
a:visited { color: #6a1b9a; }   /* odwiedzony */
a:hover   { color: #e65100; }   /* kursor nad odnośnikiem */
a:active  { color: #c62828; }   /* w chwili kliknięcia */
```

`:hover` działa na **każdym** elemencie, nie tylko na odnośnikach.

### Pseudoklasy pozycji

| Pseudoklasa | Wybiera |
|---|---|
| `li:first-child` | pierwszy element |
| `li:last-child` | ostatni element |
| `li:nth-child(3)` | trzeci element |
| `tr:nth-child(odd)` / `even` | nieparzyste / parzyste |
| `li:nth-child(3n)` | co trzeci |

### Menu z listy

```css
nav ul { list-style-type: none; padding: 0; }
nav li { display: inline; }        /* elementy obok siebie */
nav a  { padding: 10px 15px; text-decoration: none; }
```

## Zadanie główne (25 min)

Pobierz [listy.html](../pliki/lekcja-24/listy.html){ download }. Utwórz `styl.css` i dołącz go.

1. **Menu** (`nav`):
    1. tło `#37474f`, usunięte punktory i marginesy listy,
    2. elementy listy obok siebie (`display: inline`),
    3. odnośniki: biały tekst bez podkreślenia, margines wewnętrzny 10px 15px,
    4. po najechaniu kursorem: tło `#ff9800`, kolor tekstu `#37474f`.
2. **Lista zakupów** (`#zakupy`): punktory w kształcie kwadratu, kolor tekstu `#33691e`.
3. **Ranking** (`#ranking`): numeracja rzymska wielkimi literami; pierwszy element pogrubiony z tłem `#ffd54f`, ostatni element kolor `#9e9e9e`.
4. **Zadania** (`#zadania`): bez punktorów; co drugi element (parzyste) z tłem `#f5f5f5`; każdy element zmienia tło na `#e3f2fd` po najechaniu kursorem.
5. **Odnośniki w treści** (`main a`): stany `link`, `visited`, `hover` w kolorach z przykładu we wprowadzeniu, `hover` dodatkowo z podkreśleniem.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Użyj pseudoklasy `:not()`: wszystkie elementy listy `#zadania` poza ostatnim mają dolne obramowanie 1px `#cfd8dc`. Zapisz to jedną regułą.

## Czy potrafię…?

- [ ] zmienić lub usunąć punktory listy
- [ ] zapisać style odnośników w kolejności L-V-H-A
- [ ] wybrać pierwszy, ostatni i co drugi element listy
- [ ] zbudować poziome menu z listy
