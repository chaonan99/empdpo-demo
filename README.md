# EmpDPO — audio samples (static site)

Anonymous supplementary audio page for the ICASSP 2027 submission.
Built by `proj/tts/tts_emphasis/scripts/eval/build_paper_demo_site.py`
(6 random evaluation sentences per language × 2 reference voices × all
systems, plain + emphasis; every clip −24 LUFS / 48 kHz mono MP3, 32 MB total).
Rebuild with a different `--seed` to draw other sentences.

## Publish on GitHub Pages (anonymous account)
1. Create a fresh GitHub account not linked to your name/employer; create an
   empty public repo, e.g. `empdpo-demo` (repo name must not reveal identity).
2. From this folder:
   ```bash
   git init -b main && git add -A && git commit -m "audio samples"
   git remote add origin https://github.com/<anon-account>/empdpo-demo.git
   git push -u origin main
   ```
3. Repo → Settings → Pages → Source: *Deploy from a branch*, branch `main`,
   folder `/ (root)`. The page appears at
   `https://<anon-account>.github.io/empdpo-demo/` within a minute.
4. Put that URL into `paper/main.tex` (`\thanks{Audio samples: \url{...}}`).

## Anonymity checklist (all verified at build time)
- No author, affiliation, e-mail, internal hostname, or repository path in
  `index.html` / `manifest.json` (grep for adobe|haonan|colligo|devpod|pluto|sensei → 0 hits).
- Commit with the anonymous account's identity (`git config user.name/email`
  inside this repo) so the commit metadata does not leak either.
- Do not add analytics or third-party embeds.
