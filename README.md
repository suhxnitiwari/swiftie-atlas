# ✦ Swiftie Atlas

*An open, sourced, fan-made atlas of the Taylor Swift universe: who each song is about, who's feuding with whom, and what it all does to the economy.*

**Live:** https://suhxnitiwari.github.io/swiftie-atlas/

## What it is

Fan knowledge usually lives in threads and TikToks with no sources and no way to tell fact from theory. This atlas puts it in structured, labeled data and makes it explorable:

- **Song → subject map.** 77 songs across 13 albums, each tied to the ex, friend, rival or family member it's linked to, with a confidence label on every entry (20 confirmed, 39 widely reported, 18 fan theories).
- **Drama map.** An interactive network of 43 people and 49 relationships: exes, friendships, faded friendships, feuds, reconciliations and business disputes.
- **Easter eggs & symbolism.** Colors, symbols and easter eggs for 12 eras, plus a write-up of how symbols evolve across her whole career.
- **Likes & dislikes.** What she has publicly said she loves or can't stand.
- **Swiftonomics case study.** How one artist measurably moves hotel revenue, antitrust policy, NFL ratings and voter registration, with caveats and sources.

## How it's built

- **Data first.** Everything lives in four JSON files under `docs/data/` with a `_meta` block each, so the page is just a view over the data and contributors can edit facts without touching code.
- **D3 force-directed graph.** `d3.forceSimulation` with link, charge, center and collision forces. Link length depends on relationship type, nodes are draggable (pinned while dragging, released after), and positions are clamped so nothing escapes the frame. Rumored feuds and faded friendships are drawn as dashed lines.
- **Cross-referenced tooltips.** Hovering a person in the network looks up every song linked to them in `songs.json` and lists the titles.
- **Filterable song table** by album, confidence level and free-text search, all client-side.
- **Safe rendering.** Every string from the data is HTML-escaped before it reaches the page.
- **Light and dark themes** through CSS custom properties and `prefers-color-scheme`.

## Design choices

- **No lyrics, ever.** Songs are referenced by title and themes are described in my own words. That rule is in the README, the contributing guide and the page header.
- **Confidence is part of the data model.** Every song-subject link must be `confirmed`, `widely_reported` or `fan_theory`, so speculation always looks like speculation.
- **Public events only,** and a color-coded legend that turns a messy celebrity timeline into something you can read at a glance.
- **Each era card wears its album color,** so the eras grid doubles as a palette of her career.

## What's inside

```
docs/
  index.html            interactive map (D3 force graph + filterable tables)
  data/
    songs.json          song → subject, album, confidence, theme (no lyrics)
    network.json        people + relationship edges (ex, friend, feud, reconciled…)
    eras.json           per-album colors, symbols, easter eggs
    likes.json          public likes & dislikes
analysis/
  symbolism.md          recurring symbols across the whole career
  economy-case-study.md Swiftonomics: the Eras Tour, Ticketmaster, masters, NFL, voting
```

## Tech stack

HTML, CSS, vanilla JavaScript, D3.js v7, JSON. Analysis in Markdown.

## Run it locally

The page fetches its JSON, so serve the folder instead of double-clicking the file:

```bash
cd docs && python3 -m http.server 8000
```

Then open http://localhost:8000.

## Ground rules for contributing

1. **No lyrics.** Song lyrics are copyrighted. Reference songs by **title**, and describe themes in your own words.
2. **Confidence labels are required.** Every song-subject link is `confirmed`, `widely_reported`, or `fan_theory`.
3. **Public events only.** Nothing private, nothing about non-public people beyond what they've made public themselves, and no harassment of anyone named here.
4. **Sources are encouraged.** See [CONTRIBUTING.md](CONTRIBUTING.md).

---

*Fan project. Not affiliated with or endorsed by Taylor Swift, her label, or anyone named here. Data current as of October 2025.*

Built by [Suhani Tiwari](https://suhanitiwari.com).
