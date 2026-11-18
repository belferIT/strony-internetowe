# Lekcja 36. Przejścia, transformacje i animacje

<p class="lekcja-meta">Dział: CSS · 45 min · Efekty: INF.03.3 (2) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- płynnie zmieniać wygląd elementu (`transition`),
- przesuwać, obracać i skalować elementy (`transform`),
- tworzyć animacje z klatek kluczowych (`@keyframes`).

## Wprowadzenie

### Przejścia

Bez przejścia zmiana po `:hover` jest natychmiastowa. Z przejściem trwa określony czas:

```css
.przycisk {
    background: #1e88e5;
    transition: background 0.3s ease, transform 0.3s;
}
.przycisk:hover {
    background: #0d47a1;
    transform: scale(1.1);
}
```

### Transformacje

| Funkcja | Działanie |
|---|---|
| `translate(20px, 10px)` | przesunięcie |
| `rotate(45deg)` | obrót |
| `scale(1.5)` | powiększenie (1 = bez zmian) |
| `skew(10deg)` | pochylenie |

Kilka transformacji zapisujesz po spacji: `transform: rotate(10deg) scale(1.2);`

### Animacje

```css
@keyframes pulsowanie {
    0%   { transform: scale(1); }
    50%  { transform: scale(1.2); }
    100% { transform: scale(1); }
}
.serce {
    animation: pulsowanie 1s ease-in-out infinite;
    /* nazwa, czas, tempo, liczba powtórzeń */
}
```

| Właściwość | Przykład |
|---|---|
| `animation-duration` | `2s` |
| `animation-timing-function` | `linear`, `ease`, `ease-in-out` |
| `animation-iteration-count` | `3`, `infinite` |
| `animation-direction` | `alternate` (tam i z powrotem) |
| `animation-delay` | `0.5s` |

!!! warning "Szacunek dla użytkownika"
    Niektóre osoby źle znoszą ruch na ekranie. Przeglądarka informuje o tym ustawieniem systemu, które sprawdzisz w CSS:
    ```css
    @media (prefers-reduced-motion: reduce) {
        * { animation: none !important; transition: none !important; }
    }
    ```

## Zadanie główne (25 min)

Pobierz [animacje.html](../pliki/lekcja-36/animacje.html){ download }. Utwórz `styl.css` i dołącz go.

1. `.przycisk`: po najechaniu kursorem płynnie (0.3s) zmienia tło na `#e65100` i unosi się o 3px w górę (`translateY(-3px)`); dodaj cień, który też pojawia się płynnie.
2. `.karta`: po najechaniu obraca się o 3 stopnie i powiększa o 5%, w czasie 0.4s.
3. `.ikona`: po najechaniu wykonuje pełny obrót (360°) w czasie 1s.
4. `.serce`: pulsuje bez przerwy jak w przykładzie we wprowadzeniu.
5. `.ladowanie`: kółko z obramowaniem 6px `#e0e0e0`, górna krawędź w kolorze `#1e88e5`, zaokrąglenie 50%, rozmiar 50×50px; obraca się bez końca ruchem jednostajnym (`linear`) w czasie 1s.
6. `.wjazd`: po załadowaniu strony wjeżdża z lewej strony (z `translateX(-100%)` i przezroczystości 0) w czasie 1s, jednorazowo.
7. Dodaj regułę `prefers-reduced-motion` z ramki we wprowadzeniu.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zrób animowany pasek postępu: blok o szerokości 0, który w czasie 3s wypełnia się do 100% szerokości rodzica, zmieniając kolor z czerwonego na zielony. Użyj `animation-fill-mode: forwards`, żeby pasek nie wracał do początku.

## Czy potrafię…?

- [ ] dodać płynne przejście do efektu `:hover`
- [ ] obrócić i powiększyć element
- [ ] napisać animację z `@keyframes`
- [ ] wyłączyć animacje dla osób, które sobie tego nie życzą
