# rcs360-site-articles

The `articles/` directory of **rcs360.co.il**, and nothing else.

The hosting panel deploys this repository into that one folder. Keeping it
narrow is deliberate: a repo wired to the site root would delete every file
the repo does not contain — the logo, the stylesheet, `accessibility.js` —
on its first pull. Here the worst case is a broken article page.

## What is in here

| pages | where they come from |
|---|---|
| 3 hand-written articles | were trapped inside a JavaScript array on `articles.html`, invisible to any crawler that does not execute JS. Lifted out into real pages on 2026-09-30. |
| 15 generated pages | built from the social queue by `scripts/site/build-article.mjs` in the **RCS360-Growth** repo. |

## The generated ones, and what they are not

They are built from posts Roy already published, and every word on them is
his. The generator's job is markup, never content.

A page is produced only when the queue item has a carousel spec behind it and
still has real prose once the opening line is promoted to the lead. Roughly
two thirds of the queue is rejected on that test, by design: a feed caption
on its own makes a thin page, and thin pages drag a site down rather than up.

Three rules the generator holds, each of which was a defect first:

- **The lead is the body's own first paragraph, moved.** Building it
  separately printed the same idea three times per page — lead, table, body.
- **The table is only `stat` and `compare` slides.** `text` slides are the
  caption restated for a square, so tabling them prints the same sentences
  twice.
- **Feed-only calls to action are stripped.** "הקישור בביו" is correct in a
  feed and nonsense on a page that has a nav bar.

## Editing

Edit the HTML here for a one-off fix. For anything systematic, fix the
generator in RCS360-Growth — a change made only here is overwritten the next
time that item is rebuilt.

