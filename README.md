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
- `NRV_SOP.docx` — Standard Operating Procedure for the NRV layer (master reference)
- `README.md` — this file
