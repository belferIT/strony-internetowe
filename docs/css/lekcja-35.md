# Lekcja 35. Mobile first i responsywne obrazy

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (7) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- pisać style w podejściu *mobile first*,
- używać zapytań `min-width`,
- przygotować obraz w kilku rozmiarach i pozwolić przeglądarce wybrać właściwy (`srcset`, `sizes`).

## Wprowadzenie

### Mobile first

Na poprzedniej lekcji style pisaliśmy dla komputera, a potem poprawialiśmy je dla telefonu (`max-width`). W podejściu **mobile first** jest odwrotnie:

1. style domyślne są dla **telefonu** (najprostszy układ: wszystko jedno pod drugim),
2. zapytania `min-width` **dodają** układ dla większych ekranów.

```css
/* telefon: jedna kolumna */
main { display: grid; grid-template-columns: 1fr; gap: 10px; }

/* od 600px: dwie kolumny */
@media (min-width: 600px) {
    main { grid-template-columns: 1fr 1fr; }
}

/* od 1000px: cztery kolumny */
@media (min-width: 1000px) {
    main { grid-template-columns: repeat(4, 1fr); }
}
```

Zaleta: telefon pobiera i przetwarza mniej reguł, a kod jest prostszy.

### Responsywne obrazy

```html
<img src="obrazy/gory-800.jpg"
     srcset="obrazy/gory-400.jpg 400w,
             obrazy/gory-800.jpg 800w,
             obrazy/gory-1600.jpg 1600w"
     sizes="100vw"
     alt="Góry o wschodzie słońca">
```

| Atrybut | Znaczenie |
|---|---|
| `srcset` | lista plików z ich rzeczywistą szerokością (`400w` = 400 pikseli) |
| `sizes` | jaką szerokość obraz zajmie na stronie, np. `100vw` lub `(min-width: 1000px) 50vw, 100vw` |
| `src` | plik zapasowy dla starych przeglądarek |

Przeglądarka sama wybiera najmniejszy plik, który wystarczy. Telefon nie pobiera obrazu 1600px.

```css
img { max-width: 100%; height: auto; }   /* obraz nigdy nie wyjdzie poza rodzica */
```

## Zadanie główne (25 min)

Pobierz i rozpakuj [mobile.zip](../pliki/lekcja-35/mobile.zip){ download }. W folderze `obrazy` jest to samo zdjęcie w trzech szerokościach: 400, 800 i 1600px (szerokość jest napisana na zdjęciu). Utwórz `styl.css`. **Używaj tylko zapytań `min-width`.**

1. Style domyślne (telefon):
    1. `body`: marginesy 0, czcionka `system-ui, sans-serif`,
    2. `header` i `footer`: tło `#33691e`, biały tekst, wyśrodkowany, margines wewnętrzny 10px,
    3. `main`: siatka w jednej kolumnie, odstęp 10px, margines wewnętrzny 10px,
    4. `.kafel`: tło `#f1f8e9`, margines wewnętrzny 15px, zaokrąglenie 8px.
2. Od **600px**: `main` w dwóch kolumnach.
3. Od **1000px**: `main` w czterech kolumnach, maksymalna szerokość 1200px, wyśrodkowany; `h1` rozmiar 40px.
4. W miejscu komentarza w HTML wstaw zdjęcie z `srcset` (trzy pliki) i `sizes="100vw"`. Obraz nie może wychodzić poza ekran.
5. Sprawdź w trybie urządzeń (++ctrl+shift+m++) i w zakładce **Network** (filtr *Img*), który plik pobrała przeglądarka przy szerokości 375px, a który przy 1280px. Przed każdą próbą odśwież stronę z wyczyszczeniem pamięci podręcznej (++ctrl+shift+r++). Zapisz wyniki w komentarzu w CSS.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Użyj znacznika `picture` z elementami `source media="(min-width: 1000px)"`, aby na dużych ekranach wyświetlić inne zdjęcie (np. `jezioro.jpg` z lekcji 7) niż na telefonie. Ta technika to *art direction*.

## Czy potrafię…?

- [ ] wyjaśnić różnicę między podejściem mobile first a desktop first
- [ ] napisać zapytanie `min-width`
- [ ] przygotować obraz z atrybutami `srcset` i `sizes`
- [ ] sprawdzić, który plik obrazu pobrała przeglądarka
