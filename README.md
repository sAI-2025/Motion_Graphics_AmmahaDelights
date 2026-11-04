# Motion_Graphics_AmmahaDelights

Motion-graphics launch video for **AmAha Delights** — premium sweet treats
(Softy, Belgian Waffles, Coconut Delights) and smart vending solutions,
Hyderabad, India.

A 20-second 16:9 brand film: Hook → Signature Treats → Smart Vending → Outro wordmark.

## Deliverable

- `brag-output/brag.mp4` — final render (1920×1080, 30 fps, H.264 + AAC, ~8 MB)

## Source

- `brag-output/composition/index.html` — Hyperframes **host** (sub-composition
  slots + audio clips + audio-reactive host timeline)
- `brag-output/composition/compositions/scene-1.html` — HOOK · `0–4.0s`
- `brag-output/composition/compositions/scene-2.html` — SIGNATURE TREATS · `4.0–10.0s`
- `brag-output/composition/compositions/scene-3.html` — SMART VENDING · `10.0–15.5s`
- `brag-output/composition/compositions/scene-4.html` — OUTRO / WORDMARK · `15.5–20.0s`
- `brag-output/composition/index.motion.json` — motion-intent assertions consumed by `hyperframes check`
- `brag-output/script.md` — on-screen copy & grounding ledger (all lines verbatim
  from the AmAha Delights website) and the full timing map
- `brag-output/composition-brief.md` — Hyperframes creative brief (tone `polished`,
  storyboard, audio plan, SFX selections)
- `brag-output/brag-plan.md` — creative contract / story spine

## Process

Built with the `/brag` workflow on top of Hyperframes (`npx hyperframes check` is
the gate): **0 errors** — layout, motion, runtime, and contrast all pass
(23/23 WCAG AA). The audio-reactive glow behind the hero/vending/wordmark layers is
driven per frame from pre-extracted RMS + 16-band FFT data (`assets/audio-data.json`).
Music: `happy-beats-business-moves-vol-12` (~110 BPM), fade-in/out via volume automation;
three strong cue locks (10.93s, 13.11s, 17.47s) with all reveals entering on the beat
grid. SFX chosen for motion-matched moments.

Reproduce: `cd brag-output/composition && npx hyperframes check && npx hyperframes render --quality looks --output ../brag.mp4`

## Skills vendored in repo

The agent skills used to build this video are vendored under `.agents/skills/` so the
project is self-contained: `brag` (the launch-video workflow, from `latent-spaces/brag`),
`hyperframes`, `hyperframes-core`, `hyperframes-animation`, `hyperframes-creative`,
`hyperframes-cli`, `hyperframes-keyframes`, `hyperframes-audio`, `hyperframes-studio`,
and `media-use` (HyperFrames domain skills, installed from the HyperFrames registry).

Note: `.agents/skills/brag/assets/music/*.mp3` (the ENDE dot APP "Happy Beats / Business
Moves" packs bundled with the skill) are deliberately excluded — their license terms are
not documented for redistribution. The single track used (`happy-beats-business-moves-vol-12`)
is included in `brag-output/composition/assets/music/`.

To refresh the domain skills to latest: `npx hyperframes@latest skills update`

Tooling excluded on purpose (not part of the product): `.agents/` (installed brag skill),
`brag-output/composition/.hyperframes/` (build artifacts), `brag-output/verify/` (check evidence).
