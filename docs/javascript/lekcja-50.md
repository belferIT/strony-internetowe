# Lekcja 50. Zdarzenia myszy i klawiatury

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- uruchomić funkcję po kliknięciu, najechaniu myszą lub naciśnięciu klawisza,
- przypisać obsługę zdarzenia atrybutem HTML i metodą `addEventListener`,
- odczytać informacje o zdarzeniu (który klawisz, który element).

## Wprowadzenie

**Zdarzenie** to coś, co dzieje się na stronie: kliknięcie, ruch myszy, naciśnięcie klawisza, wpisanie tekstu.

=== "addEventListener (zalecane)"

    ```html
    <button id="btn">Kliknij</button>
    ```
    ```js
    const btn = document.getElementById("btn");
    btn.addEventListener("click", function () {
        alert("Kliknięto!");
    });
    ```

=== "Atrybut HTML (spotykany na egzaminie)"

    ```html
    <button onclick="pokaz()">Kliknij</button>
    ```
    ```js
    function pokaz() {
        alert("Kliknięto!");
    }
    ```

| Zdarzenie | Kiedy zachodzi |
|---|---|
| `click`, `dblclick` | kliknięcie, dwuklik |
| `mouseover`, `mouseout` | kursor wjeżdża na element / opuszcza go |
| `mousemove` | ruch myszy nad elementem |
| `keydown`, `keyup` | naciśnięcie / puszczenie klawisza |
| `input` | zmiana treści pola (przy każdym znaku) |
| `change` | zmiana wartości pola (po zatwierdzeniu, np. w `select`) |
| `submit` | wysłanie formularza |
| `load`, `DOMContentLoaded` | strona się wczytała |

### Obiekt zdarzenia

```js
document.addEventListener("keydown", function (e) {
    console.log(e.key);           // naciśnięty klawisz, np. "a", "Enter", "ArrowUp"
});

pole.addEventListener("mousemove", function (e) {
    console.log(e.offsetX, e.offsetY);   // pozycja kursora w elemencie
});

lista.addEventListener("click", function (e) {
    console.log(e.target);        // element, który kliknięto
});
```

## Zadanie główne (25 min)

Pobierz [zdarzenia.html](../pliki/lekcja-50/zdarzenia.html){ download }. Utwórz `skrypt.js`. Do obsługi zdarzeń używaj `addEventListener`.

1. **Licznik.** Kliknięcie przycisku `#plus` zwiększa liczbę w `#licznik` o 1, a `#minus` zmniejsza o 1. Liczba nie może spaść poniżej 0.
2. **Żarówka.** Najechanie kursorem na blok `#zarowka` zmienia jego tło na `#ffeb3b`, a zjechanie przywraca `#9e9e9e`.
3. **Echo.** Wpisywanie tekstu w pole `#tekst` od razu wypisuje ten tekst wielkimi literami w akapicie `#echo` (zdarzenie `input`, metoda `.toUpperCase()`). Pod spodem wyświetl liczbę znaków.
4. **Klawisze.** Naciśnięcie dowolnego klawisza na stronie wypisuje jego nazwę w `#klawisz`.
5. **Kwadrat.** Klawisze strzałek przesuwają blok `#kwadrat` o 10px (zmiana `style.left` i `style.top`; blok ma już `position: relative`).
6. **Współrzędne.** Ruch myszy nad blokiem `#plotno` wypisuje w nim współrzędne kursora: `x: 120, y: 45`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Kliknięcie dowolnego elementu listy `#zakupy` przekreśla go (zmiana `style.textDecoration`). Użyj **jednego** `addEventListener` na liście i `e.target` (to tzw. *delegacja zdarzeń*).

## Czy potrafię…?

- [ ] przypisać funkcję do kliknięcia przycisku
- [ ] obsłużyć najechanie i zjechanie kursorem
- [ ] odczytać naciśnięty klawisz
- [ ] wyjaśnić różnicę między zdarzeniem `input` a `change`
