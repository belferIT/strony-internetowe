# Lekcja 3. Struktura dokumentu HTML5

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1), (7) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować poprawny szkielet dokumentu HTML5,
- odróżnić znacznik, element i atrybut,
- sprawdzić poprawność strony walidatorem W3C.

## Wprowadzenie

Każda strona internetowa to plik tekstowy z rozszerzeniem `.html`. Przeglądarka czyta go od góry do dołu i na podstawie **znaczników** buduje to, co widzisz na ekranie.

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Moja pierwsza strona</title>
</head>
<body>
    <h1>Witaj!</h1>
    <p>To jest mój pierwszy akapit.</p>
</body>
</html>
```

| Fragment | Do czego służy |
|---|---|
| `<!DOCTYPE html>` | informuje przeglądarkę, że to dokument HTML5 |
| `<html lang="pl">` | element główny; atrybut `lang` podaje język strony |
| `<head>` | informacje o stronie (niewidoczne w oknie): kodowanie, tytuł, style |
| `<meta charset="UTF-8">` | kodowanie znaków, dzięki któremu działają polskie litery |
| `<title>` | tytuł widoczny na karcie przeglądarki |
| `<body>` | treść widoczna dla użytkownika |

!!! info "Znacznik, element, atrybut"
    - **Znacznik** to zapis w nawiasach ostrych, np. `<p>` (otwierający) i `</p>` (zamykający).
    - **Element** to znacznik otwierający + treść + znacznik zamykający: `<p>Tekst</p>`.
    - **Atrybut** to dodatkowa informacja w znaczniku otwierającym: `<html lang="pl">`.

!!! tip "Skrót w VS Code"
    W pustym pliku `.html` wpisz `!` i naciśnij ++tab++. VS Code wstawi gotowy szkielet dokumentu.

## Zadanie główne (25 min)

Pobierz plik startowy [wizytowka.html](../pliki/lekcja-03/wizytowka.html){ download } i otwórz go w VS Code.

1. Plik zawiera błędy w strukturze. Popraw je tak, aby dokument miał poprawny szkielet HTML5.
2. Ustaw język dokumentu na polski i kodowanie na UTF-8.
3. Nadaj stronie tytuł **Wizytówka – Twoje imię i nazwisko**.
4. W `body` umieść:
    - nagłówek pierwszego stopnia z Twoim imieniem,
    - dwa akapity: o Twojej szkole i o Twoich zainteresowaniach.
5. Sprawdź stronę w [walidatorze W3C](https://validator.w3.org/#validate_by_input) (zakładka *Validate by Direct Input*). Strona ma przejść walidację bez błędów.

??? question "Podpowiedź do punktu 1"
    Sprawdź, czy każdy znacznik otwierający ma znacznik zamykający i czy `title` jest wewnątrz `head`, a nie `body`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Otwórz narzędzia deweloperskie (++f12++), zakładkę **Elements**. Zmień w nich treść nagłówka bez edytowania pliku. Odśwież stronę (++f5++). Co się stało i dlaczego?

## Czy potrafię…?

- [ ] napisać z pamięci szkielet dokumentu HTML5
- [ ] wyjaśnić różnicę między `head` a `body`
- [ ] wyjaśnić, czym jest atrybut, i podać przykład
- [ ] sprawdzić stronę w walidatorze W3C
