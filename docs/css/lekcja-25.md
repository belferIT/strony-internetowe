# Lekcja 25. Pseudoelementy i selektory atrybutów

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- dodawać treść ozdobną pseudoelementami `::before` i `::after`,
- stylować pierwszą literę i pierwszy wiersz tekstu,
- wybierać elementy według atrybutów i ich wartości.

## Wprowadzenie

### Pseudoelementy

Pseudoelement to „wirtualna” część elementu, której nie ma w HTML.

| Pseudoelement | Działanie |
|---|---|
| `::first-letter` | pierwsza litera (inicjał) |
| `::first-line` | pierwszy wiersz tekstu |
| `::before` | treść dodana **przed** zawartością elementu |
| `::after` | treść dodana **po** zawartości elementu |
| `::selection` | tekst zaznaczony myszą |
| `::placeholder` | podpowiedź w polu formularza |

```css
.uwaga::before {
    content: "⚠ ";          /* bez content pseudoelement się nie pojawi */
    color: #e65100;
}
p::first-letter {
    font-size: 3em;
    float: left;
}
```

!!! info "Pseudoklasa czy pseudoelement?"
    Pseudoklasa (jeden dwukropek `:hover`) wybiera element w określonym **stanie**. Pseudoelement (dwa dwukropki `::before`) wybiera **część** elementu.

### Selektory atrybutów

| Selektor | Wybiera elementy… |
|---|---|
| `[title]` | z atrybutem `title` |
| `[type="email"]` | z atrybutem o dokładnie tej wartości |
| `[href^="https"]` | z wartością **zaczynającą się** od `https` |
| `[href$=".pdf"]` | z wartością **kończącą się** na `.pdf` |
| `[class*="btn"]` | z wartością **zawierającą** `btn` |

## Zadanie główne (25 min)

Pobierz [atrybuty.html](../pliki/lekcja-25/atrybuty.html){ download }. Utwórz `styl.css` i dołącz go. **Nie zmieniaj HTML.**

1. Pierwsza litera akapitu `.wstep`: rozmiar 3em, kolor `#c62828`, opływana tekstem (`float: left`), margines prawy 8px.
2. Pierwszy wiersz akapitu `.wstep`: kapitaliki.
3. Przed każdym akapitem z klasą `uwaga` dodaj znak `⚠` i spację; całe akapity mają tło `#fff3e0`.
4. Za każdym odnośnikiem do pliku PDF (`href` kończy się na `.pdf`) dodaj tekst ` (PDF)` w kolorze `#757575`.
5. Odnośniki zewnętrzne (zaczynające się od `https`) mają kolor `#2e7d32`; po nich dodaj znak `↗`.
6. Pola formularza `input[type="email"]` mają obramowanie 2px ciągłe `#1976d2`, a `input[type="password"]` obramowanie 2px ciągłe `#d32f2f`.
7. Elementy z atrybutem `title` mają podkreślenie kropkowane (`text-decoration: underline dotted`) i kursor `help`.
8. Zaznaczony myszą tekst ma tło `#ffeb3b` i kolor czarny.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Za pomocą `::before` i liczników CSS (`counter-reset`, `counter-increment`, `content: counter(...)`) ponumeruj wszystkie nagłówki `h2` na stronie w formacie `Rozdział 1. `.

## Czy potrafię…?

- [ ] dodać treść pseudoelementem `::before` lub `::after`
- [ ] ostylować pierwszą literę akapitu
- [ ] wybrać pole formularza według typu
- [ ] wybrać odnośniki do plików PDF
