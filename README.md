# ✦ Swiftie Atlas

An open, sourced, fan-made atlas of the Taylor Swift universe:

- **Song → subject map.** Which ex, friend, rival, or family member each song is widely tied to, with a confidence label on every entry.
- **Drama map.** An interactive network of exes, friendships, faded friendships, feuds, reconciliations, and business disputes.
- **Likes & dislikes.** What she has publicly said she loves or can't stand.
- **Easter eggs & symbolism.** Per album, plus how symbols evolve across her whole career.
- **Economy case study.** How one artist measurably moves hotel revenue, antitrust policy, NFL ratings, and more.

👉 **Interactive site:** open [`docs/index.html`](docs/index.html), or enable GitHub Pages (Settings → Pages → Branch `main`, folder `/docs`).

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

## Ground rules

1. **No lyrics.** Song lyrics are copyrighted. Reference songs by **title**, and describe themes in your own words.
2. **Confidence labels are required.** Every song-subject link is `confirmed`, `widely_reported`, or `fan_theory`. Speculation is labeled as speculation.
3. **Public events only.** Nothing private, nothing about non-public people beyond what they've made public themselves, and no harassment of anyone named here.
4. **Sources are encouraged.** See [CONTRIBUTING.md](CONTRIBUTING.md).

## Run locally

The page fetches its JSON, so serve the folder instead of double-clicking the file:

```bash
cd docs && python3 -m http.server 8000
```

Then open http://localhost:8000.

---
*Fan project. Not affiliated with or endorsed by Taylor Swift, her label, or anyone named here. Data current as of October 2025.*
