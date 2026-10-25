# CallerTips: Caller Tips I Wish I Had Been Given

**Read it online: <https://vancem.github.io/CallerTips/>**

CallerTips is a free guide for new and aspiring square dance callers by Vance Morrison.
It covers your first singing call, learning to resolve a square (stations, zeros,
chicken pluckers, foolproof two-couple resolution), using the Taminations sequencer,
microphones and sound equipment, rules for good patter, no-experience-necessary dances,
progressive squares and six-couple squares.

It is a companion to [CallerBuddy](https://github.com/vancem/CallerBuddy), a music player
and lyric manager for square dance callers.

## How the site is built

The book is plain Markdown: one file per chapter in `docs/`, with images in `docs/images/`.
The chapter order is the `nav` list in `mkdocs.yml`.
[MkDocs Material](https://squidfunk.github.io/mkdocs-material/) turns the pages into the
website, and the `Deploy site` GitHub Action publishes it to GitHub Pages on every push
to `main`.

To preview locally:

```
pip install -r requirements.txt
mkdocs serve        # preview at http://127.0.0.1:8000/CallerTips/
```
