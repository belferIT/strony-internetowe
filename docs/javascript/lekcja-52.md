# Lekcja 52. Zmiana wyglądu z JavaScript: style i klasy

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- zmieniać pojedyncze style elementu (`style`),
- dodawać, usuwać i przełączać klasy CSS (`classList`),
- pokazywać i ukrywać elementy,
- zbudować galerię ze zmianą dużego obrazu po kliknięciu miniatury.

## Wprowadzenie

=== "style: pojedyncza właściwość"

    ```js
    const box = document.getElementById("box");
    box.style.backgroundColor = "#ffcc80";   // background-color → backgroundColor
    box.style.fontSize = "20px";             // jednostka jest konieczna
    box.style.display = "none";              // ukrycie
    ```

=== "classList: cały zestaw stylów"

    ```css
    .aktywny { background: #1e88e5; color: white; border-radius: 6px; }
    .ukryty { display: none; }
    ```
    ```js
    box.classList.add("aktywny");
    box.classList.remove("aktywny");
    box.classList.toggle("ukryty");          // dodaj, jeśli nie ma; usuń, jeśli jest
    box.classList.contains("aktywny");       // true / false
    ```

!!! tip "Klasy zamiast stylów"
    Wygląd trzymaj w CSS, a w JavaScript tylko przełączaj klasy. Kod jest krótszy, a zmianę wyglądu robisz w jednym miejscu.

### Galeria: zmiana obrazu po kliknięciu

```js
function pokaz(plik) {
    document.getElementById("duzy").src = plik;
}
```
```html
<img src="foto1.jpg" class="miniatura" onclick="pokaz('foto1.jpg')">
```

## Zadanie główne (25 min)

Pobierz i rozpakuj [galeria.zip](../pliki/lekcja-52/galeria.zip){ download }. Strona, style i 4 obrazy są gotowe. Utwórz `skrypt.js` i dołącz go.

1. **Galeria.** Kliknięcie miniatury wyświetla ten obraz w dużym obrazie `#duzy`, a jego tekst alternatywny w podpisie `#podpis`. Kliknięta miniatura dostaje klasę `wybrana`; pozostałe ją tracą.
2. **Strzałki.** Przyciski `#poprzedni` i `#nastepny` przełączają obrazy po kolei (po ostatnim wraca do pierwszego).
3. **Tryb nocny.** Przycisk `#tryb` przełącza klasę `noc` na elemencie `body`. Napis na przycisku zmienia się: **Tryb nocny** ↔ **Tryb dzienny**.
4. **Opis.** Przycisk `#pokaz-opis` pokazuje i ukrywa akapit `#opis` (przełączanie klasy `ukryty`). Napis na przycisku: **Pokaż opis** ↔ **Ukryj opis**.
5. **Powiększenie.** Suwak `#rozmiar` (100–300) zmienia szerokość dużego obrazu w procentach jego bazowego rozmiaru 300px (np. 150 → 450px).

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Kliknięcie dużego obrazu otwiera go na pełnym ekranie na półprzezroczystym tle (*lightbox*). Kliknięcie tła lub klawisz ++esc++ zamyka podgląd.

## Czy potrafię…?

- [ ] zmienić pojedynczy styl elementu z JS
- [ ] przełączyć klasę elementu
- [ ] ukryć i pokazać element
- [ ] zmienić obraz po kliknięciu miniatury
