# RLEF Project Page

Project page for **Reinforcement Learning from Ecological Feedback (RLEF): A
Framework for Aligning Language-Model Planning with Planetary Boundaries**,
AAAI Fall Symposium Series 2026.

[Zhangfei Yang](https://zhangfeiy.github.io/)\* and
[Aizierjiang Aiersilan](https://ezharjan.github.io/)\* (\*equal contribution),
The George Washington University.

## Page buttons

| Button | Target | Status |
|---|---|---|
| Slides | `RLEF_AizierjiangAiersilan_silides4AAAI2026FSS.pdf` (downloads the deck) | Final |
| Confab | [cal.com/ezhar/30min](https://cal.com/ezhar/30min) | Final |
| Paper | [AAAI Fall Symposium Series 2026](https://aaai.org/conference/fall-symposia/2026-fall-symposium-series-2/) | Placeholder; replace with the accepted-paper URL |

The buttons appear in the order of the `links` array in `config.json`.

## Editing the page

All page content lives in `config.json`; `static/js/render.js` renders it and
`config.schema.json` provides editor autocomplete and validation.

- Math written as `\( … \)` (inline) or `\[ … \]` (display) is typeset with KaTeX.
- Any section, the slides, the poster, or the BibTeX block can be hidden with
  `"enabled": false`.
- Theme colors are CSS variables at the top of `static/css/index.css`.

### Slides

The Slides section shows one image per slide from `static/images/slides/` in a
scrollable frame and links to the PDF in the project root. After replacing the
PDF, regenerate the images and update `slides.file` and `slides.pages` in
`config.json` (and the Slides entry in `links`):

```bash
rm static/images/slides/slide-*.png
pdftoppm -png -scale-to-x 1600 -scale-to-y -1 YOUR_SLIDES.pdf static/images/slides/slide
```

### Poster

To add a poster, place `paper_poster.pdf` in the root, set `poster.enabled` to
`true`, and add a Poster entry to `links`.

## Preview locally

The page loads `config.json` with `fetch()`, which browsers block for files
opened directly from disk. Serve the folder instead:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy (GitHub Pages)

1. Push this folder to a GitHub repository.
2. Open **Settings → Pages → Build and deployment**, choose **Deploy from a
   branch**, select the default branch and the folder `/ (root)`.
3. The page goes live at `https://<user>.github.io/<repo>/`.

## Structure

```
index.html            Generic shell (loads KaTeX and render.js)
config.json           All page content
config.schema.json    Schema for config.json
favicon.ico           Tab icon
RLEF_…FSS.pdf         Presentation slides
static/css/           Bulma, Font Awesome, and the page theme (index.css)
static/js/render.js   Renderer that turns config.json into the page
static/images/slides/ One image per slide for the Slides section
static/webfonts/      Font Awesome fonts
```

## Credits

Layout adapted from the [Nerfies](https://github.com/nerfies/nerfies.github.io)
academic project page template.
