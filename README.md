# Strategic Value

Value engineering tool for RFID / asset visibility engagements. Single-file HTML app (`index.html`) — open in any browser, no build.

## What this is

A discovery-to-ROI workflow:

1. **Engagement Setup** — company, customer, sites
2. **Industry & Value Levers** — pick verticals; scenario library filters automatically
3. **Discovery Inputs** — customer-specific values per scenario (defaults are conservative benchmarks)
4. **Cost Model** — sliders auto-calc a BOM; every line item editable
5. **ROI & Value Case** — headline NPV / IRR / payback **plus the NRV normalization layer**
6. **Full Analysis** — printable investment appraisal + branded deck export

## NRV — Net Realization Value (normalized ROI)

The headline numbers in Step 5 use a 3-year ramp. They answer the question "what is the steady-state value of the deal?" — fine for early discovery, but they don't survive a CFO challenge because they don't price in the three forces acting on every technology dollar:

1. **Adoption friction** — no solution delivers 100% in Year 1
2. **Market commoditization** — alpha compresses as competitors reach parity
3. **Covariance / double-counting** — drivers that share a labor pool

The **NRV layer**, surfaced as a card in Step 5, re-runs the model with:

- **5-year ramp profiles** (Hardware, Software, Human Behavior, Compliance) — including post-peak decay in Years 4–5
- **Accessibility tier** (Commodity / Configured / Infrastructure) — alpha compression by tier
- **Covariance haircut h** per driver — default 0, you justify the floor
- **Decay_Avoided** — status-quo grows at g = 3.5%/yr by default (BLS ECI + McKinsey)
- **WACC sensitivity** at 8 / base / 12%
- **MIRR**, not IRR — reinvestment at WACC, no multiple-IRR artifacts
- **BCR cap at 10x** — anything higher is flagged for review before export

The "Normalization Effect" comparison cell shows how much the headline NPV moves when the decay discipline is applied. That delta is the conservatism the CFO will demand anyway; better to surface it ourselves.

Full methodology and citations: see `NRV_SOP.docx`.

## Files

- `index.html` — the app (everything is inline; no build step)
- `NRV_SOP.docx` — Standard Operating Procedure for the NRV layer (master reference)
- `README.md` — this file
