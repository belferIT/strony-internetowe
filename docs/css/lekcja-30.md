# Lekcja 30. Pozycjonowanie elementów

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- przesunąć element względem jego miejsca (`relative`),
- umieścić element w dowolnym miejscu bloku nadrzędnego (`absolute`),
- przypiąć element do okna przeglądarki (`fixed`) i do krawędzi przy przewijaniu (`sticky`),
- ustalić, który element jest na wierzchu (`z-index`).

## Wprowadzenie

| `position` | Względem czego | Czy zostawia swoje miejsce? |
|---|---|---|
| `static` | domyślne, zwykły układ | tak |
| `relative` | swojego zwykłego położenia | tak |
| `absolute` | najbliższego przodka z `position` innym niż `static` | **nie** |
| `fixed` | okna przeglądarki, nie przewija się | **nie** |
| `sticky` | zwykły układ, ale „przykleja się” przy przewijaniu | tak |

Położenie ustawiasz właściwościami `top`, `right`, `bottom`, `left`.

```css
.karta { position: relative; }          /* punkt odniesienia dla dziecka */
.znaczek {
    position: absolute;
    top: 10px;
    right: 10px;                         /* prawy górny róg karty */
}
#do-gory {
    position: fixed;
    bottom: 20px;
    right: 20px;                         /* zawsze w prawym dolnym rogu ekranu */
}
header {
    position: sticky;
    top: 0;                              /* przykleja się do góry ekranu */
    z-index: 10;                         /* nad innymi elementami */
}
```

!!! tip "Para relative + absolute"
    Chcesz umieścić coś w rogu bloku? Rodzic dostaje `position: relative`, dziecko `position: absolute`. Bez tego dziecko ustawi się względem całej strony.

## Zadanie główne (25 min)

Pobierz [pozycje.html](../pliki/lekcja-30/pozycje.html){ download }. Utwórz `styl.css` i dołącz go.

1. `header`: tło `#1565c0`, biały tekst, margines wewnętrzny 15px; przyklejony do górnej krawędzi przy przewijaniu; zawsze na wierzchu (`z-index: 100`).
2. `.karta`: szerokość 250px, wysokość 150px, tło `#e3f2fd`, margines 20px, margines wewnętrzny 15px, punkt odniesienia dla elementów wewnątrz.
3. `.znaczek`: tło `#d32f2f`, biały tekst, margines wewnętrzny 4px 8px, zaokrąglenie 12px, w **prawym górnym rogu** karty (5px od krawędzi).
4. `.cena`: w **lewym dolnym rogu** karty (10px od krawędzi), pogrubiona, rozmiar 20px.
5. `#przesuniety`: przesunięty o 30px w prawo i 10px w dół względem swojego miejsca. Zauważ, że tekst poniżej się nie przesunął.
6. `#do-gory`: odnośnik zawsze w prawym dolnym rogu ekranu (20px od krawędzi), tło `#ff9800`, kolor tekstu biały, margines wewnętrzny 10px 14px, zaokrąglenie 50%, bez podkreślenia.
7. Przewiń stronę i sprawdź działanie elementów z punktów 1 i 6.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wyśrodkuj blok `#okno` w pionie i w poziomie na środku ekranu: `position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);`. Dodaj pod nim półprzezroczyste tło na cały ekran (`inset: 0`). Tak powstają okna dialogowe (*modal*).

## Czy potrafię…?

- [ ] wyjaśnić różnicę między `relative` a `absolute`
- [ ] umieścić element w rogu bloku
- [ ] przypiąć element do ekranu
- [ ] zrobić menu przyklejone przy przewijaniu
