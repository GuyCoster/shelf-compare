# Shelf Compare

Search Google Books and Open Library at once and compare the results side by side.

**Live:** https://guycoster.github.io/shelf-compare/

## Features

- One search box with five modes: anything, title, author, subject or ISBN. Each search queries both APIs in parallel.
- **Side-by-side view:** books found in both catalogs are paired in one row. ≡ means they share an ISBN; ≈ means the title and author match. Books found in only one catalog are listed below the pairs.
- **Stats bar:** total hits, response time, how many results have a cover or a rating, and how many books appear in both.
- **Compare panel:** every field from both sources. Yellow marks fields where the sources disagree, green marks fields only one source has, and a short summary sits underneath.
- **Explore:** tap an author or subject chip to search it in both catalogs. Recent searches are kept as chips.
- **Table of contents** in the compare panel, taken from Open Library editions when one is listed. It first tries the edition with the same ISBN as Google's result, then the work's other editions. Google Books' API doesn't provide tables of contents.
- **Google API key:** paste your own free key under "⚙ Google API key". Without one, Google's shared free limit is usually used up and its results come back empty. The key is stored only in your browser (localStorage) and is never committed here.
- Light and dark mode; works on mobile.

## Tech

A single `index.html` with no build step, no dependencies and no API key.

- Google Books: `https://www.googleapis.com/books/v1/volumes`, with an optional `&key=`. To get a key, enable the Books API in Google Cloud Console and create an API key. Restricting it to the Books API and `guycoster.github.io/*` is recommended.
- Open Library: `https://openlibrary.org/search.json`, plus `/works/{id}.json` for descriptions, `/isbn/{isbn}.json` and `/works/{id}/editions.json` for tables of contents, and `covers.openlibrary.org` for cover images.

To run it locally, open `index.html` in a browser.
