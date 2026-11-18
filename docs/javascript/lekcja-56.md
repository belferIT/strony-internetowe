# Lekcja 56. Timery: setTimeout i setInterval

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- uruchomić kod z opóźnieniem (`setTimeout`),
- powtarzać kod co określony czas (`setInterval`),
- zatrzymać timer (`clearInterval`),
- zbudować zegar, stoper i automatyczny pokaz slajdów.

## Wprowadzenie

```js
// jednorazowo po 2 sekundach (czas w milisekundach)
setTimeout(function () {
    alert("Minęły 2 sekundy");
}, 2000);

// co 1 sekundę, aż do zatrzymania
let sekundy = 0;
const timer = setInterval(function () {
    sekundy++;
    document.getElementById("czas").textContent = sekundy;
    if (sekundy === 10) {
        clearInterval(timer);     // zatrzymanie
    }
}, 1000);
```

| Funkcja | Działanie |
|---|---|
| `setTimeout(funkcja, ms)` | uruchamia funkcję raz, po `ms` milisekundach |
| `setInterval(funkcja, ms)` | uruchamia funkcję co `ms` milisekund |
| `clearTimeout(id)`, `clearInterval(id)` | zatrzymuje timer o podanym identyfikatorze |

!!! warning "Podwójny start"
    Gdy użytkownik kliknie **Start** dwa razy, uruchomisz dwa timery i czas popędzi dwa razy szybciej. Przed uruchomieniem sprawdź, czy timer już działa, albo najpierw go zatrzymaj.

### Formatowanie czasu

```js
const s = 75;
const min = Math.floor(s / 60);
const sek = s % 60;
const tekst = `${min}:${String(sek).padStart(2, "0")}`;   // "1:15"
```

## Zadanie główne (25 min)

Pobierz i rozpakuj [timery.zip](../pliki/lekcja-56/timery.zip){ download }. Utwórz `skrypt.js` i dołącz go.

1. **Komunikat.** 3 sekundy po wczytaniu strony pojawia się (zdjęcie klasy `ukryty`) baner `#powitanie`.
2. **Stoper.** Przyciski **Start**, **Stop**, **Zeruj** sterują stoperem w `#stoper`. Format czasu: `M:SS` (np. `2:05`). Podwójne kliknięcie **Start** nie przyspiesza stopera.
3. **Odliczanie.** Po kliknięciu **Odliczaj** w `#odliczanie` pojawia się liczba z pola `#sekundy`, zmniejszana co sekundę. Przy zerze wyświetl **Koniec czasu!** i zatrzymaj timer.
4. **Pokaz slajdów.** Obraz `#slajd` zmienia się co 3 sekundy na kolejny z tablicy `["obrazy/foto1.jpg", …, "obrazy/foto4.jpg"]`, w kółko. Przycisk **Pauza** zatrzymuje pokaz, a ponowne kliknięcie wznawia; napis przycisku zmienia się na **Wznów**.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Gra w refleks: po kliknięciu **Gotów** po losowym czasie (1–5 s) blok zmienia kolor na zielony. Zmierz czas od zmiany koloru do kliknięcia bloku (`Date.now()`). Kliknięcie przed zmianą koloru to falstart.

## Czy potrafię…?

- [ ] uruchomić kod z opóźnieniem
- [ ] uruchomić i zatrzymać timer powtarzający
- [ ] zabezpieczyć się przed podwójnym uruchomieniem timera
- [ ] sformatować czas w zapisie `M:SS`
