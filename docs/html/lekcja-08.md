# Lekcja 8. Grafika rastrowa dla WWW w programie GIMP

<p class="lekcja-meta">Dział: HTML · 45 min · Efekty: INF.03.3 (4) · <span class="zakres zakres-p">INF.03</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- przeskalować obraz z zachowaniem proporcji,
- wykadrować obraz do zadanego rozmiaru,
- wyeksportować obraz do JPG, PNG i WebP z odpowiednią jakością,
- ocenić, jak jakość kompresji wpływa na rozmiar pliku.

## Wprowadzenie

Zdjęcie z aparatu ma zwykle kilka tysięcy pikseli szerokości i kilka megabajtów. Na stronie wyświetlisz je w szerokości np. 800 px, więc przesyłanie oryginału to strata czasu i transferu. Dlatego obrazy **przygotowuje się przed** wstawieniem na stronę.

| Czynność w GIMP | Menu | Skrót |
|---|---|---|
| zmiana rozmiaru obrazu | *Obraz → Skaluj obraz* | |
| kadrowanie | narzędzie *Kadrowanie* | ++shift+c++ |
| kadrowanie do proporcji | w opcjach narzędzia: *Stała → Proporcje*, np. `4:1` | |
| zmiana rozmiaru płótna | *Obraz → Rozmiar płótna* | |
| eksport do JPG/PNG/WebP | *Plik → Wyeksportuj jako* | ++ctrl+shift+e++ |

!!! info "Zapisz a Wyeksportuj"
    *Zapisz* tworzy plik `.xcf`, czyli format roboczy GIMP-a z warstwami. Na stronę potrzebujesz pliku JPG, PNG lub WebP, więc używasz **Wyeksportuj jako**.

!!! tip "Łańcuch przy wymiarach"
    W oknie *Skaluj obraz* ikona łańcucha obok szerokości i wysokości musi być **złączona**. Wtedy GIMP zachowa proporcje.

## Zadanie główne (25 min)

Pobierz zdjęcie [jezioro-duze.jpg](../pliki/lekcja-08/jezioro-duze.jpg){ download } (3000×1875 px). W folderze `lekcja-08` utwórz folder `obrazy`. Wszystkie pliki zapisuj w nim.

1. **Miniatura.** Przeskaluj zdjęcie z zachowaniem proporcji do szerokości **400 px**. Wyeksportuj jako `jezioro-mini.jpg`, jakość **80**. Cofnij zmiany (++ctrl+z++).
2. **Baner.** Wykadruj zdjęcie do proporcji **4:1**, tak aby zostały góry i woda. Następnie przeskaluj wynik do **1200×300 px**. Wyeksportuj jako `baner.jpg`, jakość **75**.
3. **Porównanie jakości.** Z obrazu z punktu 1 (400 px szerokości) wyeksportuj jeszcze dwa pliki: `jezioro-q95.jpg` (jakość 95) i `jezioro-q30.jpg` (jakość 30). Wyeksportuj go też jako `jezioro-mini.png` i `jezioro-mini.webp`.
4. W pliku `lekcja-08/rozmiary.txt` zapisz rozmiar każdego pliku w KB i swoją ocenę: przy której jakości widać już pogorszenie obrazu?
5. Utwórz `galeria.html`, która pokazuje baner i obok siebie miniatury `jezioro-q95.jpg` i `jezioro-q30.jpg` z podpisami (`figure`, `figcaption`) zawierającymi rozmiar pliku.

??? question "Jak sprawdzić rozmiar pliku?"
    W menedżerze plików kliknij plik prawym przyciskiem i wybierz *Właściwości*. Możesz też w VS Code najechać na plik w panelu bocznym.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Wstaw na stronę baner za pomocą znacznika `picture`: przeglądarka ma użyć wersji WebP, a jeśli jej nie obsługuje, wersji JPG.

```html
<picture>
    <source srcset="obrazy/baner.webp" type="image/webp">
    <img src="obrazy/baner.jpg" alt="Jezioro wśród gór" width="1200" height="300">
</picture>
```

## Czy potrafię…?

- [ ] przeskalować obraz do zadanej szerokości z zachowaniem proporcji
- [ ] wykadrować obraz do proporcji i rozmiaru z polecenia
- [ ] wyeksportować obraz do JPG z wybraną jakością
- [ ] wyjaśnić, kiedy wybrać JPG, a kiedy PNG
