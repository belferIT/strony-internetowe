# Lekcja 2. Jak działa WWW

<p class="lekcja-meta">Dział: Start · 45 min · Efekty: INF.03.3 (1) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- opisać, co się dzieje po wpisaniu adresu w przeglądarce,
- rozłożyć adres URL na części,
- odczytać w narzędziach deweloperskich, jakie pliki pobrała strona,
- przygotować VS Code do pracy.

## Wprowadzenie

### Klient i serwer

```text
 PRZEGLĄDARKA (klient)                     SERWER
        |  1. żądanie: GET /kontakt.html  -->  |
        |  <-- 2. odpowiedź: 200 OK + HTML     |
        |  3. żądania: style.css, logo.png --> |
        |  <-- 4. odpowiedzi: pliki            |
```

1. Wpisujesz adres, np. `https://www.example.com/kontakt.html`.
2. Serwer **DNS** zamienia nazwę `www.example.com` na adres IP serwera.
3. Przeglądarka (**klient**) wysyła do serwera **żądanie HTTP**: „daj mi plik `kontakt.html`”.
4. **Serwer** odsyła **odpowiedź** z kodem statusu i treścią pliku.
5. Przeglądarka czyta HTML i pobiera kolejne pliki: style CSS, skrypty JS, obrazy.
6. Przeglądarka składa z tego stronę i wyświetla ją.

### Budowa adresu URL

`https://www.example.com:443/sklep/produkty.html?kategoria=buty#opinie`

| Część | Przykład | Znaczenie |
|---|---|---|
| protokół | `https` | sposób komunikacji (HTTPS = HTTP szyfrowany) |
| host (domena) | `www.example.com` | nazwa serwera |
| port | `443` | „drzwi” serwera; zwykle pomijany |
| ścieżka | `/sklep/produkty.html` | folder i plik na serwerze |
| parametry | `?kategoria=buty` | dane przekazywane do serwera |
| kotwica | `#opinie` | miejsce na stronie |

### Najważniejsze kody odpowiedzi HTTP

| Kod | Znaczenie |
|---|---|
| 200 | OK, plik wysłany |
| 301 | adres przeniesiony na stałe |
| 404 | nie znaleziono pliku |
| 500 | błąd serwera |

## Zadanie główne (25 min)

Odpowiedzi zapisuj w pliku `lekcja-02/odpowiedzi.txt`.

**Część A. Adresy URL (7 min)**

Rozłóż na części (protokół, host, ścieżka, parametry, kotwica) dwa adresy:

1. `https://pl.wikipedia.org/wiki/HTML#Historia`
2. `https://www.google.com/search?q=html+tabela`

**Część B. Narzędzia deweloperskie (13 min)**

1. Otwórz w przeglądarce stronę swojej szkoły.
2. Naciśnij ++f12++ i przejdź do zakładki **Network** (Sieć). Odśwież stronę (++f5++).
3. Odczytaj i zapisz:
    1. ile żądań (requests) wykonała przeglądarka,
    2. ile danych zostało przesłanych (transferred),
    3. jaki kod statusu ma pierwszy plik na liście,
    4. jakie typy plików pobrała przeglądarka (kolumna *Type*); podaj co najmniej trzy.
4. Wpisz w pasku adresu nieistniejący adres w domenie szkoły, np. `/abcxyz.html`. Jaki kod statusu widzisz?

**Część C. VS Code (5 min)**

1. Uruchom Visual Studio Code.
2. Otwórz swój folder roboczy: *File → Open Folder*.
3. Zainstaluj rozszerzenie **Live Server** (ikona klocków po lewej). Dzięki niemu strona odświeży się w przeglądarce sama po każdym zapisie pliku.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

W zakładce **Network** kliknij pierwszy plik i otwórz **Headers** (Nagłówki). Znajdź nagłówki `server` i `content-type`. Co oznaczają? Dlaczego niektóre strony ukrywają wartość nagłówka `server`?

## Czy potrafię…?

- [ ] opisać w 4–6 krokach, co się dzieje po wpisaniu adresu strony
- [ ] wskazać w adresie URL protokół, domenę i ścieżkę
- [ ] wyjaśnić, co oznacza kod 404
- [ ] otworzyć zakładkę Network w narzędziach deweloperskich
