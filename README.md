# Strategic Value

Value engineering tool for RFID / asset visibility engagements. Single-file HTML app (`index.html`) — open in any browser, no build.

**Live:** https://alt-meridian-josh.github.io/Strategic-Value/

## What this is

A discovery-to-ROI workflow:

1. **Engagement Setup** — company, customer, sites (and **Save / Load** a whole analysis as JSON)
2. **Industry & Value Levers** — pick verticals; scenario library filters automatically
3. **Discovery Inputs** — customer-specific values per scenario (defaults are conservative benchmarks)
4. **Cost Model** — sliders auto-calc a BOM; every line item editable; **contingency rate is editable** (default 7%)
5. **ROI & Value Case** — headline NPV / IRR / payback **plus the NRV normalization layer** and the **Finance Credit** layer
6. **Full Analysis** — printable investment appraisal + branded deck export

## Saved analyses & worked examples

A whole analysis is just data — there is **no hard-coded sample baked into the app**.

- **💾 Save analysis** (Step 1) downloads the current engagement as a portable `.json` file.
- **📂 Load analysis** reads one back via the file picker (works from `file://` too).
- **📦 Export standalone tool** packages the **entire app + the current analysis** into one self-contained `.html` file. Hand it to a customer or rep: they open it straight from local disk, it runs fully offline, makes no network calls on open, and every number stays editable. (The export inlines the chart libraries so nothing phones home; *PPTX export* still pulls its generator from a CDN, so that one action needs internet. The file is not encrypted or locked — it's meant to be edited.)
- Bundled example engagements live as real files under [`examples/`](examples/) and load through the exact same path.

**Worked example — Macy's RFID + Workcloud** (`examples/macys.json`, from the Zebra Strategic Value one-pager): 441 stores, $13.044B revenue, all 8 quantified value levers mapped 1:1, 5 strategic enablers, $44.1M Yr-0 / $11.0M-yr cost model, Finance Credit at 40%.

- Hosted: open **[`?example=macys`](https://alt-meridian-josh.github.io/Strategic-Value/?example=macys)** to auto-load it.
- Offline (`file://`): the URL shortcut can't `fetch`, so use **Load analysis** and pick `examples/macys.json`.

## Finance Credit (Step-5 toolbar)

The fraction of a lever's modeled benefit a finance team will underwrite. Revenue-recovery benefit types (revenue / working-capital / soft) are credited below 100% — **default 40%** — while hard labor/cost benefits are credited at 100%. **On by default;** toggle and rate are editable inline.

Rationale (shown in-app): benefit estimates are risk-adjusted downward by likelihood-of-realization and trackability (Forrester *Total Economic Impact* methodology), and RFID sales uplift — real at 1.5–5.5% — is the hardest benefit to attribute (Beck/ECR, *Measuring the Impact of RFID in Retailing*, 2018). **The 40% rate is a deliberately conservative assumption, not a published constant — adjust it to your finance team's standard.**

## NRV — Net Realization Value (built into the ROI math)

NRV is not a separate section; it is the math layer Step 5 already runs on. Every headline number — Peak Annual Benefit, Payback, 5-yr NPV, 5-yr Net ROI, MIRR, BCR — already prices in the three forces acting on every technology dollar:

1. **Adoption friction** — 5-year ramp profile by delivery mechanism (Hardware / Software / Human Behavior / Compliance), including post-peak decay in Y4–Y5
2. **Market commoditization** — accessibility tier (Commodity / Configured / Infrastructure) compresses competitive alpha as the technology becomes easier to replicate
3. **Covariance / double-counting** — per-driver haircut h on shared labor pools or asset bases

It also adds:

- **Decay_Avoided** — status-quo grows at g = 3.5%/yr by default (BLS ECI + McKinsey)
- **WACC sensitivity** at 8 / base / 12% — shown beneath the financial model
- **MIRR**, not IRR — reinvestment at WACC, no multiple-IRR artifacts (IRR shown for reference)
- **BCR cap at 10x** — anything higher is flagged for mandatory review before export

The decay-discipline toolbar at the top of Step 5 exposes the global knobs (WACC, baseline g, finance rate, Decay_Avoided on/off, NRV layer on/off). Per-scenario profile / accessibility tier / haircut h live inline in the detail table for each scenario.

Toggle "NRV layer: Off" in the toolbar to fall back to the old 3-yr ramp math for an apples-to-apples comparison.

Full methodology and citations: see `NRV_SOP.docx`.

## Files

- `index.html` — the app (everything is inline; no build step)
- `examples/` — bundled saved engagements (e.g. `macys.json`); load via **Load analysis** or `?example=<name>`
- `.github/workflows/pages.yml` — deploys the app to GitHub Pages on push to the default branch
- `NRV_SOP.docx` — Standard Operating Procedure for the NRV layer (master reference)
- `README.md` — this file
