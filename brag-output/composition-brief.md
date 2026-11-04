# Hyperframes Composition Brief: AmAha Delights

## Objective
Create a short, warm, appetite-first launch/brand film for AmAha Delights — a premium
sweet-treats brand (Softy, Belgian Waffles, Coconut Delights) that also sells smart
vending machines.

## Output
- Composition directory: `brag-output/composition/`
- Rendered video: `brag-output/brag.mp4`
- Format: landscape — 1920x1080
- Duration: 20 seconds

## Source Material
- Project root: the AmAha Delights marketing site (https://ammahadelights.app/)
- Primary sources read: site HTML (home / products / vending-machines / about), the
  compiled stylesheet `static/styles/index.css` (palette + fonts), site imagery.
- Product name: AmAha Delights
- Tagline / strongest claim: "Delight in Every Bite"
- Key UI or visual moment to recreate: the three signature product cards with their
  "Popular" / "New" badges, and a vending-machine feature panel built from the site's
  real machine copy.
- Copy that appears on screen (all grounded):
  - "Premium Sweet Treats"
  - "Delight in Every Bite"
  - "Experience the perfect blend of traditional flavors and modern innovation."
  - "Our Signature Delights"
  - "Handcrafted with the finest ingredients, each treat is a celebration of taste"
  - Cards: "Popular · Premium Softy · Smooth, creamy soft-serve ice cream in delightful flavors."
  - "New · Belgian Waffles · Crispy golden waffles topped with fresh fruits, cream, and your favorite toppings."
  - "Coconut Delights · Traditional Kobbari Munju made with tender coconut."
  - "Smart Solutions" / "Vending Machines"
  - "State-of-the-art vending machines — serve your customers 24/7."
  - Softy Vending Machine features: "Automated soft-serve dispensing" / "Multiple flavor options" / "Touchscreen interface"
  - "24/7 Operation"
  - "+91 630 012 3897 · Swaraj Nagar, Hyderabad, India"
  - "Get a Quote"

## Creative Direction
- Tone preset: `polished`
- Creative direction: warm, appetite-driven premium dessert brand film — sun-lit,
  craving-first, confident but joyful.
- Interpretation: fewer scenes, longer holds, soft crossfades, restrained motion; let
  the product photography carry the frame; no jokes, no stat-bragging, no chaos.
- Angle: the brand that puts softy in your hand also machines it 24/7 — treats first,
  machines as the way the delight scales.
- Hook: full-bleed hero dessert shot + "Delight in Every Bite" landing big.
- Outro / punchline: the wordmark assembles over the tagline and real contact line.
- Avoid:
  - Generic SaaS language
  - Abstract filler visuals
  - Unrelated visual redesign
  - Stock/abstract backgrounds — use the real product photography

## Visual Identity
- Background: `#FCFBF7` (hsl 40 50% 98%) warm cream (light canvas — food)
- Text: `#533C2D` (hsl 24 30% 25%) warm ink; muted `#9C8A7C`
- Accent (warm): `linear-gradient(135deg, #F5CB4C 0%, #C17E5C 100%)`
- Accent (cool): `#98D2E2` (hsl 193 56% 74%)
- Display font: Playfair Display (900 / 700)
- Body font: Poppins (400 / 700 / 900)
- Visual references from the project: `hero-desserts.jpg`, `sunday.png`, `waffle.png`,
  `coconut-product.png`, `softy-machine.jpg`; the "Popular"/"New" badges; the
  gold→caramel warm gradient; glass pill / rounded-card language.

## Storyboard
Use the storyboard in `brag-output/brag-plan.md` as the creative contract.

Scene summary:
1. Hook: "Delight in Every Bite" — 4.0s — hero dessert photo, eyebrow pill, gradient headline, real subhead
2. Signature Treats — 6.0s — three real product cards fan in one by one (badges + real copy)
3. Smart Vending — 5.5s — machine photo panel + 3 machine rows ticking on; "24/7"
4. Outro / Wordmark — 4.5s — "AmAha Delights" + tagline + Hyderabad contact + CTA

## Audio
- Audio role: warm professional bed with a few tasteful, motion-matched accents
- Audio arc: fade in over the hook; steady through the two highlight scenes; fade out
  under the final wordmark hold
- Music: `assets/music/happy-beats-business-moves-vol-12-by-ende-dot-app.mp3`
- Music treatment: volume ~0.32; fade in 0→0.8s; fade out 18.3→19.9s (use the audio
  automation volume lane)
- Music cue guidance: bundled preset
  (`<skill-dir>/assets/music/cues/happy-beats-business-moves-vol-12-by-ende-dot-app.music-cues.json`,
  tempo ~109.96 BPM). Optional hints: logo payoff ~17.47s; machine rows ~10.93s and
  ~13.11s; treat cards snap to nearby beats.
- Audio-reactive treatment: subtle; music RMS lifts a warm glow behind the hero headline
  and gives the vending panel a soft presence. No waveform/equalizer visuals.
- Audio-coupled moments:
  - Scene 1 eyebrow — soft drop; headline — soft reveal hit
  - Scene 2 treat cards — card-slide per card
  - Scene 3 panel — warm bell; rows — soft clicks
  - Scene 4 wordmark — resonant warm bell payoff
- SFX selection guidance: sparse, low/medium HF risk; card sounds for cards, clicks for
  rows, one bell for the logo (see `<skill-dir>/assets/sfx/sfx-analysis.md`).
- Exact SFX choice: Hyperframes chose filenames/timestamps/volume to match the animation.
- Audio files: music + selected SFX copied into `brag-output/composition/assets/`

## Hyperframes Instructions
Loaded `hyperframes-core`, `hyperframes-animation`, `hyperframes-creative`,
`hyperframes-keyframes`, `hyperframes-cli`. `/brag` is its own workflow — do not enter
the `hyperframes` entry-point intent interview or route into its generic promo workflow.
Prefer native Hyperframes conventions.

Requirements:
- Show real product imagery and the site's real copy throughout.
- Keep all text readable in the final render.
- Keep the video within 15–25 seconds (20s).
- Include the planned music/SFX layer.
- Treat music cue metadata as optional timing hints.
- Run `npx hyperframes check` before render — brag's single gate.
- Keep creation and rendering local.

Lint posture: the four scenes are standalone sub-compositions mounted from the root
(`compositions/scene-1.html` … `scene-4.html`); the root is a pure host of sub-composition
slots + audio + overlays. `hyperframes lint` reports 0 errors / 0 warnings and
`hyperframes check` passes (Layout 0 issues, Motion 0, WCAG AA 23/23). The one remaining
`line_unread` craft warning (17-word hook panel held 3.3s in a 4.0s hook) is pacing, not a defect.
