# Lekcja 51. Obsługa formularza i obliczenia. Zadanie w stylu egzaminu

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- odczytać wartości z pól tekstowych, list, przycisków radio i pól wyboru,
- wykonać obliczenia na danych z formularza,
- wypisać wynik na stronie,
- wykonać zadanie JavaScript sformułowane jak na egzaminie INF.03.

## Wprowadzenie

```js
// pole tekstowe / liczbowe: zawsze tekst!
const ilosc = Number(document.getElementById("ilosc").value);

// lista rozwijana
const rozmiar = document.getElementById("rozmiar").value;

// przycisk radio: zaznaczony z grupy
const dostawa = document.querySelector('input[name="dostawa"]:checked').value;

// pole wyboru: zaznaczone czy nie
const sos = document.getElementById("sos").checked;     // true / false

// wypisanie wyniku
document.getElementById("wynik").innerHTML = `Do zapłaty: ${kwota.toFixed(2)} zł`;
```

!!! tip "Przycisk w formularzu"
    Przycisk `<button>` wewnątrz `<form>` domyślnie **wysyła formularz** i przeładowuje stronę, a wynik znika. Na egzaminie zwykle nie ma znacznika `form` albo przycisk ma `type="button"`. Jeśli obsługujesz `submit`, zatrzymaj wysłanie: `e.preventDefault()`.

!!! info "Typowy schemat zadania egzaminacyjnego"
    1. Pobierz dane z pól.
    2. Oblicz.
    3. Wypisz wynik w podanym elemencie, w podanym formacie (każda spacja i każdy dwukropek się liczą).

## Zadanie główne (25 min)

Pobierz [pizzeria.html](../pliki/lekcja-51/pizzeria.html){ download }. Strona i style są gotowe. Utwórz `skrypt.js` i dołącz go.

!!! note "Polecenie (styl arkusza INF.03)"
    Po kliknięciu przycisku **Oblicz** skrypt:

    1. Pobiera rozmiar pizzy z listy `rozmiar`. Ceny: mała **22 zł**, średnia **30 zł**, duża **38 zł** (wartości opcji: `22`, `30`, `38`).
    2. Pobiera liczbę pizz z pola `ilosc`.
    3. Za każdy zaznaczony dodatek (`ser`, `pieczarki`, `salami`) dolicza **4 zł do każdej pizzy**.
    4. Pobiera sposób odbioru z przycisków radio `odbior`: odbiór osobisty **0 zł**, dostawa **8 zł** (jednorazowo, niezależnie od liczby pizz).
    5. Jeśli wartość zamówienia przed doliczeniem dostawy przekracza **100 zł**, udziela rabatu **10%** na pizze (dostawa bez rabatu).
    6. Wypisuje w akapicie o identyfikatorze `wynik` tekst: **Koszt zamówienia: X zł**, gdzie X to kwota z dwoma miejscami po przecinku.
    7. Jeśli liczba pizz jest mniejsza niż 1 lub pole jest puste, zamiast kosztu wypisuje: **Podaj poprawną liczbę pizz**.

Sprawdź program na danych:

| Rozmiar | Liczba | Dodatki | Odbiór | Wynik |
|---|---|---|---|---|
| mała | 1 | brak | osobisty | 22.00 zł |
| średnia | 2 | ser | dostawa | 76.00 zł |
| duża | 3 | ser, salami | dostawa | 132.20 zł |
| duża | 0 | – | – | Podaj poprawną liczbę pizz |

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Przelicz koszt automatycznie przy każdej zmianie w formularzu (zdarzenie `input` lub `change` na całym formularzu), bez klikania przycisku.

## Czy potrafię…?

- [ ] odczytać wartość pola tekstowego i zamienić ją na liczbę
- [ ] odczytać zaznaczony przycisk radio
- [ ] sprawdzić, czy pole wyboru jest zaznaczone
- [ ] wypisać wynik z dwoma miejscami po przecinku
