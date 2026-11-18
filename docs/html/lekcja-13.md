# Lekcja 13. Semantyka HTML5

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (1), (6) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym są znaczniki semantyczne i po co się ich używa,
- dobrać znacznik do roli fragmentu strony,
- przebudować stronę zbudowaną z bloków `div` na semantyczną.

## Wprowadzenie

Znacznik `div` nic nie mówi o swojej zawartości. Znaczniki **semantyczne** mówią, czym jest dany fragment. Korzystają z tego wyszukiwarki, czytniki ekranu i inni programiści.

```text
+-------------------------------------------+
| <header>  logo, tytuł                     |
|   <nav>   menu                            |
+------------------------------+------------+
| <main>                       | <aside>    |
|   <article>                  | dodatki,   |
|     <section> ...            | reklamy    |
|   </article>                 |            |
+------------------------------+------------+
| <footer>  stopka                          |
+-------------------------------------------+
```

| Znacznik | Zawartość |
|---|---|
| `header` | nagłówek strony lub artykułu: logo, tytuł |
| `nav` | główna nawigacja |
| `main` | główna treść strony (**jeden** na stronie) |
| `article` | samodzielna treść: wpis na blogu, wiadomość, komentarz |
| `section` | tematyczna część treści, zwykle z nagłówkiem |
| `aside` | treść poboczna: ramka, reklama, lista linków |
| `footer` | stopka: autor, prawa autorskie, kontakt |
| `figure`, `figcaption` | ilustracja z podpisem |
| `time` | data lub godzina: `<time datetime="2026-11-18">18 listopada</time>` |
| `address` | dane kontaktowe autora |

!!! tip "Kiedy jednak `div`?"
    Gdy blok jest potrzebny **tylko do stylowania** (np. kontener do wyśrodkowania) i nie ma znaczenia dla treści.

!!! info "Na egzaminie"
    Polecenia INF.03 często mówią wprost: „blok banera zbudowany znacznikiem `header`”, „panel lewy: `section`”. Zawsze używaj znacznika podanego w poleceniu.

## Zadanie główne (25 min)

Pobierz [divy.html](../pliki/lekcja-13/divy.html){ download }. Strona jest zbudowana tylko z bloków `div` z klasami. Zapisz ją jako `semantyczna.html` i przebuduj:

1. Zamień każdy `div` na odpowiedni znacznik semantyczny. Klasy mówią, co jest w bloku. Zostaw klasy, żeby nie zepsuć stylów.
2. Każdy z dwóch wpisów bloga ma być osobnym artykułem z własnym nagłówkiem i stopką (autor, data).
3. Daty zapisz w znaczniku `time` z atrybutem `datetime` w formacie RRRR-MM-DD.
4. Zdjęcie z podpisem zapisz w `figure` i `figcaption`.
5. Dane kontaktowe w stopce strony zapisz w `address`.
6. Jeden `div` powinien zostać, bo służy tylko do stylowania. Znajdź go i uzasadnij w komentarzu HTML.
7. Sprawdź stronę w walidatorze W3C. Otwórz zakładkę **Outline** w walidatorze (opcja *Show outline*) i porównaj strukturę nagłówków.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zainstaluj w przeglądarce rozszerzenie pokazujące strukturę strony (np. *HeadingsMap*). Porównaj strukturę swojej strony ze stroną dużego portalu informacyjnego.

## Czy potrafię…?

- [ ] wymienić 6 znaczników semantycznych i ich zastosowanie
- [ ] wyjaśnić różnicę między `article` a `section`
- [ ] wyjaśnić, komu pomaga semantyka
- [ ] zapisać datę w znaczniku `time`
