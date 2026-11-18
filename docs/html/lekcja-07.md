# Lekcja 7. Obrazy na stronie

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1), (4) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wstawić obraz i opisać go tekstem alternatywnym,
- dobrać format pliku graficznego do zawartości,
- dodać podpis do obrazu,
- zrobić z obrazu odnośnik.

## Wprowadzenie

```html
<img src="obrazy/gory.jpg" alt="Szczyty gór o zachodzie słońca" width="400" height="250">
```

| Atrybut | Znaczenie |
|---|---|
| `src` | ścieżka do pliku (zasady jak w odnośnikach) |
| `alt` | **tekst alternatywny**: czyta go czytnik ekranu, wyświetla się, gdy obraz się nie wczyta. Wymagany! |
| `width`, `height` | wymiary w pikselach (bez jednostki) |
| `title` | dymek po najechaniu myszą |

!!! warning "Proporcje obrazu"
    Jeśli podasz tylko `width`, przeglądarka sama dobierze wysokość z zachowaniem proporcji. Podanie obu wymiarów o złych proporcjach **zniekształci** obraz.

### Formaty plików graficznych

| Format | Rodzaj | Przezroczystość | Animacja | Kiedy używać |
|---|---|---|---|---|
| JPG | rastrowy, kompresja stratna | nie | nie | zdjęcia |
| PNG | rastrowy, bezstratny | tak | nie | grafiki z ostrymi krawędziami, zrzuty ekranu, ikony |
| GIF | rastrowy, maks. 256 kolorów | tak (1 kolor) | tak | proste animacje |
| SVG | wektorowy | tak | tak | logo, ikony, wykresy: skaluje się bez utraty jakości |
| WebP | rastrowy, stratny lub bezstratny | tak | tak | nowoczesny zamiennik JPG i PNG, mniejsze pliki |

### Obraz z podpisem i obraz jako odnośnik

```html
<figure>
    <a href="obrazy/gory.jpg">
        <img src="obrazy/gory.jpg" alt="Szczyty gór o zachodzie słońca" width="300">
    </a>
    <figcaption>Widok z przełęczy (kliknij, aby powiększyć)</figcaption>
</figure>
```

## Zadanie główne (25 min)

Pobierz i rozpakuj [wycieczka.zip](../pliki/lekcja-07/wycieczka.zip){ download }. W folderze `wycieczka/obrazy` są pliki: `gory.jpg`, `jezioro.jpg` (1600×1000 px), `logo.svg`, `ikona-poczta.png`.

![Podgląd pliku gory.jpg](../pliki/lekcja-07/podglad-gory.jpg){ width="300" }

Utwórz w folderze `wycieczka` plik `index.html` (tytuł karty: **Szkolne Wędrówki**):

1. Na początku strony wstaw `logo.svg` o szerokości 200 px z tekstem alternatywnym **Logo Szkolne Wędrówki**.
2. Dodaj nagłówek 1. stopnia **Rajd jesienny 2026** i akapit z krótkim opisem wycieczki (2–3 zdania, wymyśl je).
3. Wstaw dwa zdjęcia, każde w elemencie `figure` z podpisem `figcaption`:
    1. `gory.jpg`, podpis **Dzień 1. Przełęcz**,
    2. `jezioro.jpg`, podpis **Dzień 2. Nocleg nad jeziorem**.
4. Zdjęcia mają mieć szerokość 400 px **z zachowaniem proporcji** (podaj tylko jeden wymiar).
5. Kliknięcie zdjęcia ma otwierać je w pełnym rozmiarze.
6. Każde zdjęcie ma mieć tekst alternatywny opisujący, **co na nim widać**.
7. Na dole strony wstaw `ikona-poczta.png` jako odnośnik `mailto:` do adresu `rajd@example.com`. Tekst alternatywny ma mówić, co się stanie po kliknięciu: **Napisz do organizatorów**.
8. Zmień w kodzie nazwę jednego pliku na nieistniejącą. Co widać na stronie? Przywróć poprawną nazwę.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do obrazów atrybut `loading="lazy"`. Sprawdź w narzędziach deweloperskich (zakładka **Network**), kiedy przeglądarka pobiera zdjęcia, jeśli strona jest długa, a zdjęcia są na dole. Do czego to się przydaje?

## Czy potrafię…?

- [ ] wstawić obraz z poprawnym tekstem alternatywnym
- [ ] dobrać format pliku do zdjęcia, logo i animacji
- [ ] przeskalować obraz bez zniekształcenia
- [ ] dodać podpis i zrobić z obrazu odnośnik
