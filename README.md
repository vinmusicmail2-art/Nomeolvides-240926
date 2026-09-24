# NoMeOlvides - Clean Working Site

This folder is the current clean working baseline for the NoMeOlvides site.

As of 2026-09-25, this folder is the only approved working version of the site.

## Canonical Project Root

`U:\Ресторан Баски\GITHUB\Nomeolvides-site-clean`

Do not use `U:\Ресторан Баски\GITHUB\Nomeolvides-210926-main\Nomeolvides-210926-main` as the main working root unless the user explicitly asks for the old archive/dirty history.

## Current Approved Baseline

- GitHub repository: `https://github.com/vinmusicmail2-art/Nomeolvides-240926`
- Landing page: `/landing-full-preview`
- Menu: `/menu`
- Armenian menu section: `/menu#armenia`
- Nuestra taberna: `/nuestra-taberna`
- Galería: `/galeria`
- Verified local preview for the current running version: `http://127.0.0.1:5024`
- If `http://127.0.0.1:5014` shows pages without `inner-menu-sections.css`, that is an old running server and must not be treated as the working version.
- Git baseline commits:
  - `99a4579 Initial clean site baseline`
  - `bd9f35f Lock clean project root`
  - `0e850a2 Apply approved inner section designs`
  - `ae341a8 Document approved working baseline`

## Source Of Truth Documents

- `AGENTS.md` - project rules and strict no-autonomy workflow.
- `WORKING_STATE_LOCK.md` - locked current working state.
- `MAIN_VERSION.md` - approved landing/menu state.

Do not rely on old Aksay Grill documents, old deploy notes, old previews, `dist`, archived folders, or generated service folders as instructions for this project.

## Run Locally

```powershell
python -c "from app import app; app.run(host='127.0.0.1', port=5024, debug=False)"
```

Open:

```text
http://127.0.0.1:5024/landing-full-preview
http://127.0.0.1:5024/menu
http://127.0.0.1:5024/nuestra-taberna
http://127.0.0.1:5024/galeria
```

## Git

Check status:

```powershell
git status --short --branch
```

Commit a new approved point only after the user explicitly asks to save the state.
