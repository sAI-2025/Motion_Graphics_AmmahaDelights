# AmAha Delights — Brag Video Script & Content Sheet

Final cut: `brag-output/brag.mp4` · 1920×1080 landscape · 20.0s · 30fps · 4 scenes

Source layout: `composition/index.html` is a pure host (sub-composition slots + audio).
Each scene is a standalone sub-composition mounted from the host:
`compositions/scene-1.html` (Hook), `compositions/scene-2.html` (Signature Treats),
`compositions/scene-3.html` (Smart Vending), `compositions/scene-4.html` (Outro).
The audio-reactive RMS/bass glow layer is driven by the host timeline (all 600 frames);
per-scene entrance, hold and dip timings live inside each sub-composition's own timeline
each scene's timeline uses scene-local seconds (scene-local = absolute − scene offset).

Every line that appears on screen is quoted from the AmAha Delights site
(home hero, "Our Signature Delights" cards, `/vending-machines`, footer contact).
Nothing is asserted about the product that the site doesn't say.

---

## SCENE 1 — HOOK · 0.0 – 4.0s

| t | on screen | sound |
| --- | --- | --- |
| 0.00 | dessert hero photo opens full-frame, panning gently out of a 1.14 zoom | music fades in 0 → 0.8s |
| 0.10 – 1.00 | cream glass panel rises in; eyebrow rows up at 0.54s | `interface/drop_001` at 0.28s |
| 0.78 | headline lands | `impact/impactSoft_heavy_000` (0.51s) |
| 1.04 | subline settles | — |
| 1.04 – 4.0 | full hook holds (panel stays on screen to the cut) | — |

**Eyebrow (pill):** `✦ Premium Sweet Treats`

**Headline (Playfair Display 900, two stacked lines):**

- `Delight in` — deep caramel
- `Every Bite` — warm ink

**Subhead (verbatim):**

> Experience the perfect blend of traditional flavors and modern innovation.

**Reactive:** a warm gold glow behind the panel; opacity/scale driven per-frame
from the music's RMS + bass band (source: `assets/audio-data.json`).

---

## SCENE 2 — SIGNATURE TREATS · 4.0 – 10.0s

| t | on screen | sound |
| --- | --- | --- |
| 4.00 | warm/pink wash cuts in | music |
| 4.10 – 4.84 | heading + rule + subline rise | — |
| 4.39 // beat | card 1 slides up | `casino/card-slide-1` (0.60s) |
| 5.34 // beat | card 2 slides up | `casino/card-slide-3` (0.60s) |
| 6.56 // beat | card 3 slides up | `casino/card-slide-8` (0.67s) |
| 7.41 – 9.3 | full three-card row holds | — |
| 9.3 – 9.65 | text dips out; cut on cream | music |

**Heading:** `Our Signature Delights` — with `Delights` in deep caramel
**Subline:** `Handcrafted with the finest ingredients, each treat is a celebration of taste`

**Cards (site badges + real titles + real copy):**

| badge | title | copy | image |
| --- | --- | --- | --- |
| `Popular` | Premium Softy | Smooth, creamy soft-serve ice cream in delightful flavors. | `assets/images/sunday.png` |
| `New` | Belgian Waffles | Crispy golden waffles topped with fresh fruits, cream, and your favorite toppings. | `assets/images/waffle.png` |
| — | Coconut Delights | Traditional Kobbari Munju made with tender coconut. | `assets/images/coconut-product.webp` |

---

## SCENE 3 — SMART VENDING · 10.0 – 15.5s

| t | on screen | sound |
| --- | --- | --- |
| 10.00 | cool/pink wash cuts in | music |
| 10.1 | machine photo panel slides in from the left | `interface/switch_001` (0.62s) |
| 10.36 – 11.2 | eyebrow + heading + subline | — |
| 10.93 // strong cue | row 1 | `keyboard/keypress-001` (0.25s) |
| 12.02 // beat grid | row 2 | `keyboard/keypress-002` (0.25s) |
| 13.11 // strong cue | row 3 | `keyboard/keypress-003` (0.25s) |
| 13.71 – 14.8 | full feature list holds | — |
| 14.8 – 15.1 | content dips out; cut on cream | music |

**Photo panel:** `assets/images/softy-machine.jpg` + gold pill `24/7 Operation`
**Eyebrow:** `Smart Solutions`
**Heading:** `Vending Machines`
**Subline:** `State-of-the-art vending machines — serve your customers 24/7.`

**Feature rows (Softy Vending Machine features, verbatim):**

- ✓ Automated soft-serve dispensing
- ✓ Multiple flavor options
- ✓ Touchscreen interface

---

## SCENE 4 — OUTRO / WORDMARK · 15.5 – 20.0s

| t | on screen | sound |
| --- | --- | --- |
| 15.5 | warm glow cuts in | music |
| 15.8 – 17.2 | eyebrow → wordmark → tagline → rule → contact | — |
| 17.47 // strong cue | `Get a Quote` lands | `impact/impactBell_heavy_000` (1.48s, rings over the bed) |
| 18.3 – 19.0 | CTA pulses once | music fades out 18.3 → 19.9s |
| 19.0 – 20.0 | full lock holds to end | decay |

**Eyebrow:** `Premium Sweet Treats`
**Wordmark (Playfair Display 900):** `AmAha Delights`
**Tagline:** `Delight in Every Bite`
**Contact:** `+91 630 012 3897 · Swaraj Nagar, Hyderabad, India`
**CTA:** `Get a Quote`

---

## Audio architecture

- **Bed:** `assets/music/happy-beats-business-moves-vol-12-by-ende-dot-app.mp3`
  (~110 BPM), volume 0.34, 600-frame RMS+band data extracted per frame.
- **Automation:** volume lane `0 → 0.34` over 0.8s, `0.34 → 0` over 18.3–19.9s.
- **Beat locks (3 strong cues, brag convention):** 10.93s (row 1), 13.11s (row 3),
  17.47s (CTA/logo payoff). Beat grid drives the three treat cards (4.39 / 5.34 / 6.56s).
- **Reactivity:** RMS lifts a warm glow behind the hero panel, a soft pink bloom
  behind the vending panel, and a warm halo behind the wordmark. No equalizers,
  waveforms, or particle bursts.

## Copy grounding ledger

| On-screen line | Source |
| --- | --- |
| "Premium Sweet Treats" | home hero eyebrow |
| "Delight in / Every Bite" | home hero headline / site `<title>` |
| "Experience the perfect blend of traditional flavors and modern innovation." | home hero subhead (verbatim first sentence) |
| "Our Signature Delights" | home section heading |
| "Handcrafted with the finest ingredients…" | home section subline (verbatim) |
| Cards Popular / Premium Softy / Belgian Waffles / Coconut Delights + copy | home "Our Signature Delights" cards (verbatim, trimmed where marked) |
| "Smart Solutions", "Vending Machines" | `/vending-machines` kicker + h2 |
| "State-of-the-art vending machines — serve your customers 24/7." | `/vending-machines` intro (verbatim phrases, reassembled) |
| 3 feature rows | Softy Vending Machine feature list (verbatim, first three) |
| "24/7 Operation" | `/vending-machines` "Why Choose Our Vending Machines?" heading |
| "+91 630 012 3897 · Swaraj Nagar, Hyderabad, India" | site footer contact |
| "Get a Quote" | site nav / section CTA |
