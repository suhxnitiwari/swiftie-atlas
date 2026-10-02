# Contributing

PRs are welcome. Please:

1. **Never paste lyrics.** Use song titles and paraphrased themes only. PRs that contain lyrics will be closed.
2. **Label confidence honestly:**
   - `confirmed`: Taylor or the subject said so publicly (link it)
   - `widely_reported`: multiple major outlets report it
   - `fan_theory`: everything else
3. **Add a source** when you can (interview, liner notes, reputable outlet). Add a `"source"` field to the JSON entry.
4. **Keep it kind.** This project maps public events. It is not a place to attack anyone, including exes, ex-friends, or fans.
5. Validate the JSON before you open a PR:

```bash
for f in docs/data/*.json; do python3 -m json.tool "$f" > /dev/null || echo "BROKEN: $f"; done
```
