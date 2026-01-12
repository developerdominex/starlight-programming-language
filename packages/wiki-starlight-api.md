# wiki-starlight-api

A simple **Wikipedia API wrapper** for fetching **search results, summaries, full content, images, categories, and languages**. Works in **JavaScript** and **Starlight**.

---

## Installation

Install via npm:

```bash
npm install wiki-starlight-api@latest
```

---

## Import

For both **JavaScript** and **Starlight**:

```js
import * as wiki from "wiki-starlight-api";
```

---

## Usage in JavaScript

```js
import * as wiki from "wiki-starlight-api";

(async () => {
  // Search articles
  const results = await wiki.search("JavaScript", 5);
  console.log("Search results:", results);

  // Get summary of an article
  const jsSummary = await wiki.summary("JavaScript");
  console.log(jsSummary);

  // Get full page content
  const jsPage = await wiki.page("JavaScript");
  console.log(jsPage.content);

  // Get a random article
  const randomArticle = await wiki.random();
  console.log(randomArticle);

  // Get article languages
  const langs = await wiki.languages("JavaScript");
  console.log("Available languages:", langs);

  // Get article images
  const imgs = await wiki.images("JavaScript");
  console.log("Images:", imgs);

  // Get article categories
  const cats = await wiki.categories("JavaScript");
  console.log("Categories:", cats);

  // Search and get summaries
  const summaries = await wiki.searchAndSummary("Python", 3);
  console.log(summaries);
})();
```

---

## Usage in Starlight

```sl
import * as wiki from "wiki-starlight-api";

// Search articles
const results = await wiki.search("JavaScript", 5);
sldeploy("Search results:\n" + results);

// Get summary
const jsSummary = await wiki.summary("JavaScript");
sldeploy("JavaScript summary:\n" + jsSummary.extract);

// Get full page content
const jsPage = await wiki.page("JavaScript");
sldeploy(jsPage.content);

// Get random article
const randomArticle = await wiki.random();
sldeploy("Random article:\n" + randomArticle.title + "\n" + randomArticle.extract);

// Get article languages
const langs = await wiki.languages("JavaScript");
sldeploy("Languages: " + langs.map(l => l.lang + " → " + l.title).join(", "));

// Get images
const imgs = await wiki.images("JavaScript");
sldeploy("Images: " + imgs.join(", "));

// Get categories
const cats = await wiki.categories("JavaScript");
sldeploy("Categories: " + cats.join(", "));

// Search and get summaries
const summaries = await wiki.searchAndSummary("Python", 3);
summaries.forEach(s => sldeploy(s.title + ": " + s.extract));
```

---

## Features

* `search(query, limit)`: Search Wikipedia articles.
* `summary(title)`: Get article summary (intro).
* `page(title)`: Get full article content as plain text.
* `random()`: Get a random article.
* `languages(title)`: Get available translations for an article.
* `images(title)`: Get images used in an article (PNG, JPG, JPEG, SVG, GIF).
* `categories(title)`: Get categories of an article.
* `searchAndSummary(query, limit)`: Search and return summaries for results.

---

## Notes

* All functions are **asynchronous**, so use `await` in Starlight or JavaScript.
* Fetches data directly from **Wikipedia’s REST API** or **MediaWiki API**.
* Designed for **simplicity and quick access** to article data.

