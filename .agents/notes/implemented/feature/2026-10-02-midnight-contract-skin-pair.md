# Agent Note: Midnight Contract skin pair

Status: implemented

## Problem

The contributor requested two character-led skins with extensive generated UI materials rather than a palette-only reskin. The selected castle and city backgrounds both place the character on the left, whereas the original concept placed the character on the right. Default desktop settings navigation also consumes most of a narrow viewport.

## Decision

Submit two independently installable v2 pure-asset directories generated with the standard scaffolder. Keep each supplied background byte-for-byte and derive its matching portrait through CSS. Place the empty-state composer to the right on desktop, preserve its native shrink behavior when details are open, and use horizontal settings navigation below 600px. Generated assets decorate the existing workspace, form, menu, toggle, card and composer controls; there are no hooks, model changes or DOM mutations. Prefer semantic attributes and disclose the bounded class-suffix L3 seams in each README.

## Alternatives considered

- Repainting the supplied scene would break the contributor's explicit background selection.
- Baking text or navigation into raster images would lose native localization, editing and accessibility.
- Adding an executable skin hook just to replace labels would increase the review surface without adding necessary functionality.
- Blurring the composer card itself would change the containing block for fixed tooltips; leave frost to the controller's body-level sibling.

## Consequences

The two directories duplicate material references intentionally so Workshop packages remain self-contained. Original background hashes, generation prompts, material licenses and real-GUI screenshots accompany each skin. Optional plugin rows only appear when their actual plugins are installed. Class-suffix compatibility requires retesting against future official shell versions. Live inference remains untested without model credentials; no fabricated model responses are presented as evidence.
