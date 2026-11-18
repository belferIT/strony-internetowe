# Lekcja 42. Optymalizacja i SEO

<p class="lekcja-meta">Dział: Projekt i publikacja · 45 min · Efekty: INF.03.3 (7) · <span class="zakres zakres-p">INF.03</span> <span class="zakres zakres-gw">★ Lighthouse</span></p>

## Cel lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest SEO i jak wyszukiwarka „czyta” stronę,
- uzupełnić znaczniki `title` i `meta`,
- zoptymalizować obrazy i kod pod kątem szybkości wczytywania,
- przeprowadzić audyt strony w Lighthouse.

## Wprowadzenie

**SEO** (*Search Engine Optimization*) to działania, dzięki którym strona jest wyżej w wynikach wyszukiwania. Robot wyszukiwarki nie widzi kolorów ani układu: czyta **kod HTML**.

### Co czyta wyszukiwarka

| Element | Dobra praktyka |
|---|---|
| `<title>` | unikalny dla każdej podstrony, do ok. 60 znaków, najważniejsze słowa na początku |
| `<meta name="description">` | opis w wynikach wyszukiwania, do ok. 160 znaków |
| nagłówki `h1`–`h6` | jeden `h1` z głównym tematem, logiczna hierarchia |
| tekst odnośników | opisowy: „cennik noclegów”, a nie „kliknij tutaj” |
| `alt` obrazów | opis treści obrazu |
| semantyka | `header`, `main`, `article` zamiast samych `div` |
| adresy URL | krótkie, czytelne: `/cennik.html`, a nie `/strona?id=17` |

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agroturystyka nad jeziorem – noclegi na Pomorzu Zachodnim</title>
    <meta name="description" content="Pokoje dla rodzin, kajaki i domowe posiłki nad jeziorem. Nocleg ze śniadaniem od 120 zł.">
</head>
```

### Szybkość strony

| Problem | Rozwiązanie |
|---|---|
| zbyt duże obrazy | przeskaluj do wyświetlanego rozmiaru, kompresja, format WebP |
| obrazy poza ekranem pobierane od razu | `loading="lazy"` |
| skok układu po wczytaniu obrazu | atrybuty `width` i `height` |
| duże pliki CSS/JS | minifikacja (usunięcie spacji i komentarzy) |

### Lighthouse <span class="zakres zakres-gw">★</span>

Narzędzie wbudowane w Chrome: ++f12++ → zakładka **Lighthouse** → *Analyze page load*. Ocenia stronę w skali 0–100 w czterech kategoriach: *Performance* (szybkość), *Accessibility* (dostępność), *Best Practices* (dobre praktyki), *SEO*.

## Zadanie główne (25 min)

Pobierz i rozpakuj [seo.zip](../pliki/lekcja-42/seo.zip){ download }. Otwórz stronę przez Live Server, bo Lighthouse nie działa poprawnie dla plików otwieranych bezpośrednio z dysku.

1. Uruchom Lighthouse (tryb *Mobile*). Zapisz w pliku `raport.txt` wyniki czterech kategorii.
2. Uzupełnij `head`: `viewport`, opisowy `title`, `meta description` (wymyśl treść na podstawie strony).
3. Zamień bloki `div` z klasami `baner`, `tytul`, `tresc`, `naglowek` na odpowiednie znaczniki semantyczne i nagłówki. Popraw selektory w CSS.
4. Obraz `jezioro.jpg` ma 3000 px szerokości i ok. 1,4 MB, a wyświetla się w 400 px. Przygotuj w GIMP wersję 800 px szerokości (dla ekranów o dużej gęstości pikseli) w formacie WebP lub JPG o jakości 75. Dodaj `alt`, `width`, `height` i `loading="lazy"`.
5. Popraw tekst odnośnika „kliknij tutaj”.
6. Uruchom Lighthouse ponownie. Zapisz nowe wyniki i porównaj z pierwszymi.

## Zadanie dla chętnych <span class="zakres zakres-gw">★ poza egzaminem</span>

Dodaj do strony znaczniki Open Graph (`og:title`, `og:description`, `og:image`). Dowiedz się, do czego służą: co się dzieje, gdy wklejasz link do strony na Messengerze lub w innym komunikatorze?

## Czy potrafię…?

- [ ] napisać dobry `title` i `meta description`
- [ ] wymienić 5 elementów strony ważnych dla wyszukiwarki
- [ ] zoptymalizować obraz dla strony
- [ ] przeprowadzić audyt w Lighthouse i odczytać wyniki
