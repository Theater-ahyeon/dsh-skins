# Verification / 验证说明

These files are captures from the real official DSH 0.1.7-rc.1 Web GUI in an isolated profile, taken on 2026-10-02. They are not generated design mocks. Both themes were exercised at 1440×900 and 390×844.

## GUI evidence

- Four theme/viewport combinations per skin; the complete two-skin run passed 80 interaction checks and two restoration checks.
- Settings/general and model configuration, opaque permission/model menus, actual sapphire switch toggle and restoration.
- Draft typing and clearing, sidebar collapse/reopen, details expansion, keyboard Escape and persisted skin activation.
- Switching to blue-fantasy and no skin removes Midnight Contract styles. Original QA skin/theme restored.
- Zero page errors and zero failed asset requests. Background source hashes match their contributor-provided originals.
- Standard preview/light.jpg and preview/dark.jpg were captured directly by the browser (JPEG quality 85); other evidence is native PNG screenshot output.

Machine-readable results: [gui-verification.json](gui-verification.json). Screens: [preview/](preview/).

## Automated gates

Skin catalog/safety pipeline (55 catalog entries), reviewed-hook registry, typecheck, build and generated lib drift check pass. Tool script tests pass 27/27 in the normal temporary environment. The untouched dsh-web baseline passes typecheck and docs:check. See the contribution PR for final full-test/CI results.

The contribution's [Ubuntu CI run](https://github.com/zhu1090093659/dsh-skins/actions/runs/36916974113) passed all repository gates, including the complete 776-test suite and 27 script tests. [PR #33](https://github.com/zhu1090093659/dsh-skins/pull/33) records the final review status. The local filesystem limitations below are retained as historical validation evidence.

## Environment boundaries

The Windows full-suite run encounters the existing file-symlink permission failure in tests/pkg-extract.spec.ts. Genuine Linux runs execute that symlink test successfully, but the available WSL temporary filesystem reproduces existing immediate root-mtime/cache invalidation assertions. No test assertion, timeout or host implementation was changed to hide these conditions. The upstream base commit has a successful Ubuntu CI run. Full local tests are not described as all-green until a supported complete run proves it.

No model key was entered and no inference request was sent. Live assistant messages, streaming code and actual tool receipts remain untested; their styles use the existing semantic surfaces. Optional plugin rows were not present in this minimal profile. No user acceptance or pixel-perfect claim is inferred from automation.

## 中文说明

两版在真实 DSH 宿主覆盖亮暗、桌面／窄屏、设置、模型、菜单、开关、草稿、侧栏与详情，并验证切回默认和无皮肤恢复。原图哈希一致。测试未填入模型凭据、未调用模型、未伪造回复，因此真实流式回复与工具内容仍是验证边界。完整测试中的系统符号链接／mtime 环境失败会在 PR 如实说明，不通过修改测试掩盖。
