# Lekcja 55. Walidacja formularza w JavaScript i HTML5

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- przechwycić wysłanie formularza i zatrzymać je, gdy dane są błędne,
- sprawdzić dane własnymi warunkami w JavaScript,
- wyświetlić komunikaty o błędach przy polach,
- połączyć walidację HTML5 z walidacją JavaScript.

## Wprowadzenie

```js
const form = document.getElementById("rejestracja");

form.addEventListener("submit", function (e) {
    const haslo = document.getElementById("haslo").value;
    const haslo2 = document.getElementById("haslo2").value;

    if (haslo !== haslo2) {
        e.preventDefault();                       // zatrzymaj wysłanie
        document.getElementById("blad-haslo2").textContent = "Hasła nie są takie same";
    }
});
```

| Narzędzie | Do czego |
|---|---|
| `e.preventDefault()` | zatrzymuje wysłanie formularza |
| `pole.value.trim()` | usuwa spacje z początku i końca |
| `tekst.length` | długość tekstu |
| `/wzorzec/.test(tekst)` | sprawdza wyrażenie regularne, np. `/[0-9]/.test(haslo)`: czy jest cyfra |
| `pole.checkValidity()` | czy pole spełnia warunki HTML5 |
| `pole.setCustomValidity("komunikat")` | własny komunikat przeglądarki (pusty tekst = poprawne) |

### Przydatne wyrażenia regularne

| Wzorzec | Sprawdza |
|---|---|
| `/[A-Z]/` | czy jest wielka litera |
| `/[a-z]/` | czy jest mała litera |
| `/[0-9]/` | czy jest cyfra |
| `/^[0-9]{2}-[0-9]{3}$/` | kod pocztowy `00-000` |
| `/^[0-9]{9}$/` | dokładnie 9 cyfr (np. telefon) |

!!! tip "Dobre komunikaty błędów"
    Komunikat mówi, **co** jest źle i **jak** to poprawić: „Hasło musi mieć co najmniej 8 znaków i jedną cyfrę”, a nie „Błąd!”.

## Zadanie główne (25 min)

Pobierz [walidacja.html](../pliki/lekcja-55/walidacja.html){ download }. Każde pole ma pod sobą pusty element `span` na komunikat błędu (klasa `blad`). Utwórz `skrypt.js`. Formularz ma atrybut `novalidate`, więc **całą** walidację wykonujesz w JavaScript.

Przy wysyłaniu formularza sprawdź:

1. **Login**: 4–15 znaków (po usunięciu spacji z brzegów).
2. **E-mail**: zawiera znak `@` i kropkę po nim (wystarczy proste sprawdzenie).
3. **Hasło**: co najmniej 8 znaków, co najmniej jedna wielka litera i jedna cyfra.
4. **Powtórz hasło**: takie samo jak hasło.
5. **Telefon**: dokładnie 9 cyfr; pole opcjonalne (puste jest poprawne).
6. **Regulamin**: zaznaczony.
7. Przy każdym błędnym polu wyświetl komunikat w jego `span.blad` i dodaj polu klasę `zle` (czerwona ramka jest w CSS). Przy poprawnym usuń komunikat i klasę.
8. Gdy wszystko jest poprawne, zatrzymaj wysłanie i zamiast formularza wyświetl **Konto zostało utworzone, LOGIN!** (z wpisanym loginem).

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Pod polem hasła pokaż na żywo (zdarzenie `input`) siłę hasła: pasek, który wypełnia się w 1/4 za każdy spełniony warunek (długość ≥ 8, wielka litera, cyfra, znak specjalny), z kolorem od czerwonego do zielonego.

## Czy potrafię…?

- [ ] zatrzymać wysłanie formularza
- [ ] sprawdzić długość tekstu i obecność cyfry
- [ ] wyświetlić komunikat błędu przy polu
- [ ] wyjaśnić, dlaczego walidację powtarza się na serwerze
