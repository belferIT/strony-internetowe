# Lekcja 15. Dostępność stron (WCAG)

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (6), (7) · <span class="zakres zakres-p">INF.03</span> <span class="zakres zakres-gw">P+</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest dostępność cyfrowa i komu służy,
- znaleźć na stronie typowe błędy dostępności,
- poprawić je w kodzie HTML,
- sprawdzić stronę automatycznym narzędziem.

## Wprowadzenie

Ze stron korzystają też osoby niewidome (czytnik ekranu), słabowidzące (powiększenie, wysoki kontrast), niesłyszące (napisy), z niepełnosprawnością ruchową (tylko klawiatura). **WCAG** (*Web Content Accessibility Guidelines*) to międzynarodowe wytyczne dostępności. W Polsce strony instytucji publicznych, w tym szkół, muszą je spełniać z mocy ustawy.

| Zasada | Jak spełnić w HTML |
|---|---|
| Obraz ma tekst alternatywny | `alt` opisujący treść; obraz ozdobny: `alt=""` |
| Język strony jest określony | `<html lang="pl">` |
| Hierarchia nagłówków jest logiczna | `h1` → `h2` → `h3`, bez przeskakiwania poziomów |
| Pola formularza mają etykiety | `label for` |
| Odnośnik mówi, dokąd prowadzi | „Regulamin konkursu” zamiast „kliknij tutaj” |
| Tekst ma wystarczający kontrast | min. 4,5 : 1 dla zwykłego tekstu |
| Wszystko działa z klawiatury | przyciski to `button`, odnośniki to `a`, nie `div` z kliknięciem |
| Tabela danych ma nagłówki | `th`, `caption` |
| Film ma napisy | element `track` |

!!! tip "Testy, które zrobisz w minutę"
    1. Odłóż mysz i przejdź stronę klawiszem ++tab++. Czy widzisz, gdzie jesteś? Czy dojdziesz do każdego odnośnika?
    2. Powiększ stronę do 200% (++ctrl+plus++). Czy da się ją czytać?
    3. Wyłącz obrazy albo popatrz na same teksty alternatywne. Czy wiesz, co było na obrazach?

## Zadanie główne (25 min)

Pobierz [niedostepna.html](../pliki/lekcja-15/niedostepna.html){ download }. Strona ma **co najmniej 10 błędów dostępności**.

1. Zrób trzy testy z ramki powyżej. Zapisz, co zauważyłeś/zauważyłaś.
2. Sprawdź stronę w Chrome: narzędzia deweloperskie (++f12++) → zakładka **Lighthouse** → zaznacz tylko *Accessibility* → *Analyze page load*. Możesz też użyć rozszerzenia [WAVE](https://wave.webaim.org/extension/).
3. Zapisz w pliku `lekcja-15/bledy.txt` listę znalezionych błędów (min. 10) w formacie: *element – błąd – jak naprawić*.
4. Popraw wszystkie błędy w pliku i zapisz go jako `dostepna.html`.
5. Uruchom ponownie Lighthouse. Zapisz wynik *Accessibility* przed poprawkami i po nich.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Włącz czytnik ekranu (Windows: Narrator, ++ctrl+win+enter++; Linux: Orca) i posłuchaj, jak czyta Twoją poprawioną stronę. Co jest najbardziej uciążliwe?

## Czy potrafię…?

- [ ] wyjaśnić, czym jest WCAG
- [ ] napisać dobry tekst alternatywny i wiedzieć, kiedy `alt` jest pusty
- [ ] sprawdzić stronę klawiaturą
- [ ] zbadać dostępność strony w Lighthouse
