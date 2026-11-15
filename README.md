# My R Site

A Quarto website built with R and deployed to GitHub Pages by GitHub Actions.

## Local preview

```r
# install.packages(c("knitr", "rmarkdown", "ggplot2"))
quarto::quarto_preview()      # or in a terminal: quarto preview
```

## Publish (one-time setup)

1. Create an empty repo on GitHub, e.g. `Jadevkota/Jadevkota.github.io`.
2. Replace `Jadevkota/Jadevkota.github.io` in `_quarto.yml`.
3. Push:
   ```bash
   git init -b main
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/Jadevkota/Jadevkota.github.io.git
   git push -u origin main
   ```
4. On GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
5. The **Actions** tab shows the build. The site goes live at `https://jadevkota.github.io/`.

After that, every push to `main` rebuilds and redeploys the site.

## Tips

- `freeze: auto` caches R results in `_freeze/`. Run `quarto render` locally and commit `_freeze/` so CI doesn't re-run heavy code.
- Add R packages to the `packages:` list in `.github/workflows/publish.yml`, or switch to `renv` (`renv::init()` + `r-lib/actions/setup-renv@v2`).
- New blog post: create `posts/my-post/index.qmd`.

## Visitor statistics

GoatCounter (no cookies) is loaded on every page via `analytics.html`.
Dashboard: https://jadevkota.goatcounter.com — page views, referrers, countries, devices,
and outbound link clicks (listed as "click: …" events).
