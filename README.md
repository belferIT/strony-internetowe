# Strony internetowe – materiały do lekcji (INF.03)

Strona: https://belferit.github.io/strony-internetowe/

## Podgląd lokalny

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Strona będzie dostępna pod adresem http://127.0.0.1:8000 i odświeża się po każdym zapisie pliku.

## Publikacja

Każdy `git push` do gałęzi `main` uruchamia GitHub Actions (`.github/workflows/deploy.yml`), który buduje stronę i publikuje ją na GitHub Pages.
