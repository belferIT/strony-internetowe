# Lekcja 46. Operatory i instrukcje warunkowe

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- używać operatorów arytmetycznych, porównania i logicznych,
- podejmować decyzje w programie instrukcją `if … else`,
- wybierać jedną z wielu możliwości instrukcją `switch`.

## Wprowadzenie

### Operatory

| Rodzaj | Operatory |
|---|---|
| arytmetyczne | `+` `-` `*` `/` `%` (reszta z dzielenia) `**` (potęga) |
| przypisania | `=` `+=` `-=` `*=` `++` `--` |
| porównania | `===` (równe), `!==` (różne), `<`, `>`, `<=`, `>=` |
| logiczne | `&&` (i), `||` (lub), `!` (nie) |

!!! warning "`==` czy `===`?"
    `==` porównuje po zamianie typów: `"5" == 5` daje `true`. `===` porównuje też typ: `"5" === 5` daje `false`. Używaj `===` i `!==`.

### Instrukcja warunkowa

```js
const ocena = 4;

if (ocena >= 5) {
    console.log("Świetnie!");
} else if (ocena >= 3) {
    console.log("Dobrze.");
} else {
    console.log("Trzeba poćwiczyć.");
}

// warunek złożony
if (wiek >= 13 && maZgode) { ... }
```

### Instrukcja wyboru

```js
switch (dzien) {
    case 6:
    case 7:
        console.log("Weekend");
        break;          // bez break program wykona też kolejne przypadki
    default:
        console.log("Dzień roboczy");
}
```

## Zadanie główne (25 min)

Utwórz `index.html` i `skrypt.js`. Dane pobieraj przez `prompt()`, wyniki pokazuj w `alert()` lub w konsoli. Pamiętaj o zamianie tekstu na liczbę.

1. **Parzystość.** Pobierz liczbę całkowitą i wypisz, czy jest parzysta (użyj `%`).
2. **Bilet.** Pobierz wiek. Bilet do kina kosztuje: do 6 lat 0 zł, 7–18 lat 18 zł, 19–64 lata 28 zł, od 65 lat 18 zł. Wypisz cenę.
3. **Logowanie.** Pobierz login i hasło. Jeśli login to `admin`, a hasło `Tajne123`, wypisz **Witaj, administratorze!**, w przeciwnym razie **Błędne dane**. Użyj `&&`.
4. **Dzień tygodnia.** Pobierz numer dnia 1–7 i za pomocą `switch` wypisz jego nazwę. Dla innej liczby wypisz **Nie ma takiego dnia**.
5. **Rok przestępny.** Pobierz rok. Rok jest przestępny, gdy dzieli się przez 4 i nie dzieli przez 100 **albo** dzieli się przez 400. Sprawdź program dla lat 2024, 1900, 2000, 2026.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zapisz zadanie 1 w jednej linijce za pomocą operatora warunkowego (trójargumentowego): `warunek ? wartośćGdyPrawda : wartośćGdyFałsz`.

## Czy potrafię…?

- [ ] obliczyć resztę z dzielenia i sprawdzić parzystość
- [ ] wyjaśnić różnicę między `==` a `===`
- [ ] zbudować warunek złożony z `&&` i `||`
- [ ] użyć `switch` z `break` i `default`
