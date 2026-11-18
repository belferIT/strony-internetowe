# Lekcja 57. Obiekty Math i Date: losowanie i prosta gra

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zaokrąglać liczby i losować liczby całkowite z zakresu,
- odczytać bieżącą datę i godzinę,
- obliczyć różnicę dat w dniach,
- napisać prostą grę losową.

## Wprowadzenie

### Math

| Metoda | Wynik |
|---|---|
| `Math.round(4.5)` | 5 (zaokrąglenie) |
| `Math.floor(4.9)` | 4 (w dół) |
| `Math.ceil(4.1)` | 5 (w górę) |
| `Math.abs(-7)` | 7 (wartość bezwzględna) |
| `Math.sqrt(16)`, `Math.pow(2, 3)` | 4, 8 |
| `Math.max(3, 9, 1)`, `Math.min(…)` | 9, 1 |
| `Math.random()` | losowa liczba z przedziału [0, 1) |

```js
// losowa liczba całkowita od min do max (włącznie)
function losuj(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}
losuj(1, 6);   // rzut kostką
```

### Date

```js
const teraz = new Date();
teraz.getFullYear();   // 2026
teraz.getMonth();      // 0–11 (styczeń = 0!)
teraz.getDate();       // dzień miesiąca 1–31
teraz.getDay();        // dzień tygodnia 0–6 (niedziela = 0!)
teraz.getHours();      // 0–23
teraz.toLocaleDateString("pl-PL");   // "18.11.2026"

const wakacje = new Date(2027, 5, 26);          // 26 czerwca 2027 (miesiąc 5!)
const dni = Math.ceil((wakacje - teraz) / (1000 * 60 * 60 * 24));
```

!!! warning "Miesiące od zera"
    W `Date` styczeń to `0`, a grudzień `11`. To najczęstsza pomyłka przy pracy z datami.

## Zadanie główne (25 min)

Utwórz stronę `index.html` i skrypt `skrypt.js`.

1. **Powitanie.** Na górze strony wyświetl dzisiejszą datę w formacie **Dziś jest środa, 18.11.2026** (nazwę dnia weź z tablicy). Zależnie od godziny dodaj: **Dzień dobry!** (5–17) lub **Dobry wieczór!** (pozostałe).
2. **Do wakacji.** Wyświetl, ile dni zostało do 26 czerwca 2027 r.
3. **Kostka.** Przycisk **Rzuć kostką** losuje liczbę 1–6 i wyświetla ją dużą czcionką. Pod spodem licznik rzutów i suma oczek.
4. **Zgadnij liczbę.** Komputer losuje liczbę 1–100 po wczytaniu strony. Użytkownik wpisuje liczbę w pole i klika **Sprawdź**. Strona odpowiada: **Za mało**, **Za dużo** lub **Brawo! Zgadłeś w X próbach**. Przycisk **Nowa gra** losuje nową liczbę i zeruje licznik prób.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Generator haseł: przycisk losuje hasło o długości podanej w polu (8–32 znaki), z liter, cyfr i znaków specjalnych. Gwarantuj, że hasło zawiera co najmniej jeden znak z każdej grupy.

## Czy potrafię…?

- [ ] wylosować liczbę całkowitą z zakresu
- [ ] zaokrąglić liczbę w górę, w dół i do najbliższej
- [ ] odczytać bieżący dzień tygodnia i godzinę
- [ ] obliczyć liczbę dni między datami
