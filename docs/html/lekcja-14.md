# Lekcja 14. Multimedia: dźwięk, wideo i ramki

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (5) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- osadzić na stronie plik dźwiękowy i film,
- sterować odtwarzaniem atrybutami,
- podać kilka formatów pliku jako alternatywę,
- osadzić na stronie mapę i film z innego serwisu (`iframe`).

## Wprowadzenie

```html
<video src="media/film.mp4" width="640" controls poster="media/plakat.jpg">
    Twoja przeglądarka nie obsługuje elementu video.
</video>

<audio controls>
    <source src="media/dzwonek.ogg" type="audio/ogg">
    <source src="media/dzwonek.mp3" type="audio/mpeg">
</audio>
```

| Atrybut | Działanie |
|---|---|
| `controls` | pokazuje przyciski odtwarzacza |
| `autoplay` | odtwarza od razu (przeglądarki pozwalają na to tylko z `muted`) |
| `muted` | wycisza |
| `loop` | odtwarza w pętli |
| `poster` | obraz wyświetlany przed odtworzeniem filmu |
| `preload` | `none`, `metadata`, `auto`: ile pobrać przed kliknięciem |

| Format | Typ MIME | Uwagi |
|---|---|---|
| MP4 (H.264) | `video/mp4` | działa we wszystkich przeglądarkach |
| WebM | `video/webm` | otwarty format, mniejsze pliki |
| MP3 | `audio/mpeg` | działa wszędzie |
| OGG | `audio/ogg` | otwarty format |

Przeglądarka odtworzy pierwszy obsługiwany plik z listy `source`.

### Ramki `iframe`

```html
<iframe src="https://www.openstreetmap.org/export/embed.html?bbox=14.80,53.55,14.86,53.58&layer=mapnik"
        width="600" height="400" title="Mapa Goleniowa"></iframe>
```

Kod do osadzenia mapy lub filmu daje sam serwis: w OpenStreetMap opcja *Udostępnij → HTML*, w YouTube *Udostępnij → Umieść*.

!!! warning "Prawa autorskie"
    Na swojej stronie umieszczaj tylko pliki, do których masz prawa: własne, na wolnej licencji (np. CC0, CC BY) albo osadzone z serwisu, który na to pozwala.

## Zadanie główne (25 min)

Pobierz i rozpakuj [multimedia.zip](../pliki/lekcja-14/multimedia.zip){ download }. W folderze `media` są: `film.mp4` (8 s), `plakat.jpg`, `dzwonek.mp3` i `napisy.vtt`.

Utwórz w folderze `multimedia` stronę `index.html` (tytuł karty: **Multimedia**):

1. Nagłówek 2. stopnia **Film** i film `film.mp4`: szerokość 480px, przyciski odtwarzacza, obraz `plakat.jpg` przed odtworzeniem, bez wstępnego pobierania pliku. Wewnątrz elementu tekst dla starych przeglądarek.
2. Nagłówek 2. stopnia **Animacja w tle** i ten sam film: szerokość 240px, odtwarzany automatycznie, wyciszony, w pętli, **bez** przycisków.
3. Nagłówek 2. stopnia **Dźwięk** i plik `dzwonek.mp3` w elemencie `source` z typem MIME, z przyciskami odtwarzacza.
4. Nagłówek 2. stopnia **Nasza szkoła na mapie** i mapa z [OpenStreetMap](https://www.openstreetmap.org/) pokazująca Twoją szkołę (*Udostępnij → HTML*). Szerokość 600px, wysokość 350px, atrybut `title`.
5. Sprawdź w narzędziach deweloperskich (zakładka **Network**), czy pierwszy film jest pobierany przed kliknięciem *Play*.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do pierwszego filmu napisy z pliku `napisy.vtt`: `<track src="media/napisy.vtt" kind="subtitles" srclang="pl" label="Polski" default>`. Otwórz plik `napisy.vtt` w VS Code i dopisz trzeci napis.

## Czy potrafię…?

- [ ] osadzić film z przyciskami i obrazem startowym
- [ ] sprawić, by film odtwarzał się automatycznie (i wiedzieć, dlaczego musi być wyciszony)
- [ ] podać kilka formatów pliku w elementach `source`
- [ ] osadzić mapę w ramce `iframe`
