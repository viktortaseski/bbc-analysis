# BBC News - Quarto project

This folder contains the full submission for the project "What Makes a BBC
News Category? A Tidyverse-Based Exploration of 2,225 Articles".

## Files in this folder

| File                          | What it is                                                                 |
|-------------------------------|----------------------------------------------------------------------------|
| `bbc-news-analysis.qmd`       | The Quarto source. Render in RStudio or with `quarto render`.              |
| `bbc-news-analysis.html`      | The pre-rendered, fully self-contained HTML report (embedded resources).   |
| `bbc-news-data.csv`           | The raw dataset (tab-separated, from Kaggle).                              |
| `category_meta.csv`           | Auxiliary table joined to the data with `inner_join`.                      |
| `figures/`                    | PNG copies of the four ggplots used in the report.                         |
| `website.txt`                 | URL where the report is published (edit after you deploy).                 |

## How to re-render the .qmd locally

You need R (≥ 4.2) and Quarto (≥ 1.4).

```r
install.packages(c("tidyverse", "knitr", "scales", "stringr"))
```

Then from this folder:

```bash
quarto render bbc-news-analysis.qmd
```

That produces a fresh `bbc-news-analysis.html` whose resources are
embedded thanks to `embed-resources: true` in the YAML header.

## How to publish the report on Netlify

Netlify's drag-and-drop deploy is the simplest path:

1. Open https://app.netlify.com/drop in your browser.
2. Drag `bbc-news-analysis.html` directly onto the drop zone. Netlify will
   give you a temporary URL like `https://random-name-1234.netlify.app/`.
   Because the HTML is self-contained, no other files are required.
3. (Optional) Sign in, click "Site settings → Change site name", and pick
   something readable, e.g. `bbc-news-analysis-vt`. The URL becomes
   `https://bbc-news-analysis-vt.netlify.app/`.
4. Open `website.txt` in this folder and replace the placeholder URL with
   the one Netlify just gave you.

> If you prefer a multi-file site (e.g. you also want the data and the .qmd
> to be browsable), zip the entire folder and drop the .zip onto Netlify's
> drop zone. The home page still has to be called `index.html`, so rename
> `bbc-news-analysis.html` to `index.html` first, or add a `_redirects`
> file with `/  /bbc-news-analysis.html  200`.

### Alternative: student.famnit.upr.si

If you have an account on `student.famnit.upr.si`, simply `scp` the
`bbc-news-analysis.html` (and, if you want them, the supporting files)
into your `public_html/` directory. The published URL will look like
`https://student.famnit.upr.si/~your-username/bbc-news-analysis.html`.

## How to submit on the e-classroom

Upload these three files to the e-classroom assignment:

1. `bbc-news-analysis.qmd`
2. `bbc-news-analysis.html`  (already self-contained)
3. `website.txt`             (with the URL Netlify gave you)

The e-classroom often allows a single ZIP. If so, zip the whole folder
(including `bbc-news-data.csv` and `category_meta.csv` so the .qmd can be
re-rendered by the grader) and upload that.

## Quick checklist mapping the assignment requirements

- [x] Topic on university level, made in Quarto (`.qmd`).
- [x] Dataset from Kaggle (BBC News dataset).
- [x] Tidyverse approach with `mutate`, `filter`, `summarise`, `inner_join`,
      `ggplot2`, user-defined functions, all chained with `|>`.
- [x] Section 1 - Introduction.
- [x] Section 2 - Presentation of the data, with `head()` and column
      types/units explained.
- [x] Section 3 - Three transformation tables, each explained.
- [x] Section 4 - Four ggplots of distinct types (bar, boxplot, histogram,
      heatmap), each explained.
- [x] Section 5 - Interpretation / Conclusion.
- [x] Section 6 - References, including the dataset's location and
      tidyverse / Wikipedia citations.
- [x] Self-contained HTML output (`embed-resources: true`).
- [x] `website.txt` with the published URL.
