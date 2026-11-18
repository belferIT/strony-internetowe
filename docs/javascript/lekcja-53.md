# Lekcja 53. Tablice

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- utworzyć tablicę i odczytać jej elementy,
- dodawać i usuwać elementy,
- przechodzić po tablicy pętlą,
- szukać, sumować i sortować dane w tablicy.

## Wprowadzenie

```js
const oceny = [5, 3, 4, 6, 2];     // tablica: numeracja od 0!
console.log(oceny[0]);             // 5  (pierwszy element)
console.log(oceny.length);         // 5  (liczba elementów)
console.log(oceny[oceny.length - 1]);  // 2 (ostatni)
oceny[1] = 4;                      // zmiana elementu
```

| Metoda | Działanie |
|---|---|
| `push(x)` / `pop()` | dodaje na końcu / usuwa z końca |
| `unshift(x)` / `shift()` | dodaje na początku / usuwa z początku |
| `indexOf(x)` | pozycja elementu lub `-1`, gdy go nie ma |
| `includes(x)` | czy tablica zawiera element (`true` / `false`) |
| `join(", ")` | łączy elementy w tekst |
| `sort()` | sortuje (teksty alfabetycznie) |
| `sort((a, b) => a - b)` | sortuje liczby rosnąco |
| `reverse()` | odwraca kolejność |
| `splice(i, n)` | usuwa `n` elementów od pozycji `i` |

```js
// pętla klasyczna
for (let i = 0; i < oceny.length; i++) {
    console.log(`Ocena ${i + 1}: ${oceny[i]}`);
}

// pętla for…of: kolejne wartości
let suma = 0;
for (const o of oceny) {
    suma += o;
}
const srednia = suma / oceny.length;
```

!!! warning "Sortowanie liczb"
    `[10, 9, 100].sort()` daje `[10, 100, 9]`, bo bez funkcji porównującej liczby są sortowane jak teksty. Zawsze używaj `sort((a, b) => a - b)`.

## Zadanie główne (25 min)

Pobierz [tablice.html](../pliki/lekcja-53/tablice.html){ download }. W skrypcie umieść tablicę:

```js
const temperatury = [3, -2, 5, 8, 1, -4, 6];   // pon.–niedz.
const dni = ["pon.", "wt.", "śr.", "czw.", "pt.", "sob.", "niedz."];
```

Wyniki wpisuj do elementów strony o podanych identyfikatorach.

1. `#lista`: lista `<li>` w formacie **pon.: 3°C** dla wszystkich dni.
2. `#srednia`: średnia temperatura tygodnia z jedną cyfrą po przecinku.
3. `#max`: najwyższa temperatura i dzień, w którym wystąpiła (wyszukaj w pętli, bez `Math.max`).
4. `#mroz`: liczba dni z temperaturą poniżej zera.
5. `#posortowane`: temperatury posortowane rosnąco, oddzielone przecinkami. **Uwaga:** tablica `temperatury` ma się nie zmienić (zrób kopię: `[...temperatury]`).
6. Przycisk `#dodaj`: pobiera liczbę z pola `#nowa`, dopisuje ją na koniec tablicy, dopisuje do `dni` tekst **dzień 8** (9, 10…) i odświeża wszystkie wyniki. Zamień kod punktów 1–5 na funkcję `odswiez()`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wykonaj punkty 2, 4 i 5 metodami tablic: `reduce()`, `filter()` i `toSorted()`. Porównaj długość kodu.

## Czy potrafię…?

- [ ] odczytać pierwszy i ostatni element tablicy
- [ ] dodać i usunąć element tablicy
- [ ] obliczyć sumę i średnią elementów w pętli
- [ ] poprawnie posortować liczby
