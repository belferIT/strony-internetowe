# Lekcje 61–62. Symulacja egzaminu INF.03: część HTML, CSS i JavaScript

<p class="lekcja-meta">Dział: Podsumowanie · 2 × 45 min · Efekty: INF.03.3 (1), (2), (6), INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Zasady

- Czas: **80 minut** pracy (dwie lekcje bez przerwy lub z przerwą, bez dostępu do pracy w trakcie przerwy). Ostatnie 10 minut: przygotowanie i oddanie pracy.
- Warunki jak na egzaminie: bez internetu (poza walidatorami W3C, jeśli nauczyciel na to pozwoli), bez materiałów i narzędzi AI.
- Prawdziwy egzamin INF.03 (150 minut) zawiera też bazę danych i PHP. Ta symulacja obejmuje tylko część, której uczysz się na tym przedmiocie.
- Folder z pracą: `Nazwisko_Imie` (na egzaminie: numer PESEL lub numer zdającego).

## Materiały

Pobierz i rozpakuj [kajaki.zip](../pliki/lekcja-61/kajaki.zip){ download }: `tresc.txt`, `kajak.jpg`, `logo.png`.

## Zadanie

!!! note "Polecenie"
    Wykonaj stronę internetową wypożyczalni kajaków zgodnie z rysunkiem 1 i opisem. Pliki: `kajaki.html`, `styl.css`, `skrypt.js`, obrazy w tym samym folderze.

```text
Rysunek 1. Układ strony

+------------------------------------------------------------------+
|  #baner                                                          |
+---------------+-----------------------------------+--------------+
|               |                                   |              |
|   #lewy       |            #srodkowy              |   #prawy     |
|               |                                   |              |
+---------------+-----------------------------------+--------------+
|  #stopka                                                         |
+------------------------------------------------------------------+
```

### Cechy strony (HTML)

1. Zastosowany standard HTML5, kodowanie UTF-8, język polski.
2. Tytuł widoczny na karcie przeglądarki: **Kajaki Ina**.
3. Arkusz stylów w pliku `styl.css`, skrypt w pliku `skrypt.js` dołączony na końcu `body`.
4. Podział strony na bloki: `header` (baner), trzy `section` (lewy, środkowy, prawy) i `footer` (stopka), z identyfikatorami jak na rysunku.
5. Treść bloków zgodna z plikiem `tresc.txt`.
6. Panel prawy zawiera formularz (bez znacznika `form`):
    1. etykieta **Rodzaj kajaka** i lista rozwijana `rodzaj` z opcjami **jednoosobowy** (wartość `1`) i **dwuosobowy** (wartość `2`),
    2. etykieta **Liczba kajaków** i pole liczbowe `liczba`,
    3. przyciski radio `wariant`: **1 dzień** (wartość `dzien`, zaznaczony) i **weekend** (wartość `weekend`),
    4. pole wyboru `transport` z etykietą **Transport na start (+20 zł za kajak)**,
    5. przycisk **Oblicz**,
    6. pusty akapit z identyfikatorem `wynik`.

### Styl CSS

1. Cała strona: krój czcionki `Verdana`, marginesy zewnętrzne 0.
2. Baner: kolor tła `#01579B`, kolor czcionki biały, wysokość 120px, wyrównanie tekstu do środka. Logo: wysokość 80px, opływanie do lewej, margines 20px.
3. Panele lewy i prawy: kolor tła `#B3E5FC`, szerokość 25%, wysokość 600px.
4. Panel środkowy: kolor tła `#E1F5FE`, szerokość 50%, wysokość 600px.
5. Panele ułożone obok siebie, z marginesem wewnętrznym 10px (panele nie mogą „spadać” niżej).
6. Stopka: kolor tła `#01579B`, kolor czcionki biały, margines wewnętrzny 10px, wyrównanie tekstu do prawej.
7. Obraz `kajak.jpg`: szerokość 90%, zaokrąglone rogi 10px, cień `0 0 8px gray`.
8. Tabela: szerokość 100%, obramowanie 1px ciągłe `#0277BD`, krawędzie scalone. Komórki nagłówkowe: tło `#0277BD`, kolor czcionki biały.
9. Przycisk: tło `#FF5722`, kolor czcionki biały, bez obramowania, margines wewnętrzny 8px 20px; po najechaniu kursorem tło `#BF360C`.
10. Akapit `wynik`: pogrubiony, rozmiar czcionki 120%.

### Działanie skryptu

Po kliknięciu przycisku **Oblicz**:

1. Pobierana jest liczba kajaków. Jeśli jest mniejsza niż 1, w akapicie `wynik` wypisywany jest tekst **Podaj liczbę kajaków** i obliczenia nie są wykonywane.
2. Cena za kajak: jednoosobowy **60 zł** (1 dzień) lub **100 zł** (weekend); dwuosobowy **90 zł** (1 dzień) lub **150 zł** (weekend).
3. Koszt kajaków: cena × liczba kajaków. Od **5 kajaków** udzielany jest rabat **15%** na kajaki.
4. Jeśli zaznaczony jest transport, doliczane jest **20 zł za każdy kajak** (bez rabatu).
5. W akapicie `wynik` wypisywany jest tekst: **Koszt wypożyczenia: X zł**, gdzie X to wynik z dwoma miejscami po przecinku.

| Rodzaj | Liczba | Wariant | Transport | Wynik |
|---|---|---|---|---|
| jednoosobowy | 1 | 1 dzień | nie | 60.00 zł |
| dwuosobowy | 2 | weekend | tak | 340.00 zł |
| jednoosobowy | 5 | 1 dzień | tak | 355.00 zł |
| dowolny | 0 | – | – | Podaj liczbę kajaków |

## Kryteria oceny (40 pkt)

| Obszar | Kryterium | Punkty |
|---|---|---|
| HTML | struktura dokumentu, tytuł, dołączone CSS i JS | 3 |
| HTML | bloki z identyfikatorami zgodnie z rysunkiem | 3 |
| HTML | treść bloków: logo, listy, odnośnik `tel:`, obraz z `alt`, tabela z `th` | 6 |
| HTML | formularz: lista, pole liczbowe, radio, checkbox, przycisk, akapit wynikowy | 4 |
| CSS | baner, logo, stopka | 4 |
| CSS | panele: kolory, wymiary, ułożenie obok siebie | 5 |
| CSS | obraz, tabela, przycisk z `:hover`, wynik | 5 |
| JS | odczyt danych z formularza | 3 |
| JS | obliczenia: ceny, rabat, transport | 4 |
| JS | walidacja liczby kajaków i format wyniku | 2 |
| Całość | walidacja W3C bez błędów, czytelny kod | 1 |

Na egzaminie zawodowym część praktyczna jest zdana od **75%** punktów. Zapisz swój wynik procentowy.
