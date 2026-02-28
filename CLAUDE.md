# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file static landing page for **YapYap** — a Mac voice-to-text app that runs 100% on-device using WhisperKit (STT) and MLX-based LLMs (Gemma, Qwen, Llama) for text cleanup. The entire site lives in `yapyap-landing.html`.

## Architecture

Everything is self-contained in one HTML file:
- **Inline CSS** with CSS custom properties (`--logo`, `--heading`, `--body`, `--hand` fonts; `--bg`, `--lavender`, `--warm`, `--mint`, `--zzz`, `--blush`, `--red` colors)
- **Inline SVG** for all creature illustrations (no external image assets)
- **Vanilla JS** (minimal — only FAQ accordion toggle via `onclick` attributes)
- **Google Fonts** loaded via CDN link tag (Baloo 2, Nunito, Quicksand, Caveat)

## Page Sections (in order)

1. `nav` — Fixed top bar with logo + links
2. `#download / .hero` — Hero with SVG creature, CTA, 3-step strip (`#how`)
3. `.aware` — Context-aware app detection showcase (6 app cards)
4. `#compare / .comparison` — Feature comparison table
5. `#faq` — Accordion FAQ
6. `.bottom-cta` — Repeat CTA
7. `footer` — Links

## Development

No build step. Open `yapyap-landing.html` directly in a browser. To preview changes live, use any static file server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080/yapyap-landing.html
```

## Design Conventions

- All section headings use `font-family: var(--hand)` (Caveat) for the hand-written feel
- Color palette: dark background `#1E1E24`, lavender `#C4B8E8`, warm orange `#F4A261`, mint `#7EC8A0`
- Creatures are pure SVG — same base shape reused with expression variations
- Responsive breakpoint at `max-width: 640px` in a single media query at the bottom of the stylesheet
- Animations: `breathe-anim`, `pulse-ring-anim`, `spin-ring`, `zzz-float`, `think-dot`, `scribble-anim`, `penWiggle`
