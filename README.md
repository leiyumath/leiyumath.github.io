# Lei Yu's Personal Homepage

A minimal static academic homepage for GitHub Pages.

## Profile Image

The profile photograph is stored locally as `assets/ku-campus.jpg`, resized for
the web from the [University of Kansas campus photograph](https://places.ku.edu/sites/places/files/2022-08/2104725_MK_Campus.11.5.0111.jpg).
Its display crop is controlled by `.site-photo` in `styles.css`.
The desktop layout uses a centered content area up to 1120px wide and a responsive
288–384px square profile image alongside the name, About, and Contact sections.
About and Contact share the same left column. The square crop brings the sculpture
closer. On small screens the name and an image up to 288px wide are stacked and
centered, with the About and Contact sections below both.
Clicking the photograph opens the full-resolution original in a new tab. The
image credit in Others links to KU's official [Tai Chi Figure introduction](https://places.ku.edu/artwork/tai-chi-figure).

## CV

The CV is kept in this repository:

- LaTeX source: `cv/lei_yu_cv_moderncv.tex`
- Public PDF used by the homepage: `assets/Lei-Yu-CV.pdf`

To update the CV, edit the LaTeX source and rebuild the PDF:

```sh
make cv
```

This requires `xelatex` to be installed, for example through MacTeX. The build output goes into
`cv/build/`, and the generated PDF is copied to `assets/Lei-Yu-CV.pdf` so the
homepage link stays stable.

## Local Preview

Open `index.html` directly in a browser, or run a small local server:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Hidden Learning Announcements

Four News entries remain in `index.html` with their original text, links, dates,
and chronological positions. Each has `hidden data-news-category="learning"`:

- June 28, 2026: p-adic Langlands.
- April 12, 2026: geometrization of LLC.
- March 6, 2026: prismatic cohomology.
- September 17, 2025: derived categories of schemes.

To restore any of these announcements, remove its `hidden` attribute. Keep
`data-news-category="learning"` so the entries remain easy to find.

## Visitor Counter

The homepage loads the existing Hits.sh counter image to record page views.
The footer displays the count as text. The **Refresh view count** GitHub Actions
workflow reads Hits.sh statistics about every six hours and stores the total in
`view-count.json` on the `view-count` branch. It can also run manually from the
Actions tab. The homepage displays the number in `index.html` if it cannot
load the snapshot.

## GitHub Pages

For a user site, create a repository named:

```text
<username>.github.io
```

Push these files to the repository's `main` branch. GitHub Pages will publish the
site at:

```text
https://<username>.github.io
```

For a project site, push to any repository and enable GitHub Pages from
`Settings -> Pages`, using the `main` branch and root directory.
