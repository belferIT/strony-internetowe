# Lekcja 23. Tła, gradienty i obrazy w tle

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- ustawić kolor i obraz tła,
- sterować powtarzaniem, położeniem i rozmiarem obrazu tła,
- tworzyć gradienty liniowe i radialne.

## Wprowadzenie

| Właściwość | Przykładowe wartości | Działanie |
|---|---|---|
| `background-color` | `#fafafa` | kolor tła |
| `background-image` | `url("obrazy/gory.jpg")` | obraz tła (ścieżka **względem pliku CSS**) |
| `background-repeat` | `repeat`, `no-repeat`, `repeat-x`, `repeat-y` | powtarzanie obrazu |
| `background-position` | `center`, `top right`, `50% 20%` | położenie obrazu |
| `background-size` | `cover`, `contain`, `100px 50px` | rozmiar obrazu |
| `background-attachment` | `scroll`, `fixed` | czy tło przewija się ze stroną |

| `background-size` | Działanie |
|---|---|
| `cover` | obraz pokrywa cały element, może zostać przycięty |
| `contain` | cały obraz jest widoczny, mogą zostać puste pola |

### Gradienty

```css
background-image: linear-gradient(to right, #ff9800, #e91e63);
background-image: linear-gradient(45deg, #2196f3 0%, #00bcd4 50%, #4caf50 100%);
background-image: radial-gradient(circle, #ffffff, #90caf9);
```

### Obraz z przyciemnieniem

Gradient i obraz można łączyć: pierwsza warstwa leży na wierzchu.

```css
background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url("obrazy/gory.jpg");
```

!!! warning "Ścieżka w pliku CSS"
    Jeśli plik CSS leży w folderze `css/`, a obrazy w `obrazy/`, ścieżka w CSS to `url("../obrazy/gory.jpg")`.

## Zadanie główne (25 min)

Pobierz i rozpakuj [tla.zip](../pliki/lekcja-23/tla.zip){ download }. Utwórz `styl.css` w folderze `tla` i dołącz go do `index.html`.

1. `body`: obraz tła `obrazy/kropki.png` powtarzany w obu kierunkach, marginesy 0, czcionka `Arial`.
2. `#baner`:
    1. wysokość 300px, tekst wyśrodkowany, kolor tekstu biały,
    2. obraz tła `gory.jpg` bez powtarzania, wyśrodkowany, pokrywający cały blok (`cover`),
    3. na obrazie półprzezroczyste przyciemnienie `rgba(0, 0, 0, 0.4)`,
    4. margines wewnętrzny górny 80px (żeby tekst był bliżej środka).
3. `#o-nas`: tło białe, margines wewnętrzny 20px, szerokość 70%, wyśrodkowany.
4. `#zapisy`: gradient liniowy od lewej do prawej od `#fff176` do `#ffb74d`, margines wewnętrzny 20px, szerokość 70%, wyśrodkowany.
5. `#stopka`: gradient radialny od `#546e7a` (środek) do `#263238`, kolor tekstu biały, tekst wyśrodkowany, margines wewnętrzny 10px.
6. Zmień w `#baner` wartość `cover` na `contain`, a potem na `100% 100%`. Zapisz w komentarzu, czym się różnią. Przywróć `cover`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj banerowi `background-attachment: fixed` i wydłuż stronę kilkoma akapitami. Uzyskasz efekt *parallax*, czyli tło stojące w miejscu przy przewijaniu. Sprawdź, jak to wygląda na telefonie (tryb urządzenia w narzędziach deweloperskich, ++ctrl+shift+m++).

## Czy potrafię…?

- [ ] wstawić obraz tła bez powtarzania i wyśrodkować go
- [ ] wyjaśnić różnicę między `cover` a `contain`
- [ ] utworzyć gradient liniowy i radialny
- [ ] poprawnie zapisać ścieżkę do obrazu w pliku CSS
