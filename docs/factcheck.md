# Abundance System: Fact-Check (checked 2026-10-21)
Sources: the original design conversation behind this repo.

| # | Claim (thread) | Verdict | Correct figure / note | Source |
|---|---|---|---|---|
| 1 | Bamboo compressive strength 52–121 MPa | Verified (upper end generous) | Meta-analysis of 43 studies: avg 52 MPa, middle 50% 40.7–61.9, full range 18.6–134 | https://www.bamboo.org/_uploads/pdfs/JABSv29_Sanchez_20191007.pdf |
| 2 | Bamboo bending (MOR) 70–120 MPa, "~2x softwood" | Verified | Avg 120 MPa, middle 50% 79.6–149 | same |
| 3 | Fractal/hierarchical lattice + steel plates → +40–70% compressive, 80–190 MPa effective; +50–100% buckling | Unsupported | No tested data for this assembly. Lattice fill can help local buckling of hollow culms, but these % figures are invented and need lab tests | — |
| 4 | Utah "standard" build $220–280/sq ft | Off (partly) | 2026 Utah builder-grade $180–280/sq ft (HomeGuide); RSMeans SLC standard ~$136/sq ft; mid-range ~$184/sq ft | https://homeguide.com/costs/cost-to-build-a-house-in-utah ; https://housebuildcalc.com/state/utah/ |
| 5 | Bamboo/hempcrete home at $90–147/sq ft, 3–8 weeks build | Unsupported | Target only; the thread itself gives 4 versions ($90–118, $103–132, $112–147; 3–6 wk / 4–8 wk / 3–5 mo). Pick one and label it a goal. Hempcrete is infill, not structural | — |
| 6 | Mycelium-bacteria wall: tensile ~5–15 MPa, density 0.2–0.5 g/cm³ | Off | Mycelium composites: tensile 0.01–1.55 MPa, compressive 0.03–4.44 MPa, density 0.1–0.8 g/cm³. 5–15 MPa is ~10x too high for composites (only dense membranes hit 1–10 MPa) | https://pmc.ncbi.nlm.nih.gov/articles/PMC9460913/ ; https://link.springer.com/article/10.1007/s10853-026-13104-0 |
| 7 | Tesla Semi packs "~850–900 kWh", sub-packs ~94 kWh | Off | CARB filing: Long Range 822 kWh, Standard 548 kWh (4680 NCMA). Reported 3 packs (LR) / 2 (SR), i.e. ~274 kWh each, not 94 | https://electrek.co/2026/05/08/tesla-semi-battery-size-822-kwh-548-kwh-carb-official/ |
| 8 | Trailer L2 charger adds 13–16 mi/hr to Cybertruck | Off (low) | At 48 A/11.5 kW: ~26–31 mi/hr. 13–16 mi/hr matches ~24 A. But a ~20 kWh trailer battery only holds ~50–60 mi of Cybertruck range | https://evchargeright.com/cars/tesla-cybertruck-all-wheel-drive |
| 9 | Wi-Fi sensing: ESP32 CSI detects motion/breathing through walls, $10–30/sensor | Verified (with caveats) | Espressif esp-csi supports motion/presence and subtle motion incl. breathing; through-wall breathing research ~86% success. Reliability depends on placement/tuning; "via Starlink" means using Starlink router's Wi-Fi as the signal source, not a Starlink feature | https://github.com/espressif/esp-csi ; https://dl.acm.org/doi/fullHtml/10.1145/3377165 |
| 10 | Seestar S30 Pro as free rental add-on | Verified product | $699 new; fine as add-on, budget theft/damage | https://www.seestar.com/products/seestar-s30-pro |
| 11 | Victron NG LiFePO4 ~20 kWh, 1,400–2,200 W solar on trailer | Plausible, not checked per-model | Real product line; verify model specs before quoting | — |
| 12 | "Utah: 5–10% chance of traction" type odds | Unsupported | Guess, not data | — |

## Biggest corrections
1. Mycelium wall strength is ~10x overstated.
2. Tesla Semi is 822/548 kWh; 94 kWh sub-packs don't exist.
3. Cybertruck L2 is ~27–31 mi/hr at 48 A, but a 20 kWh trailer bank gives only ~50–60 mi total.
4. Lattice-bamboo strength gains and $/sq ft goal are unproven; say "target, to be tested".
