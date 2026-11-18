# Lekcja 45. Wprowadzenie do JavaScript: zmienne i typy danych

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- dołączyć skrypt JavaScript do strony,
- wypisywać wartości w konsoli przeglądarki,
- deklarować zmienne `let` i `const`,
- rozpoznawać podstawowe typy danych.

## Wprowadzenie

HTML to treść, CSS to wygląd, a **JavaScript** to zachowanie strony: reakcja na kliknięcia, obliczenia, zmiana treści bez przeładowania. Skrypt wykonuje przeglądarka, czyli działa **po stronie klienta**.

```html
<!-- skrypt w osobnym pliku, na końcu body -->
<body>
    ...
    <script src="skrypt.js"></script>
</body>
```

```js
// komentarz jednowierszowy
/* komentarz
   wielowierszowy */

console.log("Witaj w konsoli!");      // wypisuje w konsoli (F12 → Console)

let wiek = 15;                        // zmienna: wartość może się zmieniać
const szkola = "ZS nr 1";             // stała: nie można jej przypisać nowej wartości
wiek = wiek + 1;

console.log("Wiek:", wiek);
console.log(`Chodzę do ${szkola} i mam ${wiek} lat.`);  // szablon tekstowy (grawis `)
```

### Typy danych

| Typ | Przykład | `typeof` |
|---|---|---|
| liczba | `15`, `3.14`, `-2` | `"number"` |
| tekst | `"Ala"`, `'kot'`, `` `szablon` `` | `"string"` |
| wartość logiczna | `true`, `false` | `"boolean"` |
| brak wartości | `undefined`, `null` | `"undefined"`, `"object"` |
| tablica, obiekt | `[1, 2]`, `{ imie: "Ala" }` | `"object"` |

!!! warning "Tekst i liczba"
    `"5" + 3` daje `"53"` (sklejenie tekstów), a `5 + 3` daje `8`. Dane z formularzy i z `prompt()` są zawsze tekstem. Zamieniasz je na liczbę funkcją `Number()`, `parseInt()` lub `parseFloat()`.

| Wbudowane okna | Działanie |
|---|---|
| `alert("Tekst")` | komunikat z przyciskiem OK |
| `prompt("Pytanie")` | pole do wpisania tekstu, zwraca tekst |
| `confirm("Pytanie")` | OK / Anuluj, zwraca `true` / `false` |

## Zadanie główne (25 min)

Utwórz w folderze `lekcja-45` pliki `index.html` (tytuł karty: **Pierwszy skrypt**) i `skrypt.js`. Dołącz skrypt na końcu `body`. Wyniki sprawdzaj w konsoli (++f12++ → **Console**).

1. Wypisz w konsoli tekst **Działa!**.
2. Zadeklaruj stałe `imie` i `nazwisko` z Twoimi danymi oraz zmienną `wiek`. Wypisz zdanie `Nazywam się Jan Kowalski i mam 15 lat.` za pomocą szablonu tekstowego.
3. Zwiększ wiek o 1 i wypisz zdanie `Za rok będę mieć 16 lat.`
4. Spróbuj przypisać nową wartość do stałej `imie`. Przepisz do komentarza komunikat błędu z konsoli, a następnie zakomentuj błędną linię.
5. Wypisz typ (`typeof`) pięciu wartości: `42`, `"42"`, `true`, `undefined`, `[1, 2, 3]`.
6. Za pomocą `prompt()` zapytaj użytkownika o rok urodzenia. Oblicz i wypisz w `alert()` jego wiek w roku 2026. Sprawdź, co się stanie bez zamiany na liczbę, gdy dodasz do odpowiedzi liczbę 1.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź w konsoli wyniki: `0.1 + 0.2`, `"10" - 3`, `"10" * "2"`, `true + 1`, `[] + []`. Które Cię zaskoczyły? Dowiedz się, dlaczego `0.1 + 0.2` nie daje dokładnie `0.3`.

## Czy potrafię…?

- [ ] dołączyć plik JS do strony
- [ ] wypisać wartość w konsoli
- [ ] wyjaśnić różnicę między `let` a `const`
- [ ] zamienić tekst na liczbę
