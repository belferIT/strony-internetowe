# Lekcja 37. Zmienne CSS i tryb ciemny

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2), (6) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- definiować i używać zmiennych CSS (*custom properties*),
- zmienić kolorystykę całej strony w jednym miejscu,
- przygotować tryb ciemny zgodny z ustawieniem systemu.

## Wprowadzenie

### Zmienne CSS

```css
:root {                         /* zmienne globalne, dostępne w całym dokumencie */
    --kolor-glowny: #3949ab;
    --kolor-tla: #ffffff;
    --kolor-tekstu: #212121;
    --odstep: 16px;
}
h1 { color: var(--kolor-glowny); }
.karta { padding: var(--odstep); }
.przycisk { background: var(--kolor-akcentu, orange); }  /* wartość zapasowa */
```

Nazwa zmiennej zaczyna się od dwóch myślników. Wartość odczytujesz funkcją `var()`.

### Tryb ciemny

System operacyjny (Windows, Android, iOS) ma ustawienie trybu jasnego i ciemnego. Strona może je odczytać:

```css
@media (prefers-color-scheme: dark) {
    :root {
        --kolor-tla: #121212;
        --kolor-tekstu: #e0e0e0;
        --kolor-glowny: #9fa8da;
    }
}
```

Jeśli wszystkie kolory strony są zmiennymi, tryb ciemny to **tylko kilka linijek**.

!!! tip "Jak testować?"
    W narzędziach deweloperskich Chrome: ++ctrl+shift+p++, wpisz *dark* i wybierz **Emulate CSS prefers-color-scheme: dark**. W Firefoksie: ikona słońca/księżyca w zakładce *Inspektor*.

## Zadanie główne (25 min)

Pobierz i rozpakuj [motywy.zip](../pliki/lekcja-37/motywy.zip){ download }. Arkusz `styl.css` ma kolory wpisane bezpośrednio w regułach, niektóre wielokrotnie.

1. Znajdź w `styl.css` wszystkie różne kolory. Ile ich jest? Zapisz liczbę w komentarzu na początku pliku. Zauważ, że ten sam kolor bywa użyty w różnych rolach (np. `#212121` to tekst i tło przycisku po najechaniu), dlatego zmienne nazywamy według **roli**, a nie koloru.
2. Zdefiniuj w `:root` zmienne: `--tlo`, `--tlo-karty`, `--tekst`, `--tekst-slaby`, `--akcent`, `--akcent-ciemny`, `--tekst-na-akcencie`, `--ramka` z odpowiednimi wartościami. Kolor tła przycisku po najechaniu to `--akcent-ciemny` (w trybie jasnym `#212121`), a kolor napisu na przycisku to `--tekst-na-akcencie` (w trybie jasnym `#ffffff`).
3. Zastąp wszystkie kolory w regułach zmiennymi. W regułach nie może zostać żaden kolor zapisany bezpośrednio.
4. Zdefiniuj zmienną `--zaokraglenie: 8px` i użyj jej w kartach i przycisku.
5. Dodaj tryb ciemny (`prefers-color-scheme: dark`) zmieniający **tylko** wartości zmiennych: tło `#121212`, tło kart `#1e1e1e`, tekst `#e0e0e0`, tekst słaby `#9e9e9e`, akcent `#ffb74d`, akcent ciemny `#ffa726`, tekst na akcencie `#212121` (jasny napis na jasnopomarańczowym tle byłby nieczytelny), ramka `#333333`.
6. Sprawdź stronę w obu trybach.
7. Zmień kolor akcentu na `#e91e63` w jednym miejscu i zobacz, ile elementów zmieniło kolor.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do strony przełącznik motywu: klasa `ciemny` na `body` nadpisuje zmienne (`body.ciemny { --tlo: … }`). Klasę przełączaj jedną linijką JavaScript w atrybucie przycisku: `onclick="document.body.classList.toggle('ciemny')"`. JavaScript poznasz dokładnie w dziale 4.

## Czy potrafię…?

- [ ] zdefiniować zmienną CSS i jej użyć
- [ ] wyjaśnić, dlaczego zmienne ułatwiają zmianę kolorystyki
- [ ] napisać tryb ciemny z `prefers-color-scheme`
- [ ] przetestować tryb ciemny w przeglądarce
