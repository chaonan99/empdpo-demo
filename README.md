# EmpDPO — audio samples (static site)

Supplementary audio page for the ICASSP 2027 submission.
**Live:** https://chaonan99.github.io/empdpo-demo/ (repo `chaonan99/empdpo-demo`, personal GitHub; ICASSP 2027 is single-blind so the real name is fine).
Built by `proj/tts/tts_emphasis/scripts/eval/build_paper_demo_site.py`
(12 random evaluation sentences per language × 2 reference voices × all
systems, plain + emphasis; every clip −24 LUFS / 48 kHz mono MP3 64 kbps).
Rebuild with a different `--seed` to draw other sentences.

## Publish / update
The site is pushed from a working copy on the local Mac (the devpod has no
credential for the personal account). To update after a rebuild:
```bash
# devpod: rebuild, then tar and pull it to the Mac (aip job ssh, base64 for safety)
python scripts/eval/build_paper_demo_site.py && tar czf /tmp/empdpo-demo.tgz -C demo_site .
# Mac: aip job ssh devpod --project 58705533-dialog-speech "base64 -w0 /tmp/empdpo-demo.tgz" | base64 -D -o /tmp/empdpo-demo.tgz
#      tar xzf /tmp/empdpo-demo.tgz -C /tmp/empdpo-demo && cd /tmp/empdpo-demo && git add -A && git commit -m ... && git push
```
Remote URL pins the account: `https://chaonan99@github.com/chaonan99/empdpo-demo.git`
(`gh auth git-credential` otherwise picks the `haonanc_adobe` EMU login, which
cannot own public repos). Pages source: branch `main`, folder `/`.

## Content checklist
- No internal hostnames or repository paths in `index.html` / `manifest.json`
  (grep for colligo|devpod|pluto|sensei → 0 hits). Voices are numbered 1–8; only
  the numbers appear on the page.
- All page text is English; the stimulus sentences are in their own language.
- No analytics or third-party embeds.
