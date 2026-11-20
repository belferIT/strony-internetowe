# Lekcja 44. Publikacja przez Git i GitHub Pages

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (8) · <span class="zakres zakres-gw">★ poza egzaminem</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, do czego służy system kontroli wersji Git,
- utworzyć repozytorium na GitHubie i przesłać do niego pliki,
- opublikować stronę w GitHub Pages,
- zaktualizować opublikowaną stronę.

## Wprowadzenie

**Git** zapisuje historię zmian w plikach. Każdy zapis to **commit** z opisem, co się zmieniło. W każdej chwili możesz wrócić do wcześniejszej wersji. **GitHub** przechowuje repozytoria Git w internecie, a usługa **GitHub Pages** udostępnia je jako stronę WWW za darmo.

| Pojęcie | Znaczenie |
|---|---|
| repozytorium (repo) | folder projektu z historią zmian |
| commit | zapisany stan plików z opisem |
| push | wysłanie commitów na GitHuba |
| gałąź `main` | główna linia projektu |

### Dwa sposoby pracy

=== "Przez przeglądarkę (najprościej)"

    1. Na GitHubie otwórz swoje repozytorium `strony-internetowe` (założone w lekcji 1).
    2. *Add file → Upload files*: przeciągnij **cały folder** `kawiarnia`, wpisz opis zmian, **Commit changes**.
    3. *Settings → Pages → Branch: main / (root) → Save*.
    4. Po 1–2 minutach strona działa pod adresem `https://login.github.io/strony-internetowe/kawiarnia/`.

=== "Przez terminal (jak profesjonaliści)"

    ```bash
    git clone https://github.com/login/strony-internetowe.git
    cd strony-internetowe
    # skopiuj tu folder kawiarnia
    git add .
    git commit -m "Pierwsza wersja strony"
    git push
    ```
    Kolejne zmiany:
    ```bash
    git add .
    git commit -m "Nowy kolor nagłówka"
    git push
    ```

!!! warning "Strona jest publiczna"
    Wszystko, co wyślesz do publicznego repozytorium, może zobaczyć każdy. Nie umieszczaj tam haseł, danych osobowych ani zdjęć innych osób bez ich zgody.

!!! tip "Jedno repozytorium na wszystkie prace"
    Każda praca z tego przedmiotu trafia do repozytorium `strony-internetowe`, w osobnym folderze. Folder `kawiarnia` daje adres `https://login.github.io/strony-internetowe/kawiarnia/`. Plik startowy w folderze musi się nazywać `index.html`.

## Zadanie główne (25 min)

Opublikuj stronę kawiarni z lekcji 39–40 w GitHub Pages.

1. Zaloguj się na konto GitHub, które założyłeś/założyłaś w lekcji 1.
2. Otwórz repozytorium `strony-internetowe` z lekcji 1.
3. Prześlij przez przeglądarkę folder `kawiarnia` z plikami strony. Opis commita: **Pierwsza wersja strony**.
4. Włącz GitHub Pages dla gałęzi `main`. Poczekaj na publikację (zakładka **Actions** pokazuje postęp).
5. Otwórz stronę pod adresem `https://login.github.io/strony-internetowe/kawiarnia/`. Sprawdź style i obrazy.
6. Edytuj na GitHubie plik `README.md` w głównym folderze repozytorium (ikona ołówka): dopisz opis strony kawiarni i link do niej. Zapisz commit.
7. Zmień w `kawiarnia/styl.css` dowolny kolor (edycja w przeglądarce lub ponowne wgranie pliku) i sprawdź, czy strona się zaktualizowała.
8. Wejdź w historię commitów (*Commits*). Ile ich jest? Kliknij jeden z nich: co pokazują zielone i czerwone wiersze?
9. Wyślij nauczycielowi link do swojej strony.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Zainstaluj Git na swoim komputerze i sklonuj repozytorium `strony-internetowe` (`git clone`). Wprowadź zmianę lokalnie w VS Code i wyślij ją poleceniami z zakładki „Przez terminal”. VS Code ma też wbudowany panel *Source Control* (++ctrl+shift+g++), który robi to samo przyciskami.

## Czy potrafię…?

- [ ] wyjaśnić, czym jest repozytorium, commit i push
- [ ] przesłać pliki strony do folderu w repozytorium
- [ ] włączyć GitHub Pages
- [ ] zaktualizować opublikowaną stronę
