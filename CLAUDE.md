# Instrukcje dla Claude: materiały „Strony internetowe”

Repozytorium z materiałami dla uczniów klasy I technikum (technik programista / technik informatyk), przedmiot „Strony internetowe”: 64 h, lekcje po 45 min w pracowni. Przedmiot przygotowuje do kwalifikacji INF.03 (HTML, CSS, JavaScript po stronie klienta, grafika i multimedia, publikacja).

## Źródła
- `docs/rozklad.md`: rozkład materiału (numer lekcji, temat, efekty, zakres P / P+ / ★). Nowe lekcje twórz zgodnie z nim.
- Podstawa programowa 2019, INF.03.3 (efekty 1–8) i INF.03.5 efekt 3.

## Zasady tworzenia lekcji
- Szablon: `szablony/lekcja.md`. Plik: `docs/<dział>/lekcja-NR.md` (NR dwucyfrowy), pliki startowe: `docs/pliki/lekcja-NR/`.
- Po dodaniu lekcji dopisz ją do `nav` w `mkdocs.yml`.
- Struktura 45 min: wprowadzenie ok. 10 min, zadanie główne ok. 25 min, podsumowanie i „Czy potrafię…?” ok. 5 min.
- Zadanie główne musi być wykonalne przez przeciętnego ucznia klasy I w 25 min. Zadanie dla chętnych zawsze dodatkowe.
- Treści spoza podstawy oznaczaj `<span class="zakres zakres-gw">★ poza egzaminem</span>`.
- Zadania w stylu egzaminu INF.03: polecenia numerowane, konkretne wartości (kolory HEX, wymiary w px, nazwy plików), jak w arkuszach CKE.
- Kod: HTML5 i CSS3 zgodne z walidatorem W3C, JavaScript bez bibliotek (chyba że lekcja ★), `let`/`const`, `addEventListener`.
- Język: polski, zwracanie się do ucznia na „ty”, krótkie zdania.
- Składnia MkDocs Material: ramki `!!! info|tip|warning`, zwijane `??? question`, klawisze `++f12++`, zakładki `=== "HTML"`.

## Rozwiązania
Rozwiązań NIE umieszczaj w tym repozytorium (strona jest publiczna). Trafiają do osobnego, prywatnego repozytorium nauczyciela.
