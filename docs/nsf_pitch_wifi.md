# NSF SBIR Phase I Project Pitch (DRAFT, not submitted): Wi-Fi sensing for off-grid mobile dwellings
> Public draft. Not submitted to NSF. Bracketed [CONFIRM] items are placeholders.
Format verified 2026-10-21 at https://seedfund.nsf.gov/apply/project-pitch-information/ (4 sections; limits 3500/3500/1750/1750 chars). Submit via seedfund.nsf.gov; invitation needed before the full proposal. Items in [CONFIRM] need the founder's input.

## 1. Technology Innovation (limit 3500) — 2440 chars
Solar Nomad LLC proposes research into a self-calibrating, on-device Wi-Fi sensing node for off-grid, metal-walled mobile and small dwellings (travel trailers, vans, tiny homes, cabins) that detects presence, motion, falls and breathing without cameras, microphones or cloud processing, and runs on a few hundred milliwatts from solar.

Origins: the founder rents solar-powered camping trailers in rural Utah and is designing low-cost off-grid housing (the open-source "Abundance System"). Renters and owners want to know if a unit is occupied, entered, or if someone inside is in distress, but cameras inside rentals are unacceptable and often illegal, and cellular/cloud links are intermittent off-grid.

Wi-Fi channel state information (CSI) sensing is well established in research and in commercial home products (Cognitive Systems, Origin AI, Aerial). It is NOT our novelty. Existing systems assume (1) a fixed house with stable multipath, (2) mains power and an always-on router or cloud back end, and (3) per-site training or a calibration period. All three fail in our setting: an aluminum or steel trailer shell is a highly reflective, near-enclosed cavity whose multipath changes every time the unit is moved, leveled, or its slide-outs and awnings shift; power budgets are tight; and there is often no internet.

The unproven, high-risk innovation is a sensing pipeline that (a) automatically re-learns an "empty" baseline after relocation with no user labeling, using unsupervised change detection plus a learned prior across many enclosures; (b) separates human micro-motion (breathing at 0.1-0.5 Hz) from vehicle sway, wind, HVAC fans and pump vibration in a small reflective cavity; and (c) runs entirely on a sub-$15 ESP32-S3 class microcontroller with duty-cycling to stay within an off-grid energy budget, emitting only coarse events (occupied / empty / motion / possible fall / no-breathing alert), never raw CSI or images.

Whether reliable breathing and fall detection is achievable in a moving metal enclosure, on a microcontroller, without per-site training, is an open research question. Published CSI breathing results come mostly from rooms with lab tuning and PC-class processing. If successful, the result is a privacy-preserving occupancy and safety sensor for RV-owning households, rural cabins and tiny homes, and for disaster-relief and emergency shelters, at a fraction of today's cost and with no cameras.

## 2. Technical Objectives and Challenges (limit 3500) — 2766 chars
Phase I objectives (6-12 months):

O1. Characterize CSI in mobile metal enclosures. Instrument 3-5 different trailers/vans (aluminum, steel, fiberglass) with ESP32-S3 transmit/receive pairs (Espressif esp-csi). Record CSI under empty, occupied, sleeping, walking, fall-simulation, wind, rain, HVAC and towing/re-parking conditions, with ground truth from a chest-strap respiration belt and short-term consented video kept only for labeling. Challenge: no public dataset exists for this setting. Managed by building and releasing an open dataset.

O2. Relocation-robust baseline. Develop and test unsupervised methods (e.g., subspace tracking, autoencoder reconstruction error, Doppler/phase-difference features) that re-establish an empty-cabin baseline within minutes after a move with no labels. Success metric: presence detection F1 >= 0.95 within 15 minutes after relocation, across enclosures not seen in training.

O3. Micro-motion separation. Separate breathing (0.1-0.5 Hz) and falls from structural sway and mechanical vibration. Approaches: multi-link antenna diversity, phase sanitization across subcarriers, and a small learned classifier. Metrics: breathing-rate error <= 2 breaths/min for a still occupant in >= 85% of windows; fall detection sensitivity >= 90% at <= 1 false alarm per unit-week. Risk: sway and the occupant's own breathing occupy overlapping bands; mitigation is using an IMU on the node as a reference channel for vehicle motion.

O4. Edge feasibility. Quantize models to run on the ESP32-S3 (512 KB SRAM, vector instructions) with an average power target <= 0.3 W including radio, so a 10 W panel and small battery sustain it. Metric: on-device latency < 2 s per decision.

O5. Privacy and legal design. Utah Code 76-12-302 makes it a misdemeanor to install or use a device in a private place to observe or record events without the consent of the persons entitled to privacy there. We will design for explicit renter disclosure and consent, an on-device physical "sensing off" switch, and output limited to coarse events stored locally, and we will document compliance review with counsel.

Why this is R&D, not engineering: the core uncertainty is whether physically meaningful human signals can be recovered reliably from a reflective, moving enclosure using only unsupervised adaptation on microcontroller hardware. Existing products avoid this setting. Phase I tells us whether the target metrics are reachable; failure modes (e.g., sway dominating breathing bands) are informative and will be published.

Path to commercial viability: if O2-O4 succeed, Phase II would harden firmware, run a 50-unit field pilot in Solar Nomad rental trailers and partner campgrounds, and pursue integration with RV power/monitoring platforms.

## 3. Market Opportunity (limit 1750) — 1238 chars
Near-term customers: (1) RV and trailer rental operators and peer-to-peer RV hosts, who need to know whether units are occupied, entered or abandoned without cameras; (2) RV owners and full-timers, including older travelers who want fall and "no movement" alerts without wearables; (3) operators of off-grid cabins, tiny-home communities and emergency/disaster shelters. Pain points: cameras inside sleeping spaces are unacceptable and legally risky; wearables are not worn; existing smart-home sensing assumes home broadband, a compatible router and cloud service.

Competition: Cognitive Systems (Wi-Fi Motion, reported in 20M+ homes via ISP routers), Origin AI (acquired by ADT in 2026) and Aerial license CSI sensing to router makers and ISPs for fixed homes. IEEE 802.11bf (2025) standardizes sensing measurement but not detection algorithms. mmWave radar sensors (e.g., 60 GHz presence modules) also compete, but need line of sight per zone. None target off-grid, relocating, metal-enclosure use with fully local processing. Our wedge: a sub-$30 retrofit node that works with no internet and no special router, sold directly and through RV rental/campground channels, with a later licensing path to RV OEMs and power-system makers.

## 4. Company and Team (limit 1750) — 915 chars
Solar Nomad LLC is a Utah small business, recently formed, launching solar-powered camping trailer rentals in northern Utah. It provides the real test fleet and customer access for this project. The founder leads product, field testing and commercialization, and authored the open-source Abundance System for low-cost resilient off-grid living. He is starting ESP32-S3 CSI prototyping with Espressif's open esp-csi tools.

Gaps and plan: the team currently lacks a PhD-level wireless signal processing lead. Before the full proposal we will recruit a technical lead or academic subaward partner in RF sensing/embedded ML (e.g., from Utah State University or the University of Utah, both with electrical and computer engineering programs) and a part-time embedded firmware engineer. We will also engage privacy counsel for the Utah consent and disclosure design. [CONFIRM: founder time commitment.]

## Honesty notes / sources
- Novelty claim is the off-grid, relocating metal-enclosure setting + label-free recalibration + microcontroller-only processing. CSI motion/breathing sensing itself is prior art (esp-csi: https://github.com/espressif/esp-csi ; CSI vital signs: https://dl.acm.org/doi/fullHtml/10.1145/3377165).
- Competitors: Cognitive Systems 20M+ homes (https://www.cognitivesystems.com/from-wifi-connectivity-to-spatial-intelligence); Origin AI acquired by ADT early 2026 (https://wifinowglobal.com/resources/wi-fi-sensing-technology-guide-part-3-from-proprietary-innovation-to-industry-standard/); Aerial (https://aerial.ai/resources-blog/wifi-motion-intelligence-the-fundamentals); IEEE 802.11bf-2025 (https://standards.ieee.org/ieee/802.11bf/11574/).
- Utah Code 76-12-302 (https://le.utah.gov/xcode/Title76/Chapter12/C76-12-S302_2025050720250507.pdf) does not name Wi-Fi sensing; it bans installing/using a device in a private place to observe or record events without consent of those entitled to privacy (class B misdemeanor). Disclosure and consent are the safe design. Not legal advice.
- Metric targets (F1 0.95, ≤2 bpm, 0.3 W) are proposed goals, not results.
- Biggest weakness for reviewers: the team. Adding a USU/U of U RF partner (possibly as STTR) strengthens the pitch a lot.
