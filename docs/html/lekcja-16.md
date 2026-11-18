# Lekcja 16. Sprawdzian praktyczny: HTML

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1), (5) · <span class="zakres zakres-p">INF.03</span></p>

## Zasady

- Czas: **40 minut** na pracę, 5 minut na przygotowanie i oddanie.
- Możesz korzystać z dokumentacji [MDN](https://developer.mozilla.org/pl/) i walidatora W3C. Nie możesz korzystać z narzędzi AI, materiałów z lekcji ani pomocy innych osób.
- Sprawdzian dotyczy **tylko HTML**, bez CSS. Wygląd strony nie jest oceniany.
- Pracę oddajesz jako spakowany folder `Nazwisko_Imie` w miejscu wskazanym przez nauczyciela.

## Materiały

Pobierz i rozpakuj [zoo.zip](../pliki/lekcja-16/zoo.zip){ download }: plik `tresc.txt` i obraz `lis.png`.

## Zadanie

!!! note "Polecenie"
    Utwórz stronę `index.html` mini zoo z treścią z pliku `tresc.txt`. Strona ma strukturę semantyczną HTML5.

### Wymagania

1. Dokument HTML5: kodowanie UTF-8, język polski, tytuł karty **Leśna Polana** (grupa A) lub **Mini ZOO** (grupa B).
2. Struktura: `header` z nagłówkiem i menu w `nav`, `main` z dwoma artykułami `article`, sekcja `section` z formularzem, `footer`.
3. Menu: lista punktowana z czterema odnośnikami z pliku.
4. Obraz `lis.png` w elemencie `figure` z podpisem; tekst alternatywny opisuje, co widać na obrazie; szerokość 300px.
5. Tabela cennika zgodna z rysunkiem 1 (grupa A) lub rysunkiem 2 (grupa B), z tytułem `caption` **Ceny biletów** i komórkami nagłówkowymi w pierwszym wierszu.

```text
Rysunek 1 (grupa A)                         Rysunek 2 (grupa B)

+-----------+------------+--------+         +-----------+------------------------+
| Bilet     | Dzień      | Cena   |         | Bilet     | Cena                   |
+-----------+------------+--------+         +           +-----------+------------+
|           | pon.–pt.   | 15 zł  |         |           | pon.–pt.  | weekend    |
| Normalny  +------------+--------+         +-----------+-----------+------------+
|           | weekend    | 20 zł  |         | Normalny  | 15 zł     | 20 zł      |
+-----------+------------+--------+         +-----------+-----------+------------+
|           | pon.–pt.   | 10 zł  |         | Ulgowy    | 10 zł     | 12 zł      |
| Ulgowy    +------------+--------+         +-----------+-----------+------------+
|           | weekend    | 12 zł  |         | Dzieci do lat 3 wchodzą bezpłatnie |
+-----------+------------+--------+         +------------------------------------+
| Dzieci do lat 3 wchodzą bezpłatnie |
+------------------------------------+
```

6. Formularz wysyłany metodą `post` do pliku `rezerwacja.php`, z polami (każde z etykietą `label`):
    1. nazwa szkoły: tekst, wymagany,
    2. e-mail opiekuna: typ e-mail, wymagany,
    3. data wizyty: typ data,
    4. liczba uczniów: liczba od 5 do 40,
    5. wiek uczniów: trzy przyciski radio (przedszkole, szkoła podstawowa, szkoła średnia),
    6. dodatkowe atrakcje: dwa pola wyboru (karmienie zwierząt, warsztaty przyrodnicze),
    7. uwagi: pole wielowierszowe, 4 wiersze,
    8. przycisk **Zarezerwuj**.
7. Stopka: dane z pliku w elemencie `address`; numer telefonu jest odnośnikiem `tel:`.
8. Kod przechodzi walidację W3C bez błędów, wcięcia są czytelne.

## Kryteria oceny (30 pkt)

| Kryterium | Punkty |
|---|---|
| Struktura dokumentu HTML5 (doctype, lang, charset, title) | 3 |
| Struktura semantyczna (header, nav, main, article, section, footer) | 5 |
| Menu, obraz z `figure`, `figcaption` i poprawnym `alt` | 4 |
| Tabela: `caption`, `th`, poprawne scalenia | 6 |
| Formularz: `action`, `method`, typy pól, etykiety, walidacja (`required`, `min`, `max`) | 8 |
| Stopka: `address`, odnośnik `tel:` | 2 |
| Walidacja W3C bez błędów, czytelny kod | 2 |

Progi ocen ustala nauczyciel zgodnie z WSO.
