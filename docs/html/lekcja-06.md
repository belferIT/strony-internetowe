# Lekcja 6. Odnośniki i struktura folderów

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wstawiać odnośniki do innych stron i podstron,
- stosować ścieżki względne i bezwzględne,
- tworzyć odnośniki do miejsca na stronie (kotwice), do poczty e-mail i telefonu.

## Wprowadzenie

```html
<a href="adres">tekst odnośnika</a>
```

### Rodzaje adresów w `href`

| Rodzaj | Przykład | Kiedy |
|---|---|---|
| bezwzględny | `https://www.w3.org/` | strona w innym serwisie |
| względny, ten sam folder | `kontakt.html` | podstrona obok |
| względny, podfolder | `podstrony/galeria.html` | plik w folderze niżej |
| względny, folder wyżej | `../index.html` | powrót do folderu nadrzędnego |
| kotwica | `#regulamin` | miejsce na tej samej stronie, element z `id="regulamin"` |
| e-mail | `mailto:sekretariat@szkola.pl` | otwiera program pocztowy |
| telefon | `tel:+48911234567` | dzwoni na telefonie |

```text
serwis/
├── index.html
└── podstrony/
    ├── galeria.html
    └── kontakt.html
```

Z `index.html` do galerii: `podstrony/galeria.html`.
Z `galeria.html` do kontaktu: `kontakt.html`.
Z `kontakt.html` na stronę główną: `../index.html`.

### Otwieranie w nowej karcie

```html
<a href="https://www.w3.org/" target="_blank" rel="noopener">W3C</a>
```

!!! tip "Dobra praktyka"
    W nowej karcie otwieraj tylko odnośniki do **innych serwisów**. Podstrony własnej strony otwieraj w tej samej karcie.

## Zadanie główne (25 min)

Pobierz i rozpakuj [serwis.zip](../pliki/lekcja-06/serwis.zip){ download }. Otwórz folder `serwis` w VS Code. Wszystkie odnośniki zapisuj **ścieżkami względnymi**.

1. W `index.html` w sekcji z menu (komentarz `<!-- MENU -->`) utwórz trzy odnośniki: **Strona główna**, **Galeria**, **Kontakt**. Skopiuj to samo menu do dwóch podstron i popraw ścieżki tak, by działały z folderu `podstrony`.
2. W `index.html` utwórz odnośnik **Przejdź do regulaminu**, który przeniesie do nagłówka *Regulamin* na dole strony. Nagłówkowi nadaj `id="regulamin"`.
3. Pod regulaminem dodaj odnośnik **Do góry**, przenoszący na początek strony.
4. W `kontakt.html`:
    1. adres e-mail ma otwierać program pocztowy,
    2. numer telefonu ma uruchamiać połączenie,
    3. tekst **Strona W3C** ma być odnośnikiem do `https://www.w3.org/`, otwieranym w nowej karcie.
5. Sprawdź każdy odnośnik, klikając go w przeglądarce.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź, co robi atrybut `download` w odnośniku do pliku tekstowego. Dodaj do `index.html` odnośnik **Pobierz regulamin**, który pobierze plik `regulamin.txt` (utwórz go) zamiast go otworzyć.

## Czy potrafię…?

- [ ] napisać ścieżkę do pliku w podfolderze i w folderze nadrzędnym
- [ ] utworzyć kotwicę i odnośnik do niej
- [ ] utworzyć odnośnik do e-maila i telefonu
- [ ] otworzyć odnośnik w nowej karcie
