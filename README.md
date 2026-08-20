# Dutch Circular Economy PhD Network

Source for the [Dutch CE PhD Network website](https://aymara-wagner.github.io/CE-PhD-Network/), connecting early-career researchers working on the circular economy transition across the Netherlands.

This guide is written for editors with little or no coding experience. The two things you'll do most — adding an event, adding a council member — need nothing more than filling in a template file. Everything past that section is background reference for anyone who wants it.

---

## Getting your own copy of this site (cloning)

You only need to do this once.

1. Install **[GitHub Desktop](https://desktop.github.com/)** and sign in with your GitHub account.
2. Go to the [repository page](https://github.com/aymara-wagner/CE-PhD-Network) and click the green **Code** button, then **Open with GitHub Desktop**.
3. Choose a folder on your computer and click **Clone**.

You now have a folder with all the site's files, and GitHub Desktop will show you what's changed whenever you edit something.

**Prefer not to install anything?** You can skip cloning entirely and edit files directly on [github.com](https://github.com/aymara-wagner/CE-PhD-Network) — open the file, click the pencil (✏️) icon, make your change, and scroll down to commit it. This works for everything below.

---

## Adding a future event

1. Open the [`templates`](templates) folder and copy [`event-template.md`](templates/event-template.md).
2. Paste the copy into the [`_events`](_events) folder.
3. Rename it to the event's date and a short name, e.g. `2027-03-12-spring-networking-drinks.md`.
4. Open it and fill in the fields — the file itself explains each one. Change the words after each `title:`, `date:`, etc.
5. Save, then commit and push (in GitHub Desktop: write a short summary, click **Commit**, then **Push origin**).

That's it. The website rebuilds itself automatically, usually within a minute or two. **Whether your event shows under "Future Events" or "Past Events" is worked out automatically from its date** — you never move it yourself.

## Adding a council member

1. Copy [`templates/council-member-template.md`](templates/council-member-template.md) into the [`_council`](_council) folder.
2. Rename it to the person's name, e.g. `devries-anna.md`.
3. Fill in their name, role, affiliation.
4. Got a photo? Crop it **square** first — it displays as a small circle, so a non-square photo will look stretched. Add the image file to [`assets/photos`](assets/photos), then put its exact filename in the `photo:` field.
5. No photo yet? Delete the `photo:` line entirely — the site automatically shows the person's initials instead.
6. Save, commit, push.

They appear on the site automatically, sorted alphabetically by surname.

## Checking your edit before it's public

Small text edits (a name, a date, a sentence) can't break the page layout — the template controls that, not you. To actually see the result:

- **Push it, then wait about a minute** and look at the [live site](https://aymara-wagner.github.io/CE-PhD-Network/). This works for any edit and needs nothing installed.
- If you badly damage a file's structure (e.g. delete one of the `---` lines), the site's automatic build fails safely: you'll get an email from GitHub, and **the live site keeps showing its last working version** — it does not go down or show something broken.

---

## Everything else (reference)

### Site structure

```
index.html          The homepage: masthead, about, events, council, contact
style.css            All colours, fonts, layout
Logo.PNG              The logo
_config.yml           Jekyll site settings
_layouts/default.html The page shell (used by every page)
_includes/             Reusable chunks: header, footer, one event card, one member card
_events/                One file per event — see "Adding a future event" above
_council/                One file per council member — see "Adding a council member" above
templates/                 Starting-point files to copy from — not part of the live site
assets/photos/               Council member portraits
```

This site is built with **[Jekyll](https://jekyllrb.com/)**, which GitHub Pages runs automatically on every push — nothing to install for that to happen. `_events` and `_council` are Jekyll *collections*: every file placed in one of those two folders is automatically picked up, sorted, and rendered into the matching section of the page. `index.html` contains the logic that splits events into "Future" and "Past" and lists council members alphabetically; you shouldn't need to touch that logic for routine edits.

### The "teal labels must match the nav" rule

The small teal uppercase label above a section heading must read exactly the same as that section's link in the top navigation (About, Future Events, Past Events, Council, Contact). A section with no nav link gets no label. The one exception is the invitation band's "Join the network", which is a call to action, not a nav destination.

### Editing text outside events/council

The masthead, "Who are we?", "What can you expect?", and "Get in touch" sections are static content living directly in `index.html` — search for the words you want to change and edit them in place, the same as editing any of the template files.

### Running a full local preview (optional, for developers)

Routine edits don't need this — push and check the live site instead. If you want an instant local preview that rebuilds as you save, you'll need Ruby with a working compiler toolchain (on Windows, install ["Ruby+DevKit"](https://rubyinstaller.org/) — plain Ruby is not enough, native gems will fail to build without it), then from the repo root:

```bash
bundle install
bundle exec jekyll serve
```

This starts a local server (usually `http://127.0.0.1:4000/CE-PhD-Network/`) that rebuilds automatically whenever you save a file. `Gemfile` pins Jekyll and every plugin to the exact versions GitHub Pages builds with in production, so what you see locally matches what goes live.

### HTML basics, if you're editing `index.html` directly

- Everything sits between a matching opening and closing tag: `<h2>Circular Society Day</h2>`. Edit the text in the middle; leave the tags alone.
- `class="..."` attributes control styling via `style.css` — don't change these.
- Every opening tag needs its closing tag. Deleting one half collapses the layout below it.
- `<br>` forces a line break and has no closing tag. Useful in short titles, but check it on a narrow browser window before pushing — a forced break that looks good on a laptop can strand a lone word on mobile.
- `&nbsp;` is a space that won't break across lines, useful for keeping something like "Princetonlaan 6" together.
