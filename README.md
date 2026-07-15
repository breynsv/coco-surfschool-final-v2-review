# Coco Surf School — review / change-request tool

A single self-contained page for the school owner to request website changes, section by section, against the **Dutch** version of the site. It loads the live site at [`coco-surfschool-final-v2`](https://breynsv.github.io/coco-surfschool-final-v2/) in an iframe.

- Per-section status (OK / Aanpassen / Verwijderen) + comment, plus photo attach on image sections.
- Auto-saves to the browser (localStorage). Photos are held in memory for the session.
- **Kopieer alles** → copies structured Markdown (text). **Download** → `.zip` with `feedback.md` + attached photos (or a `.md` if no photos).
- The exported `feedback.md` is written as a ready-to-paste **Claude Code prompt**: it tells Claude to edit `content/{nl,fr,en}.mjs` in the `coco-surfschool-final-v2` repo, translate NL→FR/EN, drop bundled photos into `assets/images/`, and run `node build.mjs`.

`noindex` + `robots.txt Disallow` — not meant to be publicly discovered. Everything is in one `index.html` (no dependencies; includes a tiny store-only ZIP encoder).
