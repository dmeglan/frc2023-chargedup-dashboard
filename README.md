# FRC 2023 CHARGED UP — Robot Study Dashboard

An interactive catalog of **45 teams** that publicly released downloadable CAD for the 2023
CHARGED UP season, with **10 curated ★ study picks** carrying full subsystem deep-dives mined
from each team's Chief Delphi reveal/release thread.

## Files

| File | What it is |
|---|---|
| `FRC2023_ChargedUp_Robot_Study_Dashboard.html` | The interactive dashboard (desktop table + mobile cards; search / archetype / CAD / confidence filters). |
| `FRC2023_ChargedUp_TopTeams_DeepDive.html` / `.pdf` | Printable deep-dive of the 10 study picks (subsystem cards + lessons). |
| `index.html` / `deep-dive.html` / `deep-dive.pdf` | The same outputs prepped for GitHub Pages, with the dated "Updated…" banner + "What's changed" panel. |
| `pipeline/` | Build pipeline: `config.py`, `codex_data.json` (45 teams), `deepdive_extra.py` (deep profiles + picks), build scripts, `backfill_epa.py`, and discovery inputs (`_cad_links.txt`, `_names.txt`). |

## Notes

- **EPA / rank are pending a Statbotics API outage** (HTTP 500 at build time) and will be
  backfilled by the daily scheduled task once the API recovers — the table is sorted by team
  number until then.
- Every team here released **downloadable CAD**, so all are CAD = Yes / High confidence.
- Highlights: 971 deliberately kept tank drive; 6328 (AdvantageKit); 1114 Simbot Scizor; 695's
  swerve-CAD tutorial; 3005's praised end effector; 118 (Everybot authors); 1706's grid-registering
  octagonal frame; 2767's vision-align status light.
- Discovery: Spectrum 3847 CAD Collection (2023). Mechanism detail: Chief Delphi.

## Rebuild
```
cd pipeline
python3 build_dashboard.py && python3 build_deepdive_html.py && python3 build_deepdive_pdf.py && python3 apply_changelog.py
```
See `PUBLISH_SETUP.md` for the one-time GitHub Pages setup.
