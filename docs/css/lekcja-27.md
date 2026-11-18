# Lekcja 27. Stylowanie formularzy

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- ujednolicić wygląd pól formularza,
- wyróżnić pole aktywne (`:focus`) i przycisk pod kursorem,
- ułożyć etykiety nad polami,
- pokazać pola poprawnie i błędnie wypełnione (`:valid`, `:invalid`).

## Wprowadzenie

```css
input, select, textarea {
    width: 100%;
    padding: 8px;
    border: 1px solid #90a4ae;
    border-radius: 4px;
    font-family: inherit;       /* pola nie dziedziczą czcionki same z siebie */
    font-size: 16px;
}
input:focus {
    border-color: #1e88e5;
    outline: none;
    box-shadow: 0 0 0 3px rgba(30, 136, 229, 0.3);
}
label { display: block; margin-top: 12px; }   /* etykieta nad polem */
```

| Pseudoklasa | Kiedy działa |
|---|---|
| `:focus` | pole jest aktywne (kursor w polu) |
| `:hover` | kursor myszy nad elementem |
| `:checked` | zaznaczony checkbox lub radio |
| `:disabled` | pole wyłączone atrybutem `disabled` |
| `:required` | pole z atrybutem `required` |
| `:valid` / `:invalid` | wartość spełnia / nie spełnia warunków HTML5 (`required`, `type="email"`, `min`…) |

!!! warning "Nie usuwaj obrysu bez zamiennika"
    `outline: none` usuwa obrys pola aktywnego. Osoby korzystające z klawiatury nie widzą wtedy, gdzie są. Jeśli go usuwasz, daj inne wyraźne wyróżnienie, np. `box-shadow`.

## Zadanie główne (25 min)

Pobierz [formularz.html](../pliki/lekcja-27/formularz.html){ download }. Utwórz `styl.css` i dołącz go.

1. `form`: szerokość 400px, wyśrodkowany, tło `#ffffff`, margines wewnętrzny 25px, zaokrąglenie 8px, cień `0 2px 8px rgba(0,0,0,0.15)`. Tło strony: `#e8eaf6`.
2. Etykiety (`label`) nad polami, pogrubione, margines górny 12px.
3. Pola tekstowe, e-mail, `select` i `textarea`: szerokość 100%, margines wewnętrzny 8px, obramowanie 1px `#9fa8da`, zaokrąglenie 4px, czcionka dziedziczona. Pamiętaj o `box-sizing: border-box`, żeby pola nie wychodziły poza formularz.
4. Pole aktywne: obramowanie `#3949ab` i cień jak we wprowadzeniu.
5. `textarea`: wysokość 100px, możliwa zmiana rozmiaru tylko w pionie (`resize: vertical`).
6. Przycisk: szerokość 100%, tło `#3949ab`, biały tekst, bez obramowania, margines wewnętrzny 12px, zaokrąglenie 4px, kursor `pointer`, margines górny 20px; po najechaniu tło `#283593`.
7. Pole e-mail, gdy jest niepoprawnie wypełnione i nieaktywne (`input[type="email"]:invalid:not(:focus)`): obramowanie `#e53935`.
8. Etykieta przy zaznaczonej zgodzie (`input:checked + span`): kolor `#2e7d32`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Użyj pseudoklasy `:user-invalid`, która pokazuje błąd dopiero po interakcji użytkownika z polem. Porównaj z `:invalid`: czym się różnią po otwarciu strony?

## Czy potrafię…?

- [ ] ujednolicić wygląd pól różnego typu
- [ ] wyróżnić pole aktywne
- [ ] ustawić etykiety nad polami
- [ ] wyróżnić błędnie wypełnione pole
