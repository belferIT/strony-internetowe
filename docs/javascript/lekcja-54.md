# Lekcja 54. Obiekty i tablice obiektów

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span> <span class="zakres zakres-gw">P+</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- opisać rzecz z kilkoma cechami jako obiekt,
- odczytywać i zmieniać właściwości obiektu,
- przechowywać dane w tablicy obiektów,
- generować z tablicy obiektów karty lub tabelę HTML.

## Wprowadzenie

```js
const film = {
    tytul: "Wielka podróż",
    rok: 2025,
    ocena: 7.8,
    gatunki: ["przygodowy", "familijny"]
};

console.log(film.tytul);          // odczyt właściwości
film.ocena = 8.1;                 // zmiana
film.rezyser = "A. Nowak";        // nowa właściwość
```

### Tablica obiektów

To najczęstszy sposób przechowywania danych w aplikacjach: lista produktów, uczniów, filmów.

```js
const filmy = [
    { tytul: "Wielka podróż", rok: 2025, ocena: 7.8 },
    { tytul: "Robot i przyjaciele", rok: 2024, ocena: 6.9 },
    { tytul: "Cicha noc", rok: 2026, ocena: 8.4 }
];

let html = "";
for (const f of filmy) {
    html += `<div class="karta"><h3>${f.tytul}</h3><p>${f.rok} · ★ ${f.ocena}</p></div>`;
}
document.getElementById("filmy").innerHTML = html;
```

| Operacja | Kod |
|---|---|
| filtrowanie | `filmy.filter(f => f.ocena >= 7)` |
| sortowanie po właściwości | `filmy.sort((a, b) => b.ocena - a.ocena)` |
| wyszukanie jednego | `filmy.find(f => f.tytul === "Cicha noc")` |

!!! info "JSON"
    Zapis obiektów i tablic w JavaScript to podstawa formatu **JSON**, w którym serwery przesyłają dane. Poznasz go w lekcji 59.

## Zadanie główne (25 min)

Pobierz [ksiazki.html](../pliki/lekcja-54/ksiazki.html){ download }. Skrypt na stronie zawiera już tablicę obiektów `ksiazki` (tytuł, autor, rok, liczba stron, dostępność). Dopisz kod w miejscu komentarza.

1. Napisz funkcję `pokaz(lista)`, która wypisuje książki z tablicy jako tabelę HTML w `#tabela`: kolumny **Tytuł**, **Autor**, **Rok**, **Strony**, **Dostępna** (**tak** / **nie**).
2. Wywołaj `pokaz(ksiazki)` po wczytaniu strony.
3. Przycisk **Tylko dostępne**: pokazuje tylko książki dostępne.
4. Przycisk **Sortuj wg roku**: pokazuje książki od najnowszej.
5. Przycisk **Wszystkie**: przywraca pełną listę.
6. Pod tabelą w `#podsumowanie` wypisz łączną liczbę stron wyświetlonych książek.
7. Formularz u góry: dodawanie nowej książki (tytuł, autor, rok, strony; nowa książka jest dostępna). Po dodaniu tabela się odświeża.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj pole wyszukiwania: przy każdym wpisanym znaku tabela pokazuje tylko książki, których tytuł lub autor zawiera wpisany tekst (bez względu na wielkość liter: `toLowerCase()`, `includes()`).

## Czy potrafię…?

- [ ] utworzyć obiekt z kilkoma właściwościami
- [ ] odczytać i zmienić właściwość obiektu
- [ ] wygenerować tabelę HTML z tablicy obiektów
- [ ] przefiltrować i posortować tablicę obiektów
