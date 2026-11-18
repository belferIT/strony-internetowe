# Lekcja 38. Sprawdzian praktyczny: HTML i CSS

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (1), (2), (6) · <span class="zakres zakres-p">INF.03</span></p>

## Zasady

- Czas: **40 minut** na pracę, 5 minut na przygotowanie i oddanie.
- Możesz korzystać z dokumentacji [MDN](https://developer.mozilla.org/pl/) i walidatorów W3C. Nie możesz korzystać z narzędzi AI, materiałów z lekcji ani pomocy innych osób.
- Zadanie jest zbudowane jak część praktyczna egzaminu INF.03.
- Pracę oddajesz jako spakowany folder `Nazwisko_Imie` (pliki `index.html`, `styl.css`, `kino.png`) w miejscu wskazanym przez nauczyciela.

## Materiały

Pobierz i rozpakuj [kino.zip](../pliki/lekcja-38/kino.zip){ download }: plik `tresc.txt` z treścią strony i obraz `kino.png`.

## Zadanie

!!! note "Polecenie"
    Utwórz stronę internetową kina zgodnie z rysunkiem 1 oraz z opisem. Pliki zapisz w folderze `Nazwisko_Imie`.

```text
Rysunek 1. Układ strony

+--------------------------------------------------------------+
|                          #baner                              |
+--------------------------------------------------------------+
|                          #menu                               |
+--------------------+-----------------------------------------+
|                    |                                         |
|      #lewy         |               #prawy                    |
|                    |                                         |
+--------------------+-----------------------------------------+
|                          #stopka                             |
+--------------------------------------------------------------+
```

### Cechy strony (HTML)

1. Dokument HTML5: kodowanie UTF-8, język polski, tytuł karty **Kino Klaps**.
2. Arkusz stylów w pliku `styl.css`, dołączony do strony.
3. Bloki: `header` (`id="baner"`), `nav` (`id="menu"`), dwie sekcje `section` (`id="lewy"`, `id="prawy"`), `footer` (`id="stopka"`).
4. Treść bloków zgodna z plikiem `tresc.txt`.
5. Tabela repertuaru: komórki pierwszego wiersza są komórkami nagłówkowymi. Komórki z tytułem **Wielka podróż** są scalone w jedną (dwa wiersze). Tak samo komórki z numerem sali **1** oraz komórki z numerem sali **2**.

### Styl CSS

Wartości dla grupy A i grupy B podaje tabela poniżej. Swoją grupę poda nauczyciel.

| Element | Grupa A | Grupa B |
|---|---|---|
| kolor 1 (baner, stopka) | `#263238` | `#4A148C` |
| kolor 2 (menu, nagłówek tabeli) | `#FFC107` | `#00BFA5` |
| kolor 3 (panel lewy) | `#ECEFF1` | `#F3E5F5` |
| czcionka strony | `Verdana` | `Tahoma` |

1. Cała strona: czcionka z tabeli, marginesy zewnętrzne 0.
2. Baner: tło kolor 1, czcionka biała, tekst wyśrodkowany, odstęp wewnętrzny 20px.
3. Menu: tło kolor 2, odstęp wewnętrzny 10px. Odnośniki ułożone **obok siebie** i wyśrodkowane, odstęp między nimi 30px, bez punktorów. Odnośniki: kolor czarny, pogrubione, bez podkreślenia; po najechaniu kursorem podkreślone.
4. Panel lewy: tło kolor 3, szerokość 30%, wysokość 400px, tekst wyśrodkowany.
5. Panel prawy: tło białe, szerokość 70%, wysokość 400px.
6. Oba panele: obok siebie, odstęp wewnętrzny 15px. Panele nie mogą spadać niżej.
7. Obraz: szerokość 70%, zaokrąglone narożniki 15px.
8. Tabela: szerokość 100%, krawędzie scalone, wszystkie komórki z obramowaniem 1px ciągłym w kolorze 1, odstęp wewnętrzny 8px.
9. Komórki nagłówkowe tabeli: tło kolor 2.
10. Wiersz tabeli pod kursorem: tło kolor 3.
11. Stopka: tło kolor 1, czcionka biała, wyrównanie do prawej, odstęp wewnętrzny 10px.

## Kryteria oceny (30 pkt)

| Kryterium | Punkty |
|---|---|
| Poprawna struktura HTML5 (doctype, lang, charset, title, link) | 3 |
| Bloki z identyfikatorami zgodnie z rysunkiem | 3 |
| Treść bloków zgodna z plikiem (menu jako lista odnośników, obraz z alt, lista cen) | 4 |
| Tabela: nagłówek, poprawne scalenia `rowspan` | 4 |
| Styl banera, menu i stopki (pkt 1–3, 11) | 5 |
| Układ paneli: szerokości, wysokości, obok siebie (pkt 4–6) | 5 |
| Styl obrazu i tabeli (pkt 7–10) | 4 |
| Kod przechodzi walidację HTML i CSS bez błędów, czytelne wcięcia | 2 |

Progi ocen ustala nauczyciel zgodnie z WSO.
