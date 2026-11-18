# Lekcja 58. Zapamiętywanie danych w przeglądarce: localStorage

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zapisać dane w pamięci przeglądarki i odczytać je po odświeżeniu strony,
- zapisywać tablice i obiekty za pomocą JSON,
- zbudować listę zadań, która nie znika po zamknięciu karty.

## Wprowadzenie

Zmienne JavaScript znikają po odświeżeniu strony. **localStorage** przechowuje dane w przeglądarce na stałe (do czasu usunięcia), osobno dla każdej domeny.

```js
localStorage.setItem("imie", "Ola");       // zapis (zawsze tekst)
const imie = localStorage.getItem("imie"); // odczyt; null, gdy brak
localStorage.removeItem("imie");           // usunięcie jednego wpisu
localStorage.clear();                      // usunięcie wszystkiego
```

### Tablice i obiekty: JSON

localStorage przechowuje tylko tekst. Tablicę zamieniasz na tekst JSON i z powrotem:

```js
const zadania = ["Zrobić stronę", "Nauczyć się JS"];
localStorage.setItem("zadania", JSON.stringify(zadania));       // tablica → tekst

const odczyt = JSON.parse(localStorage.getItem("zadania")) || [];  // tekst → tablica
```

`|| []` zabezpiecza przed pierwszym uruchomieniem, gdy w pamięci nic jeszcze nie ma.

!!! tip "Podgląd zawartości"
    Narzędzia deweloperskie → **Application** (Chrome) lub **Storage** (Firefox) → *Local Storage*. Możesz tam podejrzeć, zmienić i usunąć zapisane dane.

!!! warning "Nie dla haseł"
    localStorage może odczytać każdy skrypt na stronie. Nie zapisuj tam haseł ani danych wrażliwych.

## Zadanie główne (25 min)

Utwórz aplikację **Lista zadań** (`index.html`, `styl.css`, `skrypt.js`).

1. Pole tekstowe i przycisk **Dodaj**: dodaje zadanie na listę `ul`. Puste zadanie nie jest dodawane. Zadanie można też dodać klawiszem ++enter++.
2. Każde zadanie ma przycisk **✕**, który je usuwa.
3. Kliknięcie tekstu zadania oznacza je jako wykonane (przekreślenie, klasa `zrobione`) lub odznacza.
4. Zadania przechowuj w tablicy obiektów `{ tekst: "…", zrobione: false }`.
5. Po każdej zmianie zapisz tablicę w localStorage. Po wczytaniu strony odczytaj ją i wyświetl listę.
6. Pod listą wyświetl licznik: **Do zrobienia: 3 z 5**.
7. Przycisk **Usuń wykonane** usuwa wszystkie zadania oznaczone jako wykonane.
8. Sprawdź: dodaj zadania, zamknij kartę, otwórz stronę ponownie.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zapamiętuj w localStorage także wybrany motyw strony (jasny/ciemny z lekcji 37), tak aby po ponownym wejściu strona otwierała się w ostatnio wybranym motywie.

## Czy potrafię…?

- [ ] zapisać i odczytać wartość z localStorage
- [ ] zapisać tablicę obiektów za pomocą JSON
- [ ] zabezpieczyć odczyt przed brakiem danych
- [ ] podejrzeć zapisane dane w narzędziach deweloperskich
