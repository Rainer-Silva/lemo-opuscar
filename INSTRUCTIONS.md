# INSTRUCTIONS.md — Lemo-Opuscar (Rainer-Silva fork)

This file was added to the fork for Rainer Andrade Silva on 12 November 2026 (Europe/Stockholm). It is not part of the upstream project.

- **Upstream:** https://github.com/lemomo-ai/lemo-opuscar
- **This fork:** https://github.com/Rainer-Silva/lemo-opuscar
- **Gallery:** https://lemomo-ai.github.io/lemo-opuscar/
- **License:** mixed — code is MIT; docs and style prompts are CC BY-NC 4.0 (with an extra permission to use them to make your own films, including commercial films); demo films are CC BY 4.0; some third-party assets, voice tracks, and Anthropic’s “Clawd” character are excluded. Read `LICENSE` and `LICENSES/` before reusing material. GitHub shows the license as “Other” (NOASSERTION) because it is not a single SPDX license.
- **Reviewed snapshot:** 15,024 stars, 1,828 forks, last upstream commit 12 Nov 2026, 06:59 CET (Europe/Stockholm). The Instagram reel claimed about 11.7k stars; the live count is higher, which fits a fast-growing repo (created 26 September 2026).

## What it is

Lemo-Opuscar is a toolbox of 99 film styles for a coding agent, mainly Claude Code. You pick a style and a topic; the agent writes code (canvas, WebGL, ffmpeg, optional TTS and music) to render a short film. There is no video-generation model. Upstream says a film takes about 30–60 minutes and “a fair amount of tokens,” and is built for Claude (Fable / Opus / Sonnet) at high effort. Other models may not reproduce the styles well.

## Can it cut token usage / cost?

| Question | Honest answer |
|---|---|
| Cut Grok Bot / this assistant’s usage? | **No.** |
| Cut LLM token count or cost? | **No — it increases both, often a lot.** Each film is a long, high-effort agent session. |
| Other value? | Creative / YouTube-style shorts made in code, if you later want that and accept the token cost. It is not a savings tool. |

## Setup (do not run until you have decided to try it)

Needs Node 20+, ffmpeg 7+ (Ubuntu 24.04’s ffmpeg 6.1 is too old), and Python 3.11+ (or uv). Official install is a Claude Code plugin:

```sh
claude plugin marketplace add lemomo-ai/lemo-opuscar
claude plugin install lemo-opuscar@lemolab
```

On first use it downloads guides, tools and style prompts to `~/lemo-opuscar`. For other agents, copy `plugin/skills/lemo-opuscar/` into that agent’s skills folder. You can also clone this fork or upstream and work from the repo.

Three styles (Manga Panels, Text Flash Cuts, Comic History Cartoon) need an image generator you already have; the others do not.

## Risks and caveats

- **This will spend tokens**, and may spend paid Claude / TTS / image-API usage. Do not start a film until the spend is approved.
- **Mixed license.** Do not republish the docs or style prompts commercially except as allowed in `LICENSE`. Films *you* make are yours, but third-party samples keep their own terms. Do not extract the six excluded TTS voice tracks or reuse Anthropic’s Clawd character.
- The repo is large (on the order of 200 MB) because of style demos and assets.
- Star growth is fast for a six-week-old repo; still treat popularity as marketing.
- Scan the skill with SkillSpector (`--no-llm`) before installing it into an agent.

## Cost note

Running anything that needs paid APIs, Claude usage, image generation, or extra servers requires Rainer’s spend approval first. Forking and browsing the gallery is free. A single short film is not a 0 kr test if it runs on a paid Claude plan.

## Recommendation

Do not use this to reduce token usage — it does the opposite. Keep the fork as a reference if you later want code-rendered films (for example YouTube experiments). Any real film should be a separate, approved spend.
