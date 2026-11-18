# Lekcja 59. Dane z sieci: fetch i JSON

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest format JSON i API,
- pobrać dane z pliku lub serwera funkcją `fetch`,
- wyświetlić pobrane dane na stronie,
- obsłużyć błąd pobierania.

## Wprowadzenie

**JSON** (*JavaScript Object Notation*) to tekstowy format wymiany danych, oparty na zapisie obiektów i tablic JavaScript. Nazwy właściwości i teksty są zawsze w **cudzysłowach podwójnych**.

```json
{ "imie": "Anna", "klasa": "1TP", "srednia": 4.75, "zainteresowania": ["grafika", "CSS"] }
```

**API** to adres na serwerze, który zamiast strony HTML zwraca dane, najczęściej w JSON.

```js
async function wczytaj() {
    try {
        const odpowiedz = await fetch("uczniowie.json");      // żądanie HTTP
        if (!odpowiedz.ok) {
            throw new Error("Błąd HTTP " + odpowiedz.status);
        }
        const dane = await odpowiedz.json();                   // tekst JSON → tablica/obiekt
        console.log(dane);
    } catch (blad) {
        document.getElementById("wynik").textContent = "Nie udało się pobrać danych: " + blad.message;
    }
}
wczytaj();
```

| Element | Znaczenie |
|---|---|
| `async` | funkcja, w której można czekać na wynik (`await`) |
| `await` | poczekaj, aż dane przyjdą z sieci, nie blokując strony |
| `odpowiedz.ok` | `true` dla kodów 200–299 |
| `try … catch` | obsługa błędów (brak sieci, zły adres) |

!!! warning "Uruchamiaj przez serwer"
    `fetch` nie działa dla stron otwartych bezpośrednio z dysku (`file://`). Uruchom stronę przez **Live Server** w VS Code.

## Zadanie główne (25 min)

**Część A. Plik JSON (12 min).** Pobierz [uczniowie.json](../pliki/lekcja-59/uczniowie.json){ download } i zapisz obok swojej strony.

1. Pobierz plik funkcją `fetch` i wyświetl uczniów jako karty: imię i nazwisko (nagłówek), klasa, średnia, zainteresowania oddzielone przecinkami.
2. Karty uczniów ze średnią co najmniej 4,75 mają klasę `wyroznienie` (np. złota ramka).
3. Zmień w kodzie nazwę pliku na nieistniejącą. Czy strona pokazuje czytelny komunikat błędu?

**Część B. Prawdziwe API (13 min).** Serwis [Open-Meteo](https://open-meteo.com/) udostępnia prognozę pogody za darmo i bez rejestracji.

1. Pobierz dane z adresu:
   `https://api.open-meteo.com/v1/forecast?latitude=53.56&longitude=14.83&current=temperature_2m,wind_speed_10m&timezone=Europe/Warsaw`
2. Otwórz ten adres najpierw w przeglądarce i obejrzyj strukturę JSON.
3. Wyświetl na stronie: **Goleniów: 4.2°C, wiatr 12.5 km/h** (wartości z pól `current.temperature_2m` i `current.wind_speed_10m`).
4. Dodaj przycisk **Odśwież**, który pobiera dane ponownie.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj listę rozwijaną z trzema miastami (Goleniów, Szczecin, Kraków). Znajdź ich współrzędne geograficzne i pobieraj pogodę dla wybranego miasta. Dodaj prognozę na 3 dni (parametr `daily=temperature_2m_max,temperature_2m_min`).

## Czy potrafię…?

- [ ] zapisać dane w formacie JSON
- [ ] pobrać dane funkcją `fetch` z `async` i `await`
- [ ] wyświetlić pobrane dane na stronie
- [ ] obsłużyć błąd pobierania
