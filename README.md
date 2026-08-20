# Dutch Circular Economy PhD Network

Source for the [Dutch CE PhD Network website](https://aymara-wagner.github.io/CE-PhD-Network/), connecting PhD researchers working on the circular economy transition across the Netherlands.

The site is a static HTML/CSS page (`index.html` + `style.css`) served directly by GitHub Pages — no build step. To preview changes locally, open `index.html` in a browser, or run a local server from the repo root, e.g.:

```bash
python -m http.server 4321
```

then visit `http://localhost:4321`.

## Page structure

`index.html` is laid out in eight numbered sections (see the HTML comments): masthead, invitation,
about, what to expect, event, council, get involved, footer. The supporters/funders line appears
in the footer only.

## Updating the PhD Council section

Each council member is one `<article class="member">` block in `index.html`, sorted alphabetically
by surname. To add or edit a member, copy an existing block and change the avatar line:

- Photo available: `<img class="avatar" src="assets/photos/<file>.jpg" alt="Portrait of <Name>" loading="lazy" width="92" height="92">`
- No photo: `<div class="avatar avatar-initials" aria-hidden="true">XY</div>` (two-letter initials)

Photos live in `assets/photos/`. Square images work best — they are cropped to a circle.

For a member whose research topic is not yet confirmed, use
`<p class="member-bio member-bio-tbc">Topic to be confirmed.</p>`.
