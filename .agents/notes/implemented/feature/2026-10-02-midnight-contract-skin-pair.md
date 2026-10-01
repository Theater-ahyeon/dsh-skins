# Agent Note: Midnight Contract skin pair

Status: implemented

## Problem

The contributor requested two character-led skins with extensive generated UI materials rather than a palette-only reskin. The selected castle and city backgrounds both place the character on the left, whereas the original concept placed the character on the right. Default desktop settings navigation also consumes most of a narrow viewport.

## Decision

Submit two independently installable v2 pure-asset directories generated with the standard scaffolder. Keep each supplied background byte-for-byte and derive its matching portrait through CSS. Place the empty-state composer to the right on desktop, preserve its native shrink behavior when details are open, and use horizontal settings navigation below 600px. Generated assets decorate the existing workspace, form, menu, toggle, card and composer controls; there are no hooks, model changes or DOM mutations. Prefer semantic attributes and disclose the bounded class-suffix L3 seams in each README.

The official rc.1 renderer does not attach a message-body part to assistant Markdown or a tool-card part to tool views. Use actual assistant-step/tool-call flow kinds and their official slots, with a small body/bubble suffix seam where necessary. Code blocks expose stable banner/content attributes. Session-header is a display:contents wrapper, so its actual header receives the opaque title surface. Detail frame painting uses explicit border-image widths without increasing layout width, preserving the native closed pane.

## Alternatives considered

- Repainting the supplied scene would break the contributor's explicit background selection.
- Baking text or navigation into raster images would lose native localization, editing and accessibility.
- Adding an executable skin hook just to replace labels would increase the review surface without adding necessary functionality.
- Blurring the composer card itself would change the containing block for fixed tooltips; leave frost to the controller's body-level sibling.

## Consequences

The two directories duplicate material references intentionally so Workshop packages remain self-contained. Original background hashes, generation prompts, material licenses and real-GUI screenshots accompany each skin. Optional plugin rows only appear when their actual plugins are installed. Class-suffix compatibility requires retesting against future official shell versions. A clearly labeled local SSE protocol fixture exercises actual session messages, code and a genuine readonly tool receipt through the official Agent and renderer; it is not external model inference or DOM injection. QA removes its temporary provider and dummy credential, restores the original stock model selection, and opens the native new-session state for standard previews. External model inference and human visual acceptance remain separate boundaries.
