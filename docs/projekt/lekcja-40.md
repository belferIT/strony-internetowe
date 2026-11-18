# Lekcja 40. Grafika wektorowa w Inkscape: logo i ikony

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (4) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić różnicę między grafiką rastrową a wektorową,
- narysować logo z prostych kształtów i tekstu w Inkscape,
- łączyć kształty operacjami na ścieżkach,
- wyeksportować grafikę do SVG i PNG.

## Wprowadzenie

| | Grafika rastrowa | Grafika wektorowa |
|---|---|---|
| Budowa | siatka pikseli | kształty opisane matematycznie (punkty, krzywe) |
| Powiększanie | traci jakość (widać piksele) | bez utraty jakości |
| Formaty | JPG, PNG, GIF, WebP | SVG, AI, EPS, PDF |
| Zastosowanie | zdjęcia | logo, ikony, ilustracje, wykresy |
| Programy | GIMP, Photoshop | Inkscape, Illustrator, Figma |

Plik SVG to tekst w formacie XML: możesz go otworzyć w VS Code, a nawet wkleić bezpośrednio do HTML.

### Najważniejsze narzędzia Inkscape

| Narzędzie | Skrót |
|---|---|
| prostokąt | ++r++ |
| elipsa / koło (z ++ctrl++ koło) | ++e++ |
| gwiazda / wielokąt | `*` |
| tekst | ++t++ |
| wypełnienie i kontur | ++ctrl+shift+f++ |
| wyrównaj i rozmieść | ++ctrl+shift+a++ |
| suma kształtów | ++ctrl+plus++ |
| różnica kształtów | ++ctrl+minus++ |
| obiekt na ścieżkę (np. tekst) | ++ctrl+shift+c++ |
| eksport PNG | ++ctrl+shift+e++ |

!!! warning "Tekst w logo"
    Jeśli w SVG zostawisz tekst jako tekst, na komputerze bez tej czcionki logo będzie wyglądało inaczej. Przed eksportem zamień tekst na ścieżki (*Ścieżka → Obiekt w ścieżkę*).

## Zadanie główne (25 min)

Zaprojektuj logo dla kawiarni **Ziarno** z lekcji 39.

1. Utwórz nowy dokument 400×400 px (*Plik → Właściwości dokumentu*).
2. Narysuj symbol z co najmniej trzech kształtów (np. filiżanka: prostokąt z zaokrąglonymi rogami + koło jako ucho + elipsa jako spodek). Połącz je operacją **suma**.
3. Wytnij w kształcie element operacją **różnica** (np. otwór w uchu filiżanki).
4. Dodaj napis **Ziarno**, wyrównaj go do środka symbolu i zamień na ścieżkę.
5. Użyj maksymalnie trzech kolorów z projektu z lekcji 39 (kody HEX wpisz w oknie *Wypełnienie i kontur*).
6. Zapisz pracę jako `logo.svg` (*Zwykły SVG*, nie *Inkscape SVG*).
7. Wyeksportuj dwa pliki PNG: `logo-64.png` (64×64 px) i `logo-512.png` (512×512 px).
8. Wstaw `logo.svg` do swojej strony z lekcji 39 w miejsce znaku ☕ (wysokość 50px). Powiększ stronę do 400% (++ctrl+plus++) i porównaj ostrość logo SVG i PNG.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Otwórz `logo.svg` w VS Code. Usuń zbędne metadane i wklej kod `<svg>…</svg>` bezpośrednio do HTML. Zmień kolor wypełnienia w CSS, np. po najechaniu kursorem na logo (`svg path:hover { fill: … }`).

## Czy potrafię…?

- [ ] wskazać różnice między grafiką rastrową a wektorową
- [ ] połączyć i odjąć kształty w Inkscape
- [ ] zamienić tekst na ścieżkę
- [ ] wyeksportować grafikę do SVG i PNG o zadanym rozmiarze
