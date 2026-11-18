# Lekcja 12. Formularze, część 2: pola wyboru i walidacja HTML5

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1), INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wstawić przyciski opcji, pola wyboru, listę rozwijaną i pole wielowierszowe,
- grupować pola (`fieldset`, `legend`),
- sprawdzać poprawność danych bez programowania (walidacja HTML5).

## Wprowadzenie

=== "Radio i checkbox"

    ```html
    <!-- radio: jedna odpowiedź z grupy (ta sama nazwa!) -->
    <label><input type="radio" name="plec" value="k"> kobieta</label>
    <label><input type="radio" name="plec" value="m"> mężczyzna</label>

    <!-- checkbox: dowolna liczba zaznaczeń -->
    <label><input type="checkbox" name="zgoda" value="tak" checked> Akceptuję regulamin</label>
    ```

=== "Lista rozwijana"

    ```html
    <select name="klasa">
        <option value="">-- wybierz --</option>
        <optgroup label="Technik programista">
            <option value="1tp">1TP</option>
            <option value="2tp" selected>2TP</option>
        </optgroup>
    </select>
    ```

=== "Pole wielowierszowe"

    ```html
    <textarea name="uwagi" rows="4" cols="40" placeholder="Twoje uwagi"></textarea>
    ```

=== "Grupowanie"

    ```html
    <fieldset>
        <legend>Dane kontaktowe</legend>
        ...pola...
    </fieldset>
    ```

!!! warning "Przyciski radio"
    Przyciski z jednej grupy muszą mieć **taką samą** wartość `name`. Inaczej da się zaznaczyć wszystkie naraz. Każdy przycisk musi mieć inną wartość `value`, bo to ona trafia na serwer.

### Walidacja HTML5

| Atrybut | Działanie |
|---|---|
| `required` | pole wymagane |
| `min`, `max`, `step` | zakres i krok dla liczb i dat |
| `minlength`, `maxlength` | długość tekstu |
| `pattern` | wyrażenie regularne, np. `pattern="[0-9]{2}-[0-9]{3}"` (kod pocztowy) |
| `title` | komunikat podpowiedzi przy błędnym wzorcu |
| `novalidate` (w `form`) | wyłącza walidację |

Przeglądarka nie wyśle formularza, dopóki dane nie spełnią warunków.

!!! info "Walidacja w przeglądarce to nie wszystko"
    Walidację HTML łatwo obejść (np. w narzędziach deweloperskich). Serwer i tak musi sprawdzić dane drugi raz.

## Zadanie główne (25 min)

Utwórz stronę `ankieta.html` (tytuł karty: **Ankieta**) z formularzem wysyłanym metodą `post` do pliku `ankieta.php`.

1. Grupa **Dane ucznia** (`fieldset` z `legend`):
    1. imię: wymagane, od 2 do 30 znaków,
    2. wiek: liczba od 14 do 20, wymagana,
    3. klasa: lista rozwijana z grupami `Technik programista` (1TP, 2TP) i `Technik informatyk` (1TI, 2TI),
    4. kod pocztowy: wzorzec `00-000` z podpowiedzią w `title`.
2. Grupa **Twoje zainteresowania**:
    1. ulubiony przedmiot zawodowy: trzy przyciski radio (Strony internetowe, Bazy danych, Systemy operacyjne); pierwszy zaznaczony domyślnie,
    2. czym się interesujesz: cztery pola wyboru (gry, sport, muzyka, programowanie),
    3. ocena lekcji: suwak od 1 do 10.
3. Pole wielowierszowe **Twoje uwagi**: 5 wierszy, 50 kolumn, maksymalnie 300 znaków.
4. Wymagany checkbox **Wyrażam zgodę na przetwarzanie odpowiedzi**.
5. Przycisk **Wyślij ankietę**.
6. Sprawdź walidację: spróbuj wysłać pusty formularz, wpisz wiek 25 i kod pocztowy `7210`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj pole **Miasto** z podpowiedziami z listy `datalist` (Goleniów, Szczecin, Nowogard, Stargard). Czym `datalist` różni się od `select`?

## Czy potrafię…?

- [ ] utworzyć grupę przycisków radio
- [ ] zbudować listę rozwijaną z grupami opcji
- [ ] ustawić pole jako wymagane i ograniczyć zakres liczby
- [ ] użyć atrybutu `pattern`
