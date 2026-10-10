# MovieGraphs Scene Explorer

A browser view of a course project (COMP 790-158, UNC) by Vinir Rai and Anand Srinivasan:
can a small Transformer, trained from scratch on annotated social events, predict whether
one movie character will act on another in a scene, using only what happened earlier in
the film?

**Live page:** https://vinirrai.github.io/movie-graphs-explorer/ (once GitHub Pages is on)

## What it shows

- **Explore scenes.** All 9,791 held-out decisions (the last 30% of each of 51 films). For
  each pair in a scene: what actually happened, the chance of an interaction from four models
  (pair history; + relationship; + other characters' events, unordered; + the same events in
  order), and the history the models saw.
- **Is order working?** A positive control showing the ordered model can learn order when
  the label depends on it (ROC-AUC 0.97 vs 0.70), the leak we found in the unordered model,
  and why ordering the social context still does not help on the real task.
- **About the project.** The question, data, models and findings in plain English.
- **Team notes.** Encrypted (AES-GCM, key from PBKDF2-SHA256 of a passphrase) and decrypted
  in the browser; only the project team has the passphrase.

Predictions are precomputed (mean of 3 seeds); no model runs in the browser.

## Data

Built from the MovieGraphs annotations (Vicol et al., *MovieGraphs: Towards Understanding
Human-Centric Situations from Videos*, CVPR 2018). Character names, scene labels and
interaction verbs in `data.json` come from that dataset and remain under its authors' terms;
the MIT license here covers the page code only.

## Turning on hosting

Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
The site appears at the URL above within a minute or two.
