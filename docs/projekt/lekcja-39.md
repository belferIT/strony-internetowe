# Lekcja 39. Analiza projektu graficznego strony

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (6) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- podzielić projekt graficzny strony na bloki,
- odczytać z projektu wymiary, kolory i kroje pisma,
- przygotować plan struktury HTML przed pisaniem kodu,
- odwzorować projekt w HTML i CSS.

## Wprowadzenie

Grafik dostarcza projekt strony jako obraz (PNG, PDF) albo plik programu graficznego (np. Figma). Zadaniem kodera jest **odwzorowanie** go w HTML i CSS. Zanim napiszesz pierwszą linijkę, przeanalizuj projekt.

### Plan analizy

1. **Bloki**: zaznacz prostokąty: nagłówek, sekcje, karty, stopka. Które leżą obok siebie, a które pod sobą?
2. **Wymiary**: zmierz wysokości pasów i szerokości elementów (w GIMP: narzędzie *Miarka*, ++shift+m++; pozycja kursora na dolnym pasku okna).
3. **Kolory**: odczytaj je pipetą (GIMP: ++o++, a potem kliknij próbkę koloru, by zobaczyć kod HEX).
4. **Typografia**: krój szeryfowy czy bezszeryfowy, rozmiary, grubość.
5. **Odstępy**: marginesy wokół bloków, odstępy między kartami.
6. **Plan HTML**: zapisz drzewo znaczników, zanim zaczniesz pisać kod.

```text
body
├── header      (logo + nav)
├── section#hero (h1, p, a.przycisk)
├── main        (3 × article.karta)
└── footer
```

!!! tip "Wymiary względne"
    Projekt ma stałą szerokość (np. 1200px), a strona musi działać na różnych ekranach. Pasy na całą szerokość zapisuj jako `width: 100%`, a zawartość w kontenerze z `max-width`.

## Zadanie główne (25 min)

Pobierz projekt [projekt-ziarno.png](../pliki/lekcja-39/projekt-ziarno.png){ download } (1200×900 px) i otwórz go w GIMP.

**Część A. Analiza (10 min).** W pliku `lekcja-39/analiza.txt` zapisz:

1. Plan HTML (drzewo znaczników jak w przykładzie powyżej).
2. Wysokość nagłówka, sekcji z hasłem (*hero*) i stopki w pikselach.
3. Szerokość jednej karty i odstęp między kartami.
4. Kody HEX co najmniej 5 kolorów: tło nagłówka, tło *hero*, tło strony, kolor logo, obramowanie kart.
5. Które teksty są pisane krojem szeryfowym, a które bezszeryfowym?

**Część B. Kodowanie (15 min).** Odwzoruj projekt w plikach `index.html` i `styl.css`:

1. Użyj odczytanych kolorów i wymiarów.
2. Kroje: `Georgia, serif` dla nagłówków, `Arial, sans-serif` dla reszty.
3. Okrągłe elementy w kartach zrób blokami z `border-radius: 50%` (to miejsca na ikony).
4. Porównaj swoją stronę z projektem: zrób zrzut ekranu przy szerokości okna 1200px i ułóż oba obrazy obok siebie.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Załóż darmowe konto w [Figma](https://www.figma.com/) i zaprojektuj w niej podstronę **Menu** tej kawiarni w tym samym stylu. W trybie *Dev Mode* Figma pokazuje wymiary i kolory elementów.

## Czy potrafię…?

- [ ] podzielić projekt strony na bloki
- [ ] odczytać kolor pipetą i zapisać go w HEX
- [ ] zmierzyć element w programie graficznym
- [ ] przygotować plan struktury HTML przed kodowaniem
