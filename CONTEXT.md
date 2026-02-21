# Project Context

This file is the shared handoff context for agents working on this repo.
Update it whenever meaningful UI, behavior, data, or structure changes are made.

## Repo
- Name: `mouminx.github.io`
- Root: `mouminx.github.io/`
- Site pages:
  - `index.html` (landing / choose path)
  - `overview.html` (quick-view project cards, GitHub-backed)
  - `in-depth.html` (expanded case-study cards with carousel placeholders)

## Current UX / Visual Direction
- Light modern liquid-gradient background system (white base with green hues) with animated blobs.
- Node-network canvas overlay tuned for subtle visibility on light backgrounds.
- Subtle grain texture overlay.
- Flat glass cards (no folder tabs, no file-slip animation).
- Card/image "cover" slots are now part of project cards to support custom logo artwork.
- Tilt:
  - enabled on `overview` project cards
  - disabled on `in-depth` cards (intentionally removed because cards are large)

## Overview Page Behavior (`overview.html`)
- Pulls repos from GitHub user API (`mouminx`), filters forks and blocked repos.
- Grid cards show:
  - top cover slot (logo cover image or placeholder)
  - title in card body
  - compact tags
  - updated date + repo link
  - `Details` button
- Expanded section shows:
  - top cover slot (logo cover image or placeholder)
  - title
  - grouped tags:
    - `Languages Used`
    - `Technologies`
  - one-line pitch
  - technical value
- Repo-specific overrides exist for:
  - `forest-rogue-like`
  - `sell-keep-salvage`
  - `tailored.io` / `tailored-io`
  - `nikkah_planner` / `nikkah-planner`
  - `megabonk_ml` / `megabonk-ml`
  - `tower-defense` variants

## In-Depth Page Behavior (`in-depth.html`)
- Cards are stacked and collapsed by default.
- Each card expands to:
  - top cover slot (logo cover image or placeholder)
  - title
  - grouped tags (`Languages Used`, `Technologies`)
  - sections: `Problem`, `Vision`, `Solution`, `What's Next`
  - right-side media placeholder carousel (`Prev` / `Next`)
- Case-study entries currently include:
  - Forest Rogue-like Engine
  - AI-Assisted ARPG Loot Evaluator
  - Tower Defense Systems Engine
  - Resume Tailor (tailored.io)
  - Nikah Planner
  - Megabonk RL Agent

## Content/Data Convention
- For project data in both pages, prefer:
  - `languages: []`
  - `technologies: []`
  - avoid mixed `tags` unless fallback is needed.
- Keep pitch concise and technical value outcome-focused with bold keywords where appropriate.

## Editing Rules For Future Agents
1. When adding a new project:
   - update `overview.html` repo override map
   - update `in-depth.html` caseStudies array
2. Keep naming keys robust:
   - include likely slug variants (`_` and `-` forms).
3. Preserve existing visual language:
  - light liquid background + subtle node overlay
  - logo cover slots on cards
4. After changes:
  - append to `## Change Log` in this file
  - keep summary short and concrete

## Change Log
- 2026-02-21: Added this context file and documented current architecture, UI patterns, and update protocol.
- 2026-02-21: Refined folder tab visuals: cleaner slanted edge, full-width stacked file slips, outline visibility, and tab-width syncing for overview/in-depth cards.
- 2026-02-21: Switched all pages to a light/white green-accent theme, removed folder tab/file-slip effects, and added reusable logo cover slots on overview and in-depth project cards.
- 2026-02-21: Rebased card styling on glassmorphism (rounded cards, stronger blur, spec-style highlights/inset glow) and increased node-network prominence with faster, denser, gray-toned animation across all pages.
