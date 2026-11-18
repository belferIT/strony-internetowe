# Lekcja 5. Listy

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- tworzyć listy punktowane, numerowane i listy definicji,
- zmieniać sposób numerowania list,
- zagnieżdżać listy.

## Wprowadzenie

=== "Lista punktowana"

    ```html
    <ul>
        <li>mąka</li>
        <li>mleko</li>
    </ul>
    ```

=== "Lista numerowana"

    ```html
    <ol type="A" start="3">
        <li>Wymieszaj składniki.</li>
        <li>Odstaw na 10 minut.</li>
    </ol>
    ```

=== "Lista definicji"

    ```html
    <dl>
        <dt>HTML</dt>
        <dd>język znaczników opisujący strukturę strony</dd>
        <dt>CSS</dt>
        <dd>język opisujący wygląd strony</dd>
    </dl>
    ```

| Atrybut `ol` | Wartości | Działanie |
|---|---|---|
| `type` | `1`, `a`, `A`, `i`, `I` | rodzaj numeracji |
| `start` | liczba | od której liczby zacząć |
| `reversed` | (bez wartości) | numeracja malejąca |

### Lista zagnieżdżona

Lista wewnętrzna jest **wewnątrz elementu `li`**, a nie między elementami `li`:

```html
<ul>
    <li>Owoce
        <ul>
            <li>jabłka</li>
            <li>gruszki</li>
        </ul>
    </li>
    <li>Warzywa</li>
</ul>
```

!!! warning "Częsty błąd na egzaminie"
    Wewnątrz `ul` i `ol` mogą być **tylko** elementy `li`. Zagnieżdżona lista poza `li` nie przejdzie walidacji.

## Zadanie główne (25 min)

Pobierz plik [nalesniki.txt](../pliki/lekcja-05/nalesniki.txt){ download } i utwórz stronę `nalesniki.html` (tytuł karty: **Przepis na naleśniki**).

1. Nazwę przepisu umieść w nagłówku 1. stopnia, a nazwy części (Składniki, Przygotowanie, Słowniczek) w nagłówkach 2. stopnia.
2. Składniki zapisz jako listę punktowaną.
3. Kroki przygotowania zapisz jako listę numerowaną.
4. Krok 4 (dodatki) ma zawierać zagnieżdżoną listę punktowaną z trzema dodatkami.
5. Słowniczek zapisz jako listę definicji.
6. Na końcu dodaj nagłówek 2. stopnia **Ranking dodatków** i listę numerowaną z trzema pozycjami w kolejności malejącej (3, 2, 1). Użyj atrybutu `reversed`.
7. Sprawdź stronę w walidatorze W3C.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Utwórz spis treści swojego ulubionego podręcznika w postaci list zagnieżdżonych trzypoziomowych: rozdziały numerowane `I, II, III`, podrozdziały `1, 2, 3`, punkty `a, b, c`.

## Czy potrafię…?

- [ ] wybrać odpowiedni rodzaj listy do treści
- [ ] zmienić rodzaj numeracji i liczbę początkową
- [ ] poprawnie zagnieździć listę w elemencie `li`
