# Parallel V6 Lossless Refactor

This package is intentionally **lossless**.

The original uploaded files are preserved byte-for-byte in the `legacy/` folder:

- `legacy/parallel-app-v5.html`
- `legacy/parallel-studio.html`

`apps/app/index.html` is still a runnable copy of the preserved app. `apps/studio/index.html` is now the runnable Studio entrypoint with the Studio Block Engine, interaction polish, page tree, and workspace drawer applied, so it is no longer byte-for-byte identical to the uploaded Studio source.

## Run

```bash
npm install
npm run dev
```

Then open the launcher and choose either Parallel App or Parallel Studio.

## What changed

This refactor does **not** simplify, redesign, or trim the product. It adds a professional architecture around the existing source:

- global styles folder
- components folder
- modules folder
- systems folder
- services folder
- data folder
- docs folder
- checksum verification script

## Current Studio Update

`apps/studio/index.html` includes the Studio Block Engine foundation plus the polished slash menu, transform sheet, mobile editing toolbar, page tree, and workspace drawer. See `docs/PHASE1_BLOCK_ENGINE.md` for the editor model, rendering, and block action checklist.

## Verify that nothing was removed

```bash
npm run verify:lossless
```

The verification script compares only the preserved legacy files against the recorded checksums in `docs/source-checksums.json`.

## Migration rule

Future refactors should move code gradually from the preserved originals into modular files only after confirming that the original behavior and UI are still intact.
