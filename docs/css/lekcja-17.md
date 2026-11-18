# Lekcja 17. Wprowadzenie do CSS

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zapisać regułę CSS (selektor, właściwość, wartość),
- dołączyć style na trzy sposoby: liniowo, wewnętrznie i zewnętrznie,
- wyjaśnić, dlaczego najlepszy jest zewnętrzny arkusz stylów.

## Wprowadzenie

HTML opisuje, **co** jest na stronie. CSS (*Cascading Style Sheets*) opisuje, **jak** to wygląda.

```css
h1 {
    color: darkblue;
    font-size: 32px;
}
```

| Część | W przykładzie |
|---|---|
| selektor (do czego stosujemy styl) | `h1` |
| deklaracja | `color: darkblue;` |
| właściwość | `color` |
| wartość | `darkblue` |

### Trzy sposoby dołączania stylów

=== "Zewnętrzny (najlepszy)"

    Plik `styl.css`:
    ```css
    p { color: gray; }
    ```
    W `head` dokumentu HTML:
    ```html
    <link rel="stylesheet" href="styl.css">
    ```

=== "Wewnętrzny"

    ```html
    <head>
        <style>
            p { color: gray; }
        </style>
    </head>
    ```

=== "Liniowy (inline)"

    ```html
    <p style="color: gray;">Tekst</p>
    ```

!!! tip "Dlaczego zewnętrzny?"
    Jeden plik CSS może obsłużyć wszystkie podstrony serwisu. Zmieniasz kolor w jednym miejscu, a zmienia się na każdej stronie. Na egzaminie INF.03 style prawie zawsze zapisuje się w **zewnętrznym pliku** o nazwie podanej w poleceniu.

!!! warning "Częste błędy"
    - brak średnika `;` po deklaracji,
    - brak nawiasu klamrowego `}`,
    - spacja między liczbą a jednostką: `20 px` jest **błędne**, poprawnie `20px`.

## Zadanie główne (25 min)

Pobierz [strona.html](../pliki/lekcja-17/strona.html){ download } i zapisz w folderze `lekcja-17`.

1. W pierwszym akapicie (`id="p1"`) ustaw stylem liniowym kolor tekstu `red`.
2. W sekcji `head` dodaj style wewnętrzne: nagłówek `h2` ma kolor `green`.
3. Utwórz plik `styl.css` i dołącz go do strony. Zapisz w nim:
    1. dla `body`: kolor tła `#f4f4f4`, czcionka `Arial, sans-serif`,
    2. dla `h1`: kolor `#1a237e`, rozmiar 36px,
    3. dla wszystkich akapitów: kolor `#333333`.
4. Sprawdź, jakiego koloru jest akapit `p1`. Który styl „wygrał” i dlaczego? Odpowiedź zapisz w komentarzu CSS `/* ... */` na końcu pliku `styl.css`.
5. Przenieś style wewnętrzne i liniowy do pliku `styl.css` (dla `p1` użyj selektora `#p1`). W pliku HTML ma nie zostać żaden styl.
6. Sprawdź plik CSS w [walidatorze CSS W3C](https://jigsaw.w3.org/css-validator/#validate_by_input).

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Otwórz narzędzia deweloperskie (++f12++), zaznacz nagłówek `h1` i w panelu **Styles** zmień jego kolor, klikając kwadracik koloru. Znajdź kolor, który Ci się podoba, i przepisz jego wartość do pliku CSS.

## Czy potrafię…?

- [ ] nazwać części reguły CSS
- [ ] dołączyć zewnętrzny arkusz stylów
- [ ] wymienić trzy sposoby dołączania stylów i wskazać najlepszy
- [ ] sprawdzić CSS w walidatorze
