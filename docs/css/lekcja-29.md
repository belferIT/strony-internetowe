# Lekcja 29. Układ strony z bloków. Zadanie w stylu egzaminu

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (6) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować typowy układ strony z egzaminu INF.03: baner, panele obok siebie, stopka,
- ustawić bloki obok siebie za pomocą `float` i szerokości w procentach,
- odwzorować wygląd strony na podstawie opisu stylów.

## Wprowadzenie

Na egzaminie INF.03 strona prawie zawsze ma układ z bloków o podanych wymiarach i kolorach. Bloki obok siebie najprościej ustawić tak:

```css
#lewy, #glowny, #prawy {
    float: left;
    height: 500px;
}
#lewy   { width: 20%; }
#glowny { width: 60%; }
#prawy  { width: 20%; }
#stopka { clear: both; }
```

!!! warning "Suma szerokości"
    Szerokości bloków obok siebie muszą sumować się do 100%. Jeśli dodasz `padding` lub `border`, blok się poszerzy i ostatni panel „spadnie” niżej. Rozwiązanie: `box-sizing: border-box` albo odjęcie marginesów od szerokości.

!!! tip "Jak pracować na egzaminie"
    1. Najpierw cała struktura HTML z identyfikatorami bloków i treścią.
    2. Potem CSS w kolejności z polecenia: jedna linijka polecenia to jedna lub dwie deklaracje.
    3. Na koniec walidacja i porównanie z rysunkiem.

## Zadanie główne (25 min)

Pobierz i rozpakuj [schronisko.zip](../pliki/lekcja-29/schronisko.zip){ download }: plik `tresc.txt` z treścią strony i obraz `lapa.png`.

!!! note "Polecenie (styl arkusza INF.03)"
    Utwórz stronę `index.html` i arkusz stylów `styl.css` zgodnie z rysunkiem i opisem.

```text
Rysunek 1. Układ strony

+--------------------------------------------------------------+
|                          #baner                              |
+-------------+------------------------------+-----------------+
|             |                              |                 |
|   #lewy     |          #glowny             |    #prawy       |
|             |                              |                 |
+-------------+------------------------------+-----------------+
|                          #stopka                             |
+--------------------------------------------------------------+
```

**Cechy strony (HTML):**

1. Kodowanie UTF-8, język polski, tytuł karty: **Schronisko Łapka**.
2. Arkusz stylów w zewnętrznym pliku `styl.css`.
3. Bloki: `header` z identyfikatorem `baner`, trzy `section` z identyfikatorami `lewy`, `glowny`, `prawy`, `footer` z identyfikatorem `stopka`.
4. Baner: nagłówek 1. stopnia z treścią z pliku.
5. Panel lewy: lista punktowana z czterema odnośnikami z pliku.
6. Panel główny: dwa nagłówki 2. stopnia, akapit i tabela z godzinami otwarcia (bez wiersza nagłówka).
7. Panel prawy: obraz `lapa.png` z tekstem alternatywnym z pliku i akapit.
8. Stopka: akapit z Twoim imieniem i nazwiskiem.

**Styl CSS:**

1. Cała strona: czcionka `Tahoma`, marginesy zewnętrzne 0.
2. Baner: tło `#5D4037`, kolor czcionki `#FFFFFF`, wysokość 100px, tekst wyśrodkowany, odstęp wewnętrzny górny 10px.
3. Panele lewy i prawy: tło `#D7CCC8`, szerokość 20%, wysokość 450px.
4. Panel główny: tło `#EFEBE9`, szerokość 60%, wysokość 450px.
5. Wszystkie trzy panele: opływanie do lewej, odstęp wewnętrzny 10px. Panele mają nie spadać niżej (pamiętaj o `box-sizing`).
6. Stopka: tło `#5D4037`, kolor czcionki `#FFFFFF`, odstęp wewnętrzny 10px, wyrównanie do prawej, poniżej paneli.
7. Obraz: szerokość 80%, wyśrodkowany w panelu (wskazówka: `display: block; margin: auto;`).
8. Tabela: szerokość 100%, krawędzie scalone, komórki z dolnym obramowaniem 1px ciągłym `#8D6E63`.
9. Odnośniki w panelu lewym: kolor `#3E2723`, bez podkreślenia; po najechaniu podkreślone.

Masz **25 minut**. Na koniec sprawdź HTML i CSS w walidatorach W3C.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wykonaj te same panele bez `float`, za pomocą `display: inline-block`. Pojawi się mała szczelina między blokami i ostatni panel spadnie. Dowiedz się, skąd się bierze (odstępy w kodzie HTML) i jak ją usunąć.

## Czy potrafię…?

- [ ] zbudować układ: baner, trzy panele obok siebie, stopka
- [ ] dobrać szerokości bloków, żeby sumowały się do 100%
- [ ] umieścić stopkę pod blokami opływanymi
- [ ] wyśrodkować obraz w bloku
