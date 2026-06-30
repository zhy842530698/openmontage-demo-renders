# OpenMontage — Zero-Key Demo Renders

Three demo videos rendered end-to-end by **OpenMontage** with **no API keys required**,
using its built-in [Remotion](https://www.remotion.dev/) demo props and offline rendering.

> Generated from the demos that ship inside OpenMontage itself:
> `python3 render_demo.py` → three MP4s, ~25 s each, 1080p, H.264 + AAC.

---

## Videos

| # | File | Duration | Size | Description |
|---|------|---------:|-----:|-------------|
| 1 | `world-in-numbers.mp4` | ~23.0 s | 4.3 MB | Global-scale story with titles, stat cards and animated charts |
| 2 | `focusflow-pitch.mp4`  | ~22.5 s | 4.2 MB | Startup-style pitch deck built purely from Remotion components |
| 3 | `code-to-screen.mp4`   | ~25.0 s | 3.7 MB | Developer-workflow explainer with comparison + KPI cards |

All three are **1920×1080, 30 fps, H.264 High Profile, AAC stereo**, the standard
delivery format from OpenMontage's `Explainer` Remotion composition.

---

## How this was rendered (reproducible)

```bash
git clone --depth 1 https://github.com/calesthio/OpenMontage.git
cd OpenMontage

# Requirements: Python 3.10+, Node 18+, ffmpeg, npx
# (All free. Piper TTS and Remotion pulled automatically.)

PYTHON=python3.11 make setup      # or: make setup — uses python3 by default

# Render all three zero-key demos:
PYTHON=python3.11 python3.11 render_demo.py
# Or one at a time:
PYTHON=python3.11 python3.11 render_demo.py code-to-screen
```

Outputs land in `OpenMontage/projects/demos/renders/*.mp4` (this folder).

Total wall-clock on an Apple Silicon Mac: ~3 minutes (cold) for all three.

---

## What is OpenMontage?

OpenMontage is an open-source, agentic video-production system.
It turns your AI coding assistant into a full video production studio:
research → script → scene plan → assets → edit → compose, all driven by
a YAML pipeline manifest and Markdown stage-director skills.

- Repo: <https://github.com/calesthio/OpenMontage>
- 12 pipelines · 52 production tools · 500+ agent skills
- Free / open-source path: image-based video + local character animation,
  or real-footage documentary montages from Archive.org / NASA / Wikimedia
  / Pixabay / Pexels (no paid video models needed).

The three MP4s in this repo are the **zero-key** entry point — proving the
rendering pipeline works end-to-end before you connect any cloud providers.

---

## License of the rendered output

The composition scripts and React components used to render these videos
are MIT-licensed inside the OpenMontage repository. The rendered MP4s in
this repository are provided as-is for review.
