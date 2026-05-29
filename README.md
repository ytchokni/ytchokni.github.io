# Personal Academic Website

**Live at:** https://ytchokni.github.io

## Structure

```
index.html      → Page shell, renders content from content.js
style.css       → All styles
content.js      → All editable text (bio, papers, abstracts, links)
profile.jpg     → Headshot
assets/cv.pdf   → Downloadable CV
cv/             → LaTeX source for the CV
```

## Editing Content

Edit `content.js` — it contains all text on the site as a plain JavaScript object. The HTML reads from it automatically.

**To add a new paper**, add an entry to `workingPapers` or `workInProgress`:

```js
{
  title: "Paper Title",
  authors: "with Coauthor Name",
  paper: "https://link-to-pdf.com",       // optional
  abstract: "Abstract text here.",          // optional
},
```

**To add a software project**, add to `software`:

```js
{
  title: "Project Name",
  description: "One-line description.",
  github: "https://github.com/ytchokni/repo",
},
```

**To update the photo**, replace `profile.jpg`.

**To update the CV**, replace `assets/cv.pdf` (and optionally rebuild from `cv/academic-cv.tex`).

## Deployment

GitHub Pages deploys automatically from `main`. Push and it's live within a minute:

```
git add -A && git commit -m "update" && git push
```

## Design Decisions

- **Plain HTML/CSS + JS** — no build step, no dependencies, no framework
- **Single page** — everything visible in one scroll, matching the standard econ JM candidate format
- **Content separated from layout** — `content.js` is the only file that needs editing for text changes
- **Abstracts as fold-open `<details>` elements** — expand in place, no page navigation
- **Mobile responsive** — photo stacks above text on narrow screens
