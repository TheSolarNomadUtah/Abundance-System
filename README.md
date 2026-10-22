# Abundance System

A simple, honest, open-source plan for cheap, resilient, self-sufficient housing, energy, and exploration. Everything here is released under **CC0 (public domain)**. Copy it, improve it, build it. No gatekeeping and no hype: real pieces, real tests, and numbers you can check.

> **Honesty rule:** figures marked **Goal** are targets we have not achieved or tested yet. Measured or sourced facts link to [docs/factcheck.md](docs/factcheck.md).

## Vision
Make a good life cheaper and sturdier: solar-powered, low-waste living that works off-grid, starting with things that can earn their keep today (trailer rentals, stargazing nights) and funding bigger experiments (housing, materials, sensing) step by step.

## The parts

| # | Part | What it is | Status |
|---|---|---|---|
| 1 | **Solar Nomad** | Solar-powered camping trailer rentals in northern Utah. The practical testbed and revenue engine | Launching |
| 2 | **Bamboo + biomimetic housing** | Bamboo frame + hempcrete infill, with nature-inspired (fractal/lattice) reinforcement ideas | Concept |
| 3 | **Cyber RV** | Trailer with solar + LiFePO4 battery that can also top up an EV while parked | Concept |
| 4 | **Mycelium materials** | Fungal composites for insulation and non-structural panels | Research |
| 5 | **Wi-Fi sensing** | Camera-free presence/motion/breathing sensing with low-cost ESP32-S3 boards | Prototyping |
| 6 | **Star Fleet (citizen-science telescopes)** | Smart telescopes on rentals/sites feeding real citizen-science projects | Idea |
| 7 | **Soul Resonance** | Browser game about sound, tones, and cymatics (Chladni patterns) | Prototype |
| 8 | **Stargazing site** | Low-key evening stargazing events in Cache Valley | Planning |
| 9 | **Lamplight Reading** | Calm early-reading app that coaches parents, not just kids | Idea |

### 1. Solar Nomad (Part 1)
Off-grid trailer rentals with solar, battery, and optional Starlink. Real customers, real feedback, and a place to field-test everything below.

### 2. Bamboo + biomimetic housing
- Bamboo is strong. Across 43 studies, average culm compressive strength is **~52 MPa** (middle 50%: 41–62) and bending strength (MOR) is **~120 MPa** (middle 50%: 80–149). Values vary a lot by species and moisture. [source](docs/factcheck.md)
- **Unproven:** strength gains from internal fractal/lattice reinforcement. No test data exists yet; we will test before claiming numbers.
- Hempcrete is **infill/insulation, not structure**.
- **Goal:** a modular home well below typical Utah build costs (2026 builder-grade is roughly $180–280/sq ft). No builder estimate exists yet, so we publish no per-sq-ft promise.

### 3. Cyber RV
- Trailer with ~1.4–2.2 kW solar and ~20 kWh LiFePO4 (design target).
- Reality check: a Cybertruck on a 48 A Level 2 charger adds **~26–31 mi/hr**, but a 20 kWh bank holds only **~50–60 miles** of Cybertruck range. Useful for emergencies; it won't replace grid charging.
- Tesla Semi packs are **822 kWh** (Long Range) and **548 kWh** (Standard), per the CARB filing. Reusing Semi packs is a far-future idea only.

### 4. Mycelium materials
- Real mycelium composites: compressive strength **~0.03–4.4 MPa**, tensile **~0.01–1.6 MPa**, density **~0.1–0.8 g/cm³**. Great insulation, **not** structural walls.
- Focus: insulation panels, packaging, and acoustic tiles.

### 5. Wi-Fi sensing
- ESP32 boards can read Wi-Fi channel state information (CSI) to detect motion and, under good conditions, breathing ([Espressif esp-csi](https://github.com/espressif/esp-csi)).
- This is **not new science**. Companies like Cognitive Systems, Origin AI, and Aerial already ship it in homes. Our open question: does it work in **small metal trailers that move**, on a microcontroller, with no cloud?
- **Privacy:** sensing inside a rental needs clear disclosure and guest consent (see Utah Code 76-12-302). The design uses coarse events only, no raw data leaving the device, and a physical off switch.
- Draft research pitch: [docs/nsf_pitch_wifi.md](docs/nsf_pitch_wifi.md)

### 6. Star Fleet: citizen-science telescopes
Smart telescopes (e.g., ZWO Seestar) at rentals and the stargazing site. The goal is to contribute observations to existing citizen-science programs rather than build a new network.

### 7. Soul Resonance
A playful browser experiment: pick tones (sine, singing bowl, ocean, OM…) and watch sand-like Chladni patterns form. Meant to be calming, not addictive.

### 8. Stargazing site
Simple evening events: loungers, cocoa, a big Dobsonian telescope, and a smart scope for photos. Fair prices, low effort. Ideas and add-ons: [docs/stargazing_ideas.md](docs/stargazing_ideas.md)

### 9. Lamplight Reading
A low-stimulation reading app. Short nightly sessions where the app coaches a parent through phonics and decodable stories. No coins, streaks, or autoplay. Data stays on the device.

## Roadmap
See [docs/ROADMAP.md](docs/ROADMAP.md).

## Docs
- [docs/factcheck.md](docs/factcheck.md): claims checked against sources (Verified / Off / Unsupported)
- [docs/grants.md](docs/grants.md): grants and programs that may fit
- [docs/nsf_pitch_wifi.md](docs/nsf_pitch_wifi.md): draft NSF SBIR Project Pitch (not submitted)
- [docs/stargazing_ideas.md](docs/stargazing_ideas.md): low-effort stargazing add-ons
- [docs/ROADMAP.md](docs/ROADMAP.md)

## Contributing
Ideas, test data, and corrections are welcome. Open an issue or PR. Please cite sources for numbers.

## License
[CC0 1.0 Universal](LICENSE): public domain dedication, matching the project's original "Creative Commons Zero" statement.
