# Midnight Contract · Moonlit Castle

English | [中文](README.zh.md)

A Lu Mingze / Dragon Raja inspired skin for the real DeepSeek Harness Web GUI. Moonlit Castle uses the contributor-selected background unchanged, with a matching portrait and custom generated contract materials throughout the interface. Its companion [skin](../midnight-contract-city/README.md) shares the component language with a different scene.

## Preview

These are actual DSH 0.1.7-rc.1 GUI captures, not generated mockups. The default model label belongs to the host; no model call or synthetic assistant reply was used.

| Light | Dark |
| --- | --- |
| ![Light GUI](preview/light.jpg) | ![Dark GUI](preview/dark.jpg) |

Additional real captures are in [preview/](preview/). [Verification](VERIFICATION.md) records the tested states and limits.

## Interface

- Dragon-leather sidebar, matching portrait, four-quarter contract crest and burgundy invitation plaque.
- Generated workspace folio, metal spine, feather corner and custom folder/session glyphs; native scrolling and workspace actions stay intact.
- Sapphire envelope composer and red wax send seal; attachment, permission and model controls remain native interactive controls.
- Generated dossier frames for menus, model cards and message/tool surfaces; dark engraved input beds, action plaques and sapphire toggle thumbs.
- Ivory settings surfaces in light mode and navy surfaces in dark mode. Both retain the dark character-led sidebar and contract composer.
- Desktop hero copy stays to the right of the supplied left-hand character. Collapsed rails and narrow dialogs adapt to their real layout; settings navigation becomes horizontal below 600px.

## Install and remove

After this contribution is accepted and the market is rebuilt, install this skin from the DSH Workshop and select it in **Settings > Skins**. Before market availability, copy this entire directory to the skin center's user skin directory, normally `$DSH_HOME/skins/midnight-contract/`, then open the real DSH GUI and select it in Settings. `DSH_SKINS_HOME` overrides the user skin directory when explicitly configured.

This folder is an asset package, not a standalone HTML app. It needs the DSH web host and skin-center v2 loader. Choose another skin or no skin to restore host styling. The background controller retains Wallpaper Engine > manual background > skin background priority; the skin does not override user wallpaper settings.

## Integration and scope

Both files are controller-scoped to `html[data-dsh-skin="midnight-contract"]`. `skin.css` defines L1 tokens and L2 semantic parts; `patches.css` is a disclosed L3 layer for the real sidebar, composer, settings navigation, provider editor, switch thumb and menu suffixes. It uses stable semantic attributes/class suffixes rather than build hashes or text-dependent selectors.

The skin has no executable hook, remote asset, model behavior change, credential handling or backend configuration. Optional skill, task and SSH rows are decorated only when their actual plugins are installed; the skin does not invent navigation entries. Skin materials never carry functional text. Do not apply backdrop-filter to the composer: the controller owns its separate frost layer and fixed-tooltip positioning.

## Assets and license

See [NOTICE](NOTICE.md), [asset provenance](asset-provenance.json), [generation prompts](generation-prompts.json) and the repository [Apache-2.0 license](../../LICENSE). The background was supplied by the contributor, who confirmed public redistribution rights. The original file hash is recorded and the avatar is a CSS crop of that same file. Old Steam Workshop character art is excluded. Independent UI ornaments were generated using OpenAI image_gen; franchise ownership and official endorsement are not claimed.

## Development

This directory was generated with `node scripts/dsh-skin-new.cjs midnight-contract`. Run from the dsh-skins root:

```sh
pnpm skin-center:check
pnpm skin-hooks:check
pnpm build
pnpm typecheck
pnpm test
node --test scripts/*.test.mjs
```

The skin is self-contained pure content with no package or local build step. The Workshop packages it on demand; only blue-fantasy is included in the skin-center npm package. Recheck class-suffix seams and real GUI screenshots when the official web shell changes.
