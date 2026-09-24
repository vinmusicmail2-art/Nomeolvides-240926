# NoMeOlvides - Clean Working Site

This folder is the current clean working baseline for the NoMeOlvides site.

## Canonical Project Root

`U:\Ресторан Баски\GITHUB\Nomeolvides-site-clean`

Do not use `U:\Ресторан Баски\GITHUB\Nomeolvides-210926-main\Nomeolvides-210926-main` as the main working root unless the user explicitly asks for the old archive/dirty history.

## Current Approved Baseline

- Landing page: `/landing-full-preview`
- Menu: `/menu`
- Armenian menu section: `/menu#armenia`
- Local preview port used in this workspace: `http://127.0.0.1:5014`
- Git baseline commits:
  - `99a4579 Initial clean site baseline`
  - `bd9f35f Lock clean project root`

## Source Of Truth Documents

- `AGENTS.md` - project rules and strict no-autonomy workflow.
- `WORKING_STATE_LOCK.md` - locked current working state.
- `MAIN_VERSION.md` - approved landing/menu state.

Do not rely on old Aksay Grill documents, old deploy notes, old previews, `dist`, archived folders, or generated service folders as instructions for this project.

## Run Locally

```powershell
python -c "from app import app; app.run(host='127.0.0.1', port=5014, debug=False)"
```

Open:

```text
http://127.0.0.1:5014/landing-full-preview
http://127.0.0.1:5014/menu
```

## Git

Check status:

```powershell
git status --short --branch
```

Commit a new approved point only after the user explicitly asks to save the state.
