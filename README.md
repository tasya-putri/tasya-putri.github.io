# Tasya Putri — Portfolio

Static one-page portfolio for Nur Azizah Tasya Putri, Social Media Specialist and Content Creator.

- Live: https://tasya-putri.github.io/
- Resume: [`assets/Tasya-Putri-Resume.pdf`](assets/Tasya-Putri-Resume.pdf)

## Structure

```
index.html                     single page, inline CSS/JS, no build step
assets/Tasya-Putri-Resume.pdf  current resume (linked with download)
assets/images/                 photo, silhouette, OG image, favicon, resume preview
                               (silhouette.png = outline of tasya.png, same pixel grid; used only in the intro)
source/resume.tex              LaTeX source of the resume
source/og.html                 template used to render the OG image
```

## Edit

- **Site text/layout:** edit `index.html`. Commit and push; GitHub Pages rebuilds in about a minute.
- **Resume:** edit `source/resume.tex`, then rebuild:

```sh
export PATH="$HOME/Library/TinyTeX/bin/universal-darwin:$PATH"
cd source && pdflatex -interaction=nonstopmode resume.tex && pdflatex -interaction=nonstopmode resume.tex
cp resume.pdf ../assets/Tasya-Putri-Resume.pdf
rm -f resume.aux resume.log resume.out
```

- **Resume preview image:** `pdftoppm -r 130 -singlefile -png ../assets/Tasya-Putri-Resume.pdf p && cwebp -q 85 -m 6 p.png -o ../assets/images/resume-preview.webp`
- **OG image:** render `source/og.html` at 1200×630 in a browser and save over `assets/images/og-image.png`.

## Local preview

```sh
python3 -m http.server 8765
```

`?qa=1&at=<section-id>` renders a single section for screenshots; `?noanim=1` disables the intro and scroll reveals.
