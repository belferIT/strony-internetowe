# Lekcja 41. Walidacja i testowanie strony

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (7) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest walidacja kodu i dlaczego się ją wykonuje,
- odczytać komunikaty walidatorów HTML i CSS i naprawić błędy,
- przetestować stronę w różnych przeglądarkach i rozdzielczościach,
- znaleźć brakujące pliki w zakładce **Console** i **Network**.

## Wprowadzenie

**Walidacja** to sprawdzenie, czy kod jest zgodny ze standardem. Przeglądarki „wybaczają” błędy, ale każda może je naprawić inaczej. Strona z błędami może więc wyglądać różnie w Chrome, Firefoksie i Safari.

| Narzędzie | Adres |
|---|---|
| Walidator HTML | [validator.w3.org](https://validator.w3.org/#validate_by_input) |
| Walidator CSS | [jigsaw.w3.org/css-validator](https://jigsaw.w3.org/css-validator/#validate_by_input) |
| Konsola przeglądarki | ++f12++ → **Console**: błędy JavaScript i brakujące pliki |
| Tryb urządzeń | ++ctrl+shift+m++: różne rozdzielczości ekranu |

| Rodzaj komunikatu | Znaczenie |
|---|---|
| **Error** | błąd, trzeba poprawić |
| **Warning** | ostrzeżenie: kod działa, ale coś jest nie tak (np. przestarzały zapis) |
| **Info** | informacja |

!!! tip "Naprawiaj od góry"
    Jeden błąd (np. niezamknięty znacznik) potrafi wywołać kilka kolejnych komunikatów. Popraw pierwszy, sprawdź ponownie, potem następny.

!!! warning "Wielkość liter w nazwach plików"
    W Windows `Styl.css` i `styl.css` to ten sam plik. Na serwerze z Linuksem to **dwa różne pliki**. Strona działa na Twoim komputerze, a po publikacji traci style. Dlatego nazwy plików zapisuj zawsze małymi literami.

### Lista kontrolna testów

- [ ] HTML bez błędów w walidatorze
- [ ] CSS bez błędów w walidatorze
- [ ] brak błędów w konsoli przeglądarki
- [ ] działają wszystkie odnośniki i wczytują się wszystkie obrazy
- [ ] strona wygląda dobrze w Chrome i Firefoksie
- [ ] strona działa przy szerokości 375px, 768px i 1280px
- [ ] strona działa przy powiększeniu 200%

## Zadanie główne (25 min)

Pobierz i rozpakuj [testy.zip](../pliki/lekcja-41/testy.zip){ download }. Strona warsztatu ma kilkanaście błędów w HTML i CSS.

1. Sprawdź `index.html` w walidatorze HTML. Popraw wszystkie błędy i ostrzeżenia. Zapisz w pliku `raport.txt`, ile ich było i jakie.
2. Sprawdź `styl.css` w walidatorze CSS. Popraw błędy i dopisz je do raportu.
3. Otwórz stronę w przeglądarce. Czy style się wczytują? Znajdź przyczynę w zakładce **Network** lub **Console** i popraw ją tak, jak powinno się to robić na serwerze z Linuksem.
4. W konsoli znajdź komunikat o brakującym obrazie. Utwórz folder `obrazy` i zapisz w nim dowolny obraz roweru na wolnej licencji (np. z [Pixabay](https://pixabay.com/pl/)) pod właściwą nazwą. Dodaj tekst alternatywny.
5. Przetestuj stronę w trybie urządzeń przy szerokości 375px. Napraw problem z przewijaniem w poziomie.
6. Sprawdź stronę w drugiej przeglądarce. Zapisz w raporcie, czy są różnice.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zainstaluj w VS Code rozszerzenie **HTMLHint** lub **W3C Web Validator**. Dzięki niemu błędy są podkreślane już w edytorze, bez wklejania kodu do walidatora.

## Czy potrafię…?

- [ ] sprawdzić HTML i CSS w walidatorach W3C
- [ ] odczytać komunikat walidatora i znaleźć błędny wiersz
- [ ] znaleźć brakujący plik w narzędziach deweloperskich
- [ ] przeprowadzić test strony w różnych rozdzielczościach
