# Lekcja 49. DOM: odczyt i zmiana elementów strony

<p class="lekcja-meta">Dział: JavaScript · 45 min · Efekty: INF.03.5 (3) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest DOM,
- wybrać element strony po identyfikatorze, klasie lub selektorze CSS,
- zmienić treść, atrybuty i styl elementu,
- dodać i usunąć element strony.

## Wprowadzenie

**DOM** (*Document Object Model*) to drzewo obiektów, które przeglądarka buduje z kodu HTML. JavaScript zmienia stronę, zmieniając to drzewo.

```text
document
└── html
    ├── head
    │   └── title
    └── body
        ├── h1#tytul
        └── ul
            ├── li.produkt
            └── li.produkt
```

### Wybieranie elementów

| Metoda | Zwraca |
|---|---|
| `document.getElementById("tytul")` | element o danym `id` |
| `document.querySelector(".produkt")` | **pierwszy** element pasujący do selektora CSS |
| `document.querySelectorAll(".produkt")` | **wszystkie** pasujące elementy (lista) |
| `document.getElementsByClassName("produkt")` | wszystkie elementy z klasą |
| `document.getElementsByTagName("li")` | wszystkie elementy danego znacznika |

### Zmiana elementów

```js
const tytul = document.getElementById("tytul");
tytul.innerHTML = "Nowy <em>tytuł</em>";   // treść z interpretacją znaczników
tytul.textContent = "Zwykły tekst";         // tylko tekst
tytul.style.color = "red";                  // styl (nazwy jak w CSS, ale camelCase: backgroundColor)

const obraz = document.querySelector("img");
obraz.src = "nowy.jpg";                     // atrybut
obraz.alt = "Opis";

// nowy element
const li = document.createElement("li");
li.textContent = "Nowy produkt";
document.querySelector("ul").appendChild(li);

// usunięcie elementu
document.querySelector(".stary").remove();
```

!!! tip "Gdzie dołączyć skrypt?"
    Skrypt na końcu `body` widzi wszystkie elementy strony. Skrypt w `head` uruchomi się, zanim elementy powstaną, i `getElementById` zwróci `null`. Jeśli musisz dać go w `head`, dodaj atrybut `defer`: `<script src="skrypt.js" defer></script>`.

## Zadanie główne (25 min)

Pobierz [dom.html](../pliki/lekcja-49/dom.html){ download }. Utwórz `skrypt.js`. **Nie zmieniaj HTML** (poza dołączeniem skryptu). Wszystkie zmiany wykonaj w JavaScript.

1. Zmień treść nagłówka `#tytul` na **Sklep z owocami – promocja!**.
2. Ustaw kolor tła nagłówka na `#fff59d`.
3. Zmień obraz: atrybut `src` na `https://placehold.co/300x200?text=Owoce` i `alt` na **Kosz z owocami**.
4. Wszystkim elementom z klasą `cena` ustaw kolor `#c62828` i pogrubienie (pętla po `querySelectorAll`).
5. Dodaj na końcu listy `#owoce` nowy element `li` z tekstem **Mango – 8 zł** (z ceną w znaczniku `span` z klasą `cena`).
6. Usuń z listy element z klasą `wyprzedane`.
7. Policz elementy listy i wpisz ich liczbę do akapitu `#liczba`: **Liczba produktów: 5**.
8. W akapicie `#info` sprawdź różnicę: wpisz tekst `<strong>Uwaga!</strong>` raz przez `innerHTML`, raz przez `textContent`. Zostaw wersję z `innerHTML`.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wpisz w konsoli `document.body.children` i `document.querySelector("li").parentElement`. Przejdź po drzewie DOM od pierwszego `li` do `body`, używając tylko właściwości `parentElement`.

## Czy potrafię…?

- [ ] wyjaśnić, czym jest DOM
- [ ] wybrać element po `id` i po selektorze CSS
- [ ] zmienić treść, atrybut i styl elementu
- [ ] utworzyć i dodać nowy element do strony
