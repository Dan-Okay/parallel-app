# Parallel Architecture Direction

Parallel is moving from large prototype files into a scalable product architecture without losing its emotional design language.

## Source of truth

The preserved legacy files remain the current source of truth:

- `legacy/parallel-app-v5.html`
- `legacy/parallel-studio.html`

The app launcher points to runnable entries under `apps/`. `apps/app/index.html` remains an exact runnable copy of the preserved app; `apps/studio/index.html` now carries the Studio Block Engine, interaction polish, page tree, and workspace drawer while `legacy/parallel-studio.html` remains the untouched source archive.

## Migration strategy

1. Preserve the original files untouched.
2. Extract design tokens into `styles/variables.css` and `styles/motion.css`.
3. Move reusable UI into `components/` one component at a time.
4. Move screen logic into `modules/` one module at a time.
5. Move shared behavior into `systems/`.
6. Keep data and service boundaries ready for backend integration.
7. Verify after each migration that no visual or interaction behavior has been lost.

## Priority modules

- `modules/tasks/`
- `modules/studio/`
- `modules/focus/`
- `components/dock/`
- `systems/navigation/`
- `systems/state/`
- `systems/motion/`

## Visual identity rules

Do not remove the luxury sanctuary feeling. Preserve warm white surfaces, sage/lilac accents, floating glass cards, cinematic gradients, soft shadows, and tactile spring motion.
