# Lekcja 18. Selektory

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- stosować selektory znacznika, klasy i identyfikatora,
- grupować selektory,
- wybierać elementy według położenia w dokumencie (selektor potomka i dziecka).

## Wprowadzenie

| Selektor | Zapis | Wybiera |
|---|---|---|
| uniwersalny | `*` | wszystkie elementy |
| znacznika | `p` | wszystkie akapity |
| klasy | `.wazne` | elementy z `class="wazne"` (może być wiele na stronie) |
| identyfikatora | `#menu` | element z `id="menu"` (tylko jeden na stronie) |
| grupowanie | `h1, h2, h3` | wszystkie nagłówki 1., 2. i 3. stopnia |
| potomka | `nav a` | odnośniki **gdziekolwiek** wewnątrz `nav` |
| dziecka | `ul > li` | `li` będące **bezpośrednio** w `ul` |
| znacznik z klasą | `p.wazne` | tylko akapity z klasą `wazne` |

```html
<p class="wazne duze">Element może mieć kilka klas, oddzielonych spacją.</p>
```

!!! tip "Klasa czy identyfikator?"
    Klasa: styl, który chcesz użyć wiele razy. Identyfikator: jeden, wyjątkowy element (np. `#baner`, `#stopka`). Na egzaminie bloki układu strony często mają identyfikatory, a powtarzające się elementy klasy.

## Zadanie główne (25 min)

Pobierz [selektory.html](../pliki/lekcja-18/selektory.html){ download }. **Nie zmieniaj** pliku HTML. Utwórz `styl.css`, dołącz go i zapisz reguły:

1. Wszystkie elementy: czcionka `Verdana`.
2. Nagłówki `h1` i `h2` (jedną regułą): kolor `#0d47a1`.
3. Elementy z klasą `ostrzezenie`: kolor tekstu `#b71c1c`, pogrubienie (`font-weight: bold`).
4. Element z identyfikatorem `stopka`: kolor tła `#eeeeee`, kolor tekstu `#666666`.
5. Odnośniki wewnątrz `nav`: kolor `#2e7d32`. Odnośnik w treści strony ma zostać niezmieniony.
6. Elementy `li` będące bezpośrednio w liście `#lista-glowna` (nie w liście zagnieżdżonej): kolor `#e65100`.
7. Akapity z klasą `info` (ale nie inne elementy z tą klasą): tło `#e3f2fd`.

Po każdej regule sprawdź w przeglądarce, czy zmieniły się **tylko** właściwe elementy.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź, co wybierają selektory `h2 + p` i `h2 ~ p`. Dopisz do pliku reguły, które pokażą różnicę (np. różne kolory tła).

## Czy potrafię…?

- [ ] zapisać selektor klasy i identyfikatora
- [ ] zgrupować kilka selektorów w jednej regule
- [ ] wyjaśnić różnicę między `nav a` a `nav > a`
