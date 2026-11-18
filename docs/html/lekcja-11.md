# Lekcja 11. Formularze, część 1: pola tekstowe i etykiety

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować formularz i określić, dokąd i jak wysyła dane,
- wstawić pola tekstowe różnych typów,
- powiązać pole z etykietą,
- ustawić podpowiedź, wartość domyślną i ograniczenia długości.

## Wprowadzenie

```html
<form action="zapisz.php" method="post">
    <label for="imie">Imię:</label>
    <input type="text" id="imie" name="imie" placeholder="np. Anna">

    <label for="haslo">Hasło:</label>
    <input type="password" id="haslo" name="haslo" maxlength="20">

    <button type="submit">Wyślij</button>
</form>
```

| Atrybut `form` | Znaczenie |
|---|---|
| `action` | adres skryptu, który odbierze dane (na egzaminie najczęściej plik PHP) |
| `method` | `get`: dane widoczne w adresie strony; `post`: dane ukryte w treści żądania |

| Atrybut pola | Znaczenie |
|---|---|
| `name` | nazwa, pod którą dane trafią na serwer (**bez niej pole nie zostanie wysłane**) |
| `id` | identyfikator, do którego odwołuje się etykieta `label for` |
| `placeholder` | szara podpowiedź w pustym polu |
| `value` | wartość domyślna |
| `maxlength`, `size` | maksymalna liczba znaków, szerokość pola w znakach |
| `readonly`, `disabled` | tylko do odczytu / wyłączone (pole wyłączone nie jest wysyłane) |

### Typy pól `input`

| `type` | Pole |
|---|---|
| `text` | zwykły tekst |
| `password` | hasło (kropki zamiast znaków) |
| `email` | adres e-mail |
| `number` | liczba (strzałki góra/dół) |
| `tel` | numer telefonu |
| `date`, `time` | data, godzina (kalendarz) |
| `color` | wybór koloru |
| `range` | suwak |
| `hidden` | pole ukryte |

!!! tip "Po co etykieta?"
    Kliknięcie etykiety powiązanej przez `for` ustawia kursor w polu. Czytnik ekranu czyta etykietę, gdy osoba niewidoma wejdzie w pole. Etykietę można też powiązać, wkładając pole do jej środka: `<label>Imię: <input type="text" name="imie"></label>`.

## Zadanie główne (25 min)

Utwórz stronę `rejestracja.html` (tytuł karty: **Rejestracja**) z nagłówkiem 1. stopnia **Załóż konto w bibliotece**.

1. Formularz wysyła dane metodą `post` do pliku `rejestracja.php`.
2. Pola formularza (każde z etykietą powiązaną przez `for` i `id`, każde w osobnym akapicie):
    1. **Imię**: tekst, podpowiedź `np. Jan`,
    2. **Nazwisko**: tekst, maksymalnie 40 znaków,
    3. **E-mail**: typ e-mail,
    4. **Telefon**: typ telefon, podpowiedź `123 456 789`,
    5. **Data urodzenia**: typ data,
    6. **Hasło**: typ hasło,
    7. **Szkoła**: tekst, wartość domyślna `ZS nr 1 w Goleniowie`, tylko do odczytu,
    8. **Ulubiony kolor**: wybór koloru.
3. Pole ukryte o nazwie `zrodlo` i wartości `strona-www`.
4. Przyciski **Zarejestruj** (wysyła) i **Wyczyść** (`type="reset"`).
5. Wypełnij formularz i zmień `method` na `get`. Wyślij. Co widać w pasku adresu? Zapisz odpowiedź w komentarzu HTML na końcu pliku.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj atrybuty `autocomplete` (`given-name`, `family-name`, `email`, `tel`, `new-password`). Sprawdź, jak przeglądarka podpowiada dane. Dlaczego to ułatwia życie użytkownikom telefonów?

## Czy potrafię…?

- [ ] zbudować formularz i ustawić `action` oraz `method`
- [ ] wyjaśnić różnicę między metodą `get` a `post`
- [ ] powiązać etykietę z polem
- [ ] dobrać typ pola do rodzaju danych
