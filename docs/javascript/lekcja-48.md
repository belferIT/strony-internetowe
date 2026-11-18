# Lekcja 48. Funkcje

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zdefiniować funkcję z parametrami,
- zwrócić wynik instrukcją `return`,
- wywołać funkcję wiele razy z różnymi argumentami,
- odróżnić zmienną lokalną od globalnej.

## Wprowadzenie

Funkcja to nazwany fragment kodu, który możesz uruchamiać wiele razy.

```js
// definicja
function poleProstokata(a, b) {      // a, b – parametry
    return a * b;                     // wynik funkcji
}

// wywołanie
const p1 = poleProstokata(3, 4);      // 3, 4 – argumenty
console.log(p1);                      // 12
console.log(poleProstokata(10, 2));   // 20

// funkcja bez wyniku
function przywitaj(imie) {
    alert(`Cześć, ${imie}!`);
}
przywitaj("Ola");

// funkcja strzałkowa (zapis skrócony)
const kwadrat = (x) => x * x;
```

| Pojęcie | Znaczenie |
|---|---|
| parametr | nazwa w nawiasie przy definicji |
| argument | wartość podana przy wywołaniu |
| `return` | kończy funkcję i zwraca wynik |
| zmienna lokalna | zadeklarowana w funkcji, widoczna tylko w niej |
| zmienna globalna | zadeklarowana poza funkcjami, widoczna wszędzie |

!!! tip "Dobra nazwa funkcji"
    Nazwa mówi, co funkcja robi: `obliczCene()`, `pokazWynik()`, `czyPelnoletni()`. Funkcja zwracająca `true` lub `false` często zaczyna się od `czy…`.

## Zadanie główne (25 min)

Utwórz `index.html` i `skrypt.js`. Każdą funkcję przetestuj co najmniej trzema wywołaniami i wypisz wyniki w konsoli.

1. `poleKola(r)`: zwraca pole koła (`Math.PI * r * r`), zaokrąglone do 2 miejsc po przecinku (`.toFixed(2)`).
2. `czyPelnoletni(wiek)`: zwraca `true` dla wieku od 18 lat, w przeciwnym razie `false`.
3. `cenaBrutto(netto, vat)`: zwraca cenę brutto. Gdy nie podasz `vat`, przyjmij 23 (parametr domyślny: `vat = 23`).
4. `maksimum(a, b, c)`: zwraca największą z trzech liczb **bez** użycia `Math.max`.
5. `silnia(n)`: zwraca n! obliczone w pętli (`5! = 1·2·3·4·5 = 120`).
6. `ocenaSlownie(ocena)`: dla liczb 1–6 zwraca nazwę oceny (`"niedostateczny"` … `"celujący"`), dla innych `"błędna ocena"`.
7. Zadeklaruj zmienną `licznik` wewnątrz funkcji i spróbuj ją wypisać poza funkcją. Zapisz w komentarzu, co się stało i dlaczego.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Napisz funkcję `silniaRek(n)`, która oblicza silnię **rekurencyjnie**, czyli wywołuje samą siebie: `n! = n · (n−1)!`, a `0! = 1`.

## Czy potrafię…?

- [ ] zdefiniować funkcję z parametrami i wywołać ją
- [ ] zwrócić wynik funkcji
- [ ] ustawić wartość domyślną parametru
- [ ] wyjaśnić, czym jest zmienna lokalna
