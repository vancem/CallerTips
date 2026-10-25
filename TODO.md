# TODO

Future work for CallerTips. Add an item here when it should be picked up later.
Write enough that the item can be done without the conversation that created it:
what is true today, why it is waiting, and when to do it.

## Revisit the site generator before Material for MkDocs ends

The published book is built with MkDocs 1.6 and the Material theme, pinned in
`requirements.txt` as `mkdocs==1.6.*`, `mkdocs-material==9.*`, and
`mkdocs-print-site-plugin==2.*`. `mkdocs.yml` selects the Material theme.
`.github/workflows/deploy.yml` runs `mkdocs build` and publishes the `site`
directory to GitHub Pages on every push to `main`.

The book must keep a single page that prints the whole thing. The `print-site`
plugin adds that page, titled "Print / PDF (whole book)", with a cover page and
chapter numbers. The home page links to it at `print_page/`. Figure centering
lives only in `docs/stylesheets/extra.css`, so the Markdown stays plain.

Material for MkDocs is in critical maintenance and ends on **May 5, 2027**. Its
successor, from the same author, is [Zensical](https://zensical.org/). Zensical
stays free and can build an existing `mkdocs.yml`. On **November 5, 2026**
Zensical 0.1.0 starts its stable release line. See [Upcoming
changes](https://zensical.org/upcoming-changes/) and [Migrate from
MkDocs](https://zensical.org/docs/compatibility/mkdocs/migration/).

In October 2026 a Zensical build of this repo succeeded and the chapter Markdown
did not need edits. Zensical did not run the `print-site` plugin, so the
whole-book print page was absent. The plugin author has said Zensical support
will not be added to `mkdocs-print-site-plugin`; a replacement would have to be
a new plugin. See [mkdocs-print-site-plugin issue
147](https://github.com/timvink/mkdocs-print-site-plugin/issues/147).

ProperDocs is the other option. It continues the MkDocs 1.6 line so existing
themes and plugins, including Material and `print-site`, keep working. As of
October 2026 the current release was 1.6.7 (March 20, 2026). It is a
compatibility fork, not the path Material's author is developing. See
[ProperDocs](https://github.com/ProperDocs/properdocs).

**November 5, 2026: retest, and leave the published site on Material.** Build
this repo with the stable Zensical and check three things: the whole-book print
page, figure centering, and that chapter addresses such as
`/06-learning-to-resolve-a-square/` are unchanged. Switch only if the print page
is actually there.

**February 2027: do the move.** That leaves time to fix the print page before
maintenance stops. Prefer Zensical if it can print the whole book by then,
whether through its own PDF publishing or a replacement plugin. Keep the
Markdown as it is, keep the GitHub Actions deploy, and check the print page,
centering, search, and chapter addresses before replacing the build command.

If Zensical still cannot print the whole book in February 2027, move the build
to ProperDocs instead, and confirm that `mkdocs-material` and
`mkdocs-print-site-plugin` still install and pass the same checks. Staying on
the last Material release after May 5, 2027 means the generator gets no further
fixes.
