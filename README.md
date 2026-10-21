<!-- © 2026 Chenell Moniq'ue & Automations Bae. All rights reserved. Proprietary and confidential. Unauthorized copying, sharing, resale, or removal of this notice is prohibited. See LICENSE. -->

# Automations Bae's Edit Kit

![Automations Bae](assets/Automations%20Bae%20Logo.png)

Automations Bae's video-editing kit for **Claude Code and Codex**, built on HyperFrames.
You bring the footage. The AI agent cuts the dead air, catches your mistakes, plans the story, adds captions and B-roll, and builds the motion graphics with HyperFrames and GSAP.

Most people edit videos by hand. We hand the file to an agent and get our time back.

## What's included

- **[Editing playbook](docs/EDITING-PLAYBOOK.md):** the Automations Bae house rules, plus the B-roll, caption, and sound rules, and how every note becomes a rule in a skill.
- **14 skills**, mirrored for both assistants, with their helper scripts and references.
- **406 draft motion-graphics cards** across two styles (Paper Explainer and Bae Glow), with manifests, CSS tokens, and editable slots. Bae Glow uses the Automations Bae navy, copper, and gold.
- **Two scene templates:** dark graph paper and a left glass popout.
- Transcription, silence cutting, mistake detection, reviewed cut rendering, transcript retiming, EDL review, beat-sync validation, and preflight tools.
- **Short-form editing:** 9:16 reels, YouTube Shorts, hook and payoff planning, precise captions, moving B-roll, and audio review.
- **Brand kit:** logo, brand board, and color tokens in [`assets/`](assets/).
- A practice starter video and editing fixture that need no footage or API key.

## Tools and optional services

The kit transcribes with **ElevenLabs Scribe** and can generate video and image assets with **Kie.ai**. Bring your own API keys and credits if you use them. You can also ask the agent to use OpenAI Whisper or local Whisper instead, or hand it a word-level transcript you already have. Generated assets are optional.

The starter needs no paid service. See the [tools, accounts, and API-key guide](docs/TOOLS-AND-API-KEYS.md) for setup details and prompts you can copy.

## Install

Install Node.js **22 or newer**, Git, FFmpeg (including ffprobe), and Chrome or Chromium. Make `node`, `ffmpeg`, and `ffprobe` work in your terminal. Then run:

```sh
git clone https://github.com/AutomationsBae/automations-bae-edit-kit.git
cd automations-bae-edit-kit
npm ci
npm run setup
npm test
```

Setup checks your tools and creates `.env` only if you don't have one yet. Add only the keys for the services you use. [Setup and troubleshooting](docs/SETUP.md).

## Render your first example

```sh
npm run demo
cd video-projects/demo
npx hyperframes lint
npx hyperframes preview
```

Scrub the eight-second animation in Studio. When you're happy, stop the preview with Ctrl+C, then render:

```sh
npx hyperframes render --quality draft --output renders/demo.mp4
```

The first render may download some fonts. The demo has no voiceover. The [practice transcript](examples/editing/source.json) is made-up test data for trying the cutting tools.

## Edit your footage

Open this folder in Claude Code (or Codex) and say:

> Use edit-video to edit my recording at [local path]. Keep my examples and core lessons. Tighten dead air, show me the proposed mistake cuts, and use the dark graph-paper style with Bae Glow cards. Produce a reviewed draft.

Claude Code: `/edit-video`. Codex: `$edit-video`. For one job at a time use `cut-silences`, `cut-mistakes`, `video-storytelling`, or `style-library`. See the [step-by-step workflow](docs/WORKFLOW.md), [prompt recipes](docs/PROMPTS.md), and [storytelling workbook](docs/STORYTELLING-WORKBOOK.md).

## Create a reel or YouTube Short

> Use short-form-edit to turn my recording at [local path] into a 9:16 reel. Follow the Automations Bae house rules. Build a true hook and payoff, keep my meaning, tighten mistakes, and add captions, moving footage, and sound design. End on my CTA. Prepare a draft for review. Use my own footage before suggesting generated assets.

Claude Code: `/short-form-edit`. Codex: `$short-form-edit`. The skill comes with checks for caption timing, source mapping, scene coverage, and footage reuse. Always watch the real motion and listen to the audio before you post. [Short-form walkthrough and validation commands](docs/SHORT-FORM.md).

## Make a motion-design showreel

> Use motion-showreel to make a 15-second showreel for Automations Bae. Study my reference reel at [local path] if I give one. Pick one motif that changes through every chapter, cut on the music's beat, and end on the logo. Show me the storyboard and beat sheet before building, and check with me before any paid music or asset generation.

Claude Code: `/motion-showreel`. Codex: `$motion-showreel`.

## Your projects

Each new video gets its own folder in `video-projects/` (run `npm run new-video <name>`). Put raw footage in `raw-media/`. Both folders are ignored by Git, so your footage, transcripts, and renders stay on your computer and never get pushed.

## Explore and customize

| Resource | Start here |
| --- | --- |
| House rules, style, and lessons | [Editing playbook](docs/EDITING-PLAYBOOK.md) |
| Brand colors and fonts | [assets/brand-tokens.css](assets/brand-tokens.css) |
| Shared agent instructions | [CLAUDE.md](CLAUDE.md) (same as [AGENTS.md](AGENTS.md)) |
| Motion and transition vocabulary | [MOTION_PHILOSOPHY.md](MOTION_PHILOSOPHY.md) |
| Card library and design tokens | [Library guide](style-library/GUIDE.md) |
| Searchable card list | [registry.json](style-library/registry.json) |
| Whole-scene templates | [Template guide](style-templates/README.md) |
| Codex setup and mirroring | [.codex/README.md](.codex/README.md) |
| Release checks and limits | [Verification](docs/VERIFICATION.md) |
| Third-party resources | [Notices](THIRD_PARTY_NOTICES.md) |

The cards are **draft assets**. The names, labels, and numbers inside them are placeholders. Swap in your own real copy before you publish, and never post a number you can't back up. Some templates load GSAP and Google Fonts from public CDNs; save them locally when you build a final project.

## License

Copyright (c) 2026 Chenell Moniq'ue & Automations Bae. All rights reserved. This is proprietary software licensed only to paying students and clients. See [LICENSE](LICENSE) and [NOTICE](NOTICE). Some parts come from open-source projects and keep their own licenses in the [`licenses/`](licenses/) folder. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
