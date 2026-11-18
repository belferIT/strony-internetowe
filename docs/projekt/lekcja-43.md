# Lekcja 43. Publikacja strony: hosting, domena, FTP

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (8) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest hosting, domena i serwer DNS,
- dobrać rodzaj hostingu do potrzeb,
- połączyć się z serwerem przez FTP w programie FileZilla,
- opublikować stronę i sprawdzić ją po publikacji.

## Wprowadzenie

### Hosting i domena

| Pojęcie | Znaczenie |
|---|---|
| **hosting** | miejsce na serwerze, w którym leżą pliki strony, dostępne 24 h na dobę |
| **domena** | nazwa strony, np. `szprycha.pl`; kupuje się ją u rejestratora na określony czas (zwykle rok) |
| **DNS** | system zamieniający nazwę domeny na adres IP serwera; w panelu domeny wskazujesz, na jaki serwer ma prowadzić |
| **certyfikat SSL/TLS** | szyfrowanie połączenia (`https://`); wiele firm hostingowych daje go za darmo (Let's Encrypt) |

| Rodzaj hostingu | Dla kogo |
|---|---|
| darmowy (np. GitHub Pages, Netlify) | strony statyczne (HTML, CSS, JS), portfolio, dokumentacja |
| współdzielony | małe firmy, strony z PHP i bazą danych, WordPress |
| VPS / serwer dedykowany | duże serwisy, pełna kontrola nad serwerem |

!!! info "Pakiety serwerowe"
    Do testów na własnym komputerze używa się pakietów typu **XAMPP**: zawierają serwer WWW Apache, PHP i bazę MySQL/MariaDB. Na egzaminie INF.03 pracujesz właśnie na takim pakiecie, a pliki strony zapisujesz w folderze `htdocs`.

### FTP

**FTP** (*File Transfer Protocol*) służy do przesyłania plików na serwer. Bezpieczniejsze odmiany to **FTPS** i **SFTP** (szyfrowane). Do połączenia potrzebujesz:

| Dane | Przykład |
|---|---|
| serwer (host) | `ftp.example.com` |
| nazwa użytkownika | `uczen01` |
| hasło | podaje administrator |
| port | 21 (FTP/FTPS), 22 (SFTP) |

```text
FileZilla
+----------------------------+----------------------------+
| Witryna lokalna            | Witryna zdalna (serwer)    |
| (Twój komputer)            |                            |
|  lekcja-43/                |  public_html/              |
|   ├── index.html   ──────► |   ├── index.html           |
|   └── styl.css     ──────► |   └── styl.css             |
+----------------------------+----------------------------+
```

Pliki przeciągasz z lewej (komputer) na prawą stronę (serwer). Folder publiczny serwera nazywa się zwykle `public_html`, `www` lub `htdocs`.

!!! tip "Strona główna"
    Serwer po wejściu na adres domeny wyświetla plik `index.html` (lub `index.php`). Dlatego strona główna musi mieć dokładnie taką nazwę.

## Zadanie główne (25 min)

Dane do serwera FTP dostaniesz od nauczyciela.

1. Uruchom **FileZilla**. W polach na górze wpisz serwer, nazwę użytkownika, hasło i port. Kliknij *Szybkie łączenie*.
2. Odczytaj z okna komunikatów (u góry), jakim protokołem się połączyłeś/połączyłaś i czy połączenie jest szyfrowane.
3. Po lewej przejdź do folderu ze stroną kawiarni z lekcji 39–40. Po prawej otwórz folder publiczny.
4. Prześlij na serwer `index.html`, `styl.css` i folder z obrazami.
5. Otwórz stronę w przeglądarce pod adresem podanym przez nauczyciela. Sprawdź, czy wczytały się style i obrazy. Jeśli nie, znajdź przyczynę (wielkość liter w nazwach plików, ścieżki).
6. Zmień lokalnie kolor nagłówka w `styl.css`, prześlij poprawiony plik i odśwież stronę (++ctrl+f5++).
7. Zapisz w zeszycie: czym różni się hosting od domeny i co trzeba zrobić, żeby domena `mojastrona.pl` wyświetlała Twoją stronę.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Sprawdź w serwisie [whois](https://www.dns.pl/whois) właściciela domeny swojej szkoły i datę jej rejestracji. Następnie w terminalu wpisz `nslookup` i adres strony szkoły. Jaki adres IP ma serwer?

## Czy potrafię…?

- [ ] wyjaśnić, czym jest hosting, domena i DNS
- [ ] połączyć się z serwerem w FileZilla
- [ ] przesłać pliki strony do folderu publicznego
- [ ] sprawdzić stronę po publikacji i znaleźć przyczynę błędów
