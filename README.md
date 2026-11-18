# Shelf Compare

Search Google Books and Open Library at once and compare the results side by side.

**Live:** https://guycoster.github.io/shelf-compare/

## Features

- One search box with five modes: anything, title, author, subject or ISBN. Each search queries both APIs in parallel.
- **Side-by-side view:** books found in both catalogs are paired in one row. ≡ means they share an ISBN; ≈ means the title and author match. Books found in only one catalog are listed below the pairs.
- **Stats bar:** total hits, response time, how many results have a cover or a rating, and how many books appear in both.
- **Compare panel:** every field from both sources. Yellow marks fields where the sources disagree, green marks fields only one source has, and a short summary sits underneath.
- **Explore:** tap an author or subject chip to search it in both catalogs. Recent searches are kept as chips.
- Light and dark mode; works on mobile.

## Tech

A single `index.html` with no build step, no dependencies and no API key.

- Google Books: `https://www.googleapis.com/books/v1/volumes`. Requests without a key are rate-limited.
- Open Library: `https://openlibrary.org/search.json`, plus `/works/{id}.json` for descriptions and `covers.openlibrary.org` for cover images.

To run it locally, open `index.html` in a browser.
