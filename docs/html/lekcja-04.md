# Lekcja 4. Nagłówki, akapity i formatowanie tekstu

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zbudować hierarchię treści z nagłówków `h1`–`h6`,
- dzielić tekst na akapity i łamać wiersze,
- wyróżniać fragmenty tekstu właściwymi znacznikami,
- wstawiać znaki specjalne za pomocą encji.

## Wprowadzenie

### Nagłówki i akapity

```html
<h1>Tytuł strony</h1>          <!-- tylko jeden na stronie -->
<h2>Rozdział</h2>
<h3>Podrozdział</h3>
<p>Akapit tekstu. Przeglądarka sama zawija wiersze.<br>
   Znacznik br wymusza nowy wiersz.</p>
<hr>                           <!-- linia oddzielająca -->
```

!!! warning "Nagłówki nie służą do powiększania tekstu"
    Nagłówek wybierasz według **ważności** treści, a nie wielkości liter. Po `h2` przychodzi `h3`, a nie `h5`. Wygląd ustawisz później w CSS.

### Wyróżnianie tekstu

| Znacznik | Znaczenie | Wygląd domyślny |
|---|---|---|
| `<strong>` | ważny tekst | **pogrubienie** |
| `<em>` | akcent, nacisk | *kursywa* |
| `<b>` / `<i>` | pogrubienie / kursywa bez szczególnego znaczenia | **b** / *i* |
| `<mark>` | zaznaczenie | <mark>tło</mark> |
| `<sub>` / `<sup>` | indeks dolny / górny | H<sub>2</sub>O / m<sup>2</sup> |
| `<small>` | drobny druk | mniejsza czcionka |
| `<code>` | fragment kodu | `czcionka stała` |

### Encje, czyli znaki specjalne

| Zapis | Znak | Kiedy |
|---|---|---|
| `&lt;` `&gt;` | < > | gdy chcesz pokazać znacznik na stronie |
| `&amp;` | & | znak „i” (ampersand) |
| `&nbsp;` | twarda spacja | np. `5&nbsp;km`, żeby liczba nie została na końcu wiersza |
| `&copy;` | © | prawa autorskie |
| `&quot;` | " | cudzysłów w atrybucie |

## Zadanie główne (25 min)

Pobierz plik [historia-www.txt](../pliki/lekcja-04/historia-www.txt){ download }. Zawiera tekst bez znaczników.

1. Utwórz plik `historia.html` z poprawnym szkieletem HTML5 (tytuł karty: **Historia WWW**).
2. Wklej tekst do `body` i oznacz go znacznikami:
    1. tytuł artykułu: nagłówek 1. stopnia,
    2. tytuły rozdziałów (wiersze zaczynające się od `##`): nagłówki 2. stopnia; usuń znaki `##`,
    3. każdy akapit w osobnym `p`.
3. Wyróżnij:
    1. nazwiska osób znacznikiem `strong`,
    2. nazwy języków i protokołów (HTML, HTTP, URL) znacznikiem `code`,
    3. zdanie z ostatniego akapitu zaczynające się od „Pamiętaj” znacznikiem `mark`.
4. W zdaniu o pierwszej stronie zapisz znacznik `<html>` tak, aby był widoczny na stronie (encje).
5. Na końcu dodaj linię poziomą i stopkę: `© 2026 Imię Nazwisko` w znaczniku `small`, użyj encji `&copy;`.
6. Sprawdź stronę w walidatorze W3C.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do artykułu cytat z tagiem `blockquote` i podpisem w `cite` oraz skrót `<abbr title="HyperText Markup Language">HTML</abbr>`. Najedź myszą na skrót: co się wyświetla? Komu pomaga ten znacznik?

## Czy potrafię…?

- [ ] dobrać poziom nagłówka do ważności treści
- [ ] wyjaśnić różnicę między `strong` a `b`
- [ ] wyświetlić na stronie znak `<`
- [ ] użyć twardej spacji
