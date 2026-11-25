# Agent Instructions

## Purpose

This file gives AI coding agents the context and rules for working on this project. Follow it every session.

## Before You Start

- Read `docs/PRD.md` to understand the product and its goals.
- Read `docs/DESIGN_SYSTEM.md` before building any UI.
- Read `docs/ARCHITECTURE.md` before creating files or adding tools.
- Check what already exists before creating something new.

## Working Principles

These bias toward caution over speed. For trivial tasks, use judgment.

### 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

### 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

## Project Rules

- Only build what is in the PRD. Ask before adding features.
- Follow the design system exactly. No new colours or fonts.
- Reuse existing components and utilities before writing new ones.
- Handle loading, error and empty states.
- Don't add a tool, service or dependency without updating `docs/ARCHITECTURE.md`.
- When the stack, features or design change, update the matching file in `docs/`.

<!-- stack:begin -->
## Stack Rules

- Plain HTML, CSS and vanilla JavaScript in a single `index.html`. No framework, no build step, no npm dependencies.
- The only other files are `manifest.webmanifest`, `sw.js` and the three icon PNGs, all in the same folder as `index.html` (flat, no subfolders).
- Every external system is one entry in the `SYSTEMS` array in `index.html`. Add or change a system there, with its Malay (`ms`) and English (`en`) name and description.
- Every visible string lives in the `T` object in both `ms` and `en`. Never hard-code text in only one language.
- After any change to `index.html`, raise the version in `CACHE` in `sw.js` (for example `syshhb-portal-v13` to `v14`) so installed copies update.
- Time and dates use the `Asia/Brunei` time zone. The Hijri date uses `islamic-umalqura` plus the saved day adjustment.
- The manifest must stay a real file linked with `<link rel="manifest">`. A manifest built in JavaScript makes phones install a shortcut, not an app.
- Keep `theme_color`, `background_color`, the page header's top colour and the icon background the same green (`#27a047`), so the app's opening screen blends in.
- The crest logo stays still. Do not animate, tilt or spin it.
- Check every change at phone (390x780) and desktop (1884x927) sizes. On a phone the header and all tiles should fit on one screen without scrolling.

## Commands

```sh
python3 -m http.server 8080   # Run locally at http://localhost:8080 (the install prompt needs https, so test that on the live site)
```

There is nothing to install or build. To publish, upload `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png` and `icon-maskable.png` to the same folder on the https host.
<!-- stack:end -->

## Security

- Never put API keys or secrets in code, and never commit them.
- Keep anything sensitive in environment variables or the platform's secret store.
- Validate all user input.

## When Unsure

- Check the `docs/` folder first.
- Look at how existing code does it.
- Ask before making big changes.
