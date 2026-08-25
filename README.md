# Eric Asiedu-Akrofi — Portfolio
<img width="356" height="357" alt="d64682ce-1b5f-4880-9549-b08cb6edf254" src="https://github.com/user-attachments/assets/184587c2-ffa1-4d8f-9b72-7215f92d3d00" />

A single-file, no-build personal portfolio site hosted free on GitHub Pages. Built to showcase financial modelling, equity research, assurance work, and data analytics projects, and to double as a living resume.

**Live site:** `https://kuame-klaus.github.io`

## Features

- **Live project ledger** — pulls all public repos directly from the GitHub API at page load, no manual updates needed when a new repo is added
- **Project gallery** — auto-scrolling strip of real screenshots pulled from each repo's README
- **GSE stock ticker** — live Ghana Stock Exchange prices via a free public API, scrolls continuously, shows LIVE vs LAST CLOSE based on actual GSE trading hours
- **Skills matrix** — animated bar chart across core competency areas
- **Case studies** — expandable Problem → Approach → Result panel for flagship projects
- **Qualifications & Education** — certifications and academic background
- **Career timeline** — work history as a "workpaper index" styled ledger
- **Sankofa Pathways Foundation** — a section on a proposed NGO initiative, framed honestly as pre-launch/vision stage
- **Dark/light theme toggle** — instant switch, no page reload
- **Fully responsive** — works on mobile, tablet, and desktop
- **Zero cost, zero backend** — plain HTML/CSS/JS, no build tools, no server, no paid APIs or API keys anywhere

## Tech

Single `index.html` file. Fonts via Google Fonts CDN (Space Grotesk, Inter/JetBrains Mono depending on theme). No frameworks, no npm, no dependencies beyond what's loaded directly in the file.

APIs used (both free, no key required):
- `api.github.com` — live repo data for the project ledger
- `dev.kwayisi.org/apis/gse/live` — live Ghana Stock Exchange prices

## Deployment

This repo is set up as a GitHub Pages user site (`{username}.github.io`), so it deploys automatically:

1. Push changes to the `main` branch
2. GitHub Pages rebuilds within a minute or two
3. Live at `https://kuame-klaus.github.io`

To run locally, just open `index.html` in a browser, no build step required. (Some browsers block `fetch` calls on `file://` URLs due to CORS; if the ticker/gallery don't load locally, serve it with any static file server, e.g. `python3 -m http.server`.)

## Adding your CV

The "Download CV" button links to `/assets/Eric-Asiedu-Akrofi-CV.pdf`. To activate it:

1. Create an `assets/` folder in the repo root
2. Add your CV PDF there, named exactly `Eric-Asiedu-Akrofi-CV.pdf`

## Structure

```
├── index.html                          # the entire site
├── d64682ce-1b5f-4880-9549-b08cb6edf254.jpg   # profile photo
└── assets/
    └── Eric-Asiedu-Akrofi-CV.pdf        # add this to enable the CV download button
```

## Notes

- Project screenshots are hardcoded from each repo's README at the time of writing; repos without a README image (e.g. TeslaEquity) fall back to GitHub's auto-generated repo preview
- The GSE ticker degrades gracefully if the API is unreachable, showing a fallback message instead of breaking the page
