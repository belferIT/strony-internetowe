# Lekcja 47. Pętle

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- powtarzać instrukcje pętlą `for`, gdy znasz liczbę powtórzeń,
- powtarzać instrukcje pętlą `while`, dopóki spełniony jest warunek,
- przerywać pętlę (`break`) i pomijać krok (`continue`),
- generować fragmenty HTML w pętli.

## Wprowadzenie

```js
// for (początek; warunek; krok)
for (let i = 1; i <= 5; i++) {
    console.log("Powtórzenie nr", i);
}

// while: dopóki warunek jest prawdziwy
let haslo = "";
while (haslo !== "tajne") {
    haslo = prompt("Podaj hasło:");
}

// do…while: wykona się co najmniej raz
let liczba;
do {
    liczba = Number(prompt("Podaj liczbę od 1 do 10"));
} while (liczba < 1 || liczba > 10);
```

| Instrukcja | Działanie |
|---|---|
| `break` | natychmiast kończy pętlę |
| `continue` | pomija resztę bieżącego kroku, przechodzi do następnego |

### Tworzenie HTML w pętli

```js
let html = "";
for (let i = 1; i <= 3; i++) {
    html += `<li>Element ${i}</li>`;
}
document.getElementById("lista").innerHTML = html;
```

!!! warning "Pętla nieskończona"
    Jeśli warunek pętli nigdy nie stanie się fałszywy, przeglądarka się zawiesi. Zamknij wtedy kartę. Sprawdzaj, czy zmienna w warunku zmienia się w każdym kroku.

## Zadanie główne (25 min)

Pobierz [petle.html](../pliki/lekcja-47/petle.html){ download }. Strona ma puste elementy o identyfikatorach `z1`–`z5`. Utwórz `skrypt.js` i wpisz w każdy element wynik zadania przez `document.getElementById("z1").innerHTML = …`.

1. **z1**: liczby od 1 do 20 oddzielone spacją.
2. **z2**: liczby parzyste od 2 do 50 w kolejności malejącej.
3. **z3**: suma liczb od 1 do 100 (wynik: 5050).
4. **z4**: tabliczka mnożenia dla liczby 7 jako lista `<li>7 × 1 = 7</li>` … `<li>7 × 10 = 70</li>`.
5. **z5**: tabela HTML 5×5, w której każda komórka zawiera iloczyn numeru wiersza i kolumny (dwie pętle zagnieżdżone).
6. Na końcu pętlą `do…while` pobieraj liczby przez `prompt()`, dopóki użytkownik nie wpisze 0. Wypisz w `alert()` sumę wpisanych liczb.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

FizzBuzz: wypisz liczby od 1 do 100, ale zamiast wielokrotności 3 wypisz `Fizz`, zamiast wielokrotności 5 `Buzz`, a zamiast wielokrotności 3 i 5 `FizzBuzz`. To klasyczne zadanie z rozmów rekrutacyjnych.

## Czy potrafię…?

- [ ] napisać pętlę `for` z dowolnym krokiem
- [ ] dobrać pętlę `for` lub `while` do zadania
- [ ] użyć `break` i `continue`
- [ ] wygenerować listę lub tabelę HTML w pętli
