# Parallel V6 Lossless Refactor

This package is intentionally **lossless**.

The original uploaded files are preserved byte-for-byte in the `legacy/` folder:

- `legacy/parallel-app-v5.html`
- `legacy/parallel-studio.html`

`apps/app/index.html` is now the integrated Parallel product experience. It mounts Studio as a real module inside the same global phone shell, dock, plus button, status bar, background atmosphere, and navigation rhythm used by Home, Tasks, and You.

`apps/studio/index.html` remains as a standalone Studio preview and development harness with the Studio Block Engine, interaction polish, page tree, persistence, database core, and shell-alignment work applied, so it is no longer byte-for-byte identical to the uploaded Studio source.

## Run

```bash
npm install
npm run dev
```

Then open the launcher and choose the integrated Parallel app. The standalone Studio preview remains available for development and comparison.

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

`apps/app/index.html` now includes Studio as a mounted Parallel module. Tapping `STUDIO` in the global dock switches into the Studio world without leaving the main app shell or creating a second footer, status bar, or plus button.

`apps/studio/index.html` still includes the Studio Block Engine foundation plus the polished slash menu, transform sheet, mobile editing toolbar, page tree, workspace drawer, local persistence, search/archive restore, database core, and Phase 4.5 shell alignment as a standalone preview/dev harness.

The canonical global dock order is:

```text
HOME / TASKS / + / STUDIO / YOU
```

That order is applied to both runnable shell entries. In the integrated main app, `TASKS` safely maps to the existing Timeline surface and `STUDIO` opens the mounted Studio module in place. Focus is preserved through its existing entry points and logic, but it is no longer a dock slot in this shell map. Studio keeps its internal workspace drawer, page tree, editor toolbar, slash menu, database block, and archive/search/restore flows as module-level tools above or inside the global shell.

## Studio Phase History

- Phase 1: Block Engine. Data-backed blocks, block rendering, slash insertion, block actions, and move up/down foundation.
- Phase 2: Slash Toolbar. Premium grouped slash menu, mobile editing toolbar, transform sheet, keyboard navigation, and motion polish.
- Phase 3: Page Tree Drawer. Studio page hierarchy, workspace drawer, page actions, breadcrumbs, editable title, and empty states.
- Phase 3.5: Persistence/Search/Archive. Versioned localStorage, page search, archive restore, safer active page and block persistence.
- Phase 4: Database Core. Database, property, record, registry, persistence, database block preview, create database, and new record foundations.
- Phase 4.5: Shell Alignment. Shared dock order, contextual global create menu, launcher wording, and documentation clarity. This is not full app-module integration.
- Phase 5: Studio Module Mount. Studio is mounted inside `apps/app/index.html` under the global Parallel shell while `apps/studio/index.html` remains a standalone preview/dev harness.
- Phase 6: Shared Shell Foundation. Stable shell metadata now lives in `systems/shell/shared-shell.js`: dock order, contextual create actions, storage constants, z-index/overlay constants, and the dock-aware overlay clamp helper used by both runnable entries.

See `docs/PHASE1_BLOCK_ENGINE.md`, `docs/PHASE2_SLASH_TOOLBAR.md`, `docs/PHASE3_PAGE_TREE_DRAWER.md`, `docs/PHASE3_5_PERSISTENCE_SEARCH_ARCHIVE.md`, `docs/PHASE4_DATABASE_CORE.md`, `docs/PHASE4_5_SHELL_ALIGNMENT.md`, `docs/PHASE5_STUDIO_MODULE_MOUNT.md`, and `docs/PHASE6_SHARED_SHELL_FOUNDATION.md`.

## Verify that nothing was removed

```bash
npm run verify:lossless
```

The verification script compares only the preserved legacy files against the recorded checksums in `docs/source-checksums.json`.

## Migration rule

Future refactors should move code gradually from the preserved originals into modular files only after confirming that the original behavior and UI are still intact.
