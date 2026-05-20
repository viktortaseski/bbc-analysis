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
| `figures/`                    | PNG previews of the five ggplots; will be regenerated on `quarto render`.  |
| `website.txt`                 | URL where the report is published (edit after you deploy).                 |

## How to re-render the .qmd locally

You need R (≥ 4.2) and Quarto (≥ 1.4).

```r
install.packages(c("tidyverse", "knitr", "scales", "stringr",
                   "tidytext", "patchwork"))
```

`tidytext` provides the Bing/AFINN/NRC sentiment lexicons used in Plot 5,
and `patchwork` is the `+` operator that stitches the two panels of Plot 5
together.

Then from this folder:

```bash
quarto render bbc-news-analysis.qmd
```

That produces a fresh `bbc-news-analysis.html` whose resources are
embedded thanks to `embed-resources: true` in the YAML header.

## Live site
Link: https://bbc-news-analysis.netlify.app/