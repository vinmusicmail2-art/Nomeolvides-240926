<!-- CODEX_GLOBAL_RULES_START -->
# Global Codex Rules (synchronized)

# User Rules

- Save Codex chat archives to `E:\INSTALL_DISTRIB\Obsidian\CODEX\CODEX`.
- For each new chat, create a separate folder in `E:\INSTALL_DISTRIB\Obsidian\CODEX\CODEX\CHAT_ARCHIVES`.
- Store a readable `dialog.md` and the original `raw_session.jsonl` when local Codex session logs are available.
- Use `E:\INSTALL_DISTRIB\Obsidian\CODEX\CODEX\TOOLS\sync_codex_dialogs.ps1` to sync existing local Codex sessions into Obsidian.
- When the user asks to create a Codex Desktop project and put/move the current chat into it, do not only create a filesystem folder. Create the project folder, place the chat/context files there, then register the folder in Codex Desktop state so it appears in the Projects window: update saved workspace roots / project order / active workspace roots, remove the current thread from projectless threads, set the thread workspace root hint, and update the thread `cwd` in `state_5.sqlite`. Always create backups of `.codex-global-state.json` and `state_5.sqlite*` first, then verify the project path is present in `project-order` and the thread points to that project.
- Default desktop behavior for every new chat is to start with `ChatGPT 5.5` / `gpt-5.5` while OpenAI still provides it. For routine or бытовые tasks, use the lowest practical reasoning level. If `ChatGPT 5.5` / `gpt-5.5` is no longer available, automatically choose the lowest-ranked available newer successor model in the model list, not the largest or highest-intelligence option by default. Do not silently switch to a larger or higher-intelligence model after relaunch. Only raise the model or reasoning level when the user explicitly asks for it or the task clearly requires it, and call that out before changing it.
- For connector/integration issues like a messenger or plugin turning back on, first inspect local config and app state, verify whether there is a second enablement layer, and try to disable it yourself before asking the user for any action. Only ask the user if a real external blocker remains after that check.
- If the task or requested change is unclear, or there are multiple plausible interpretations, stop and ask one short clarifying question before making any changes. Do not guess the target, layer, or desired outcome.
- Strict write gate applies only to code, interface, data, repository, or other external-state mutations. When such a change is unclear, clarify the exact task, source, target, and expected result before acting, then wait for a separate user message containing the exact phrase `РАЗРЕШАЮ ИЗМЕНЕНИЯ`. Creating or editing documentation, reports, Obsidian notes, chat archives, and generated document files does not require this confirmation. A hook enforces the gate for supported write tools.
- Use this file as the global baseline for every chat and project. Then inspect the closest workspace or project `AGENTS.md`; files closer to the working directory apply to that subtree. Project docs such as `Wiki/CL.md` are lower-priority context, not a replacement for `AGENTS.md`. If instructions conflict or the target is still ambiguous, report the conflict and ask before acting.
- When a new project or chat archive is created, synchronize this global file into the target as a local `AGENTS.md` before reading project files or making changes. Use `E:\INSTALL_DISTRIB\Obsidian\CODEX\CODEX\TOOLS\sync_global_rules.ps1`; preserve project-specific rules below the managed global block instead of overwriting them.
- At the beginning of a new chat, run `E:\INSTALL_DISTRIB\Obsidian\CODEX\CODEX\TOOLS\sync_codex_dialogs.ps1` first so the new chat archive and its local `AGENTS.md` are created before project work starts.
- Before starting sales, competitive web checks, product-page verification, or other external browser research, enable the `browser/web` MCP if it is needed for the task.
- The user may assign a helper/auditor role named `Вальдемар`. Treat `Вальдемар` as a senior verification pass that checks the work after implementation. His standard checklist is: completeness, correctness, structure/location, stability after save/reload, and practical usability. When the user asks for `Вальдемар` to review something, make the result easy for auditing by keeping files named clearly, preserving the final state, and summarizing what changed, what remains, and where to inspect it.
<!-- CODEX_GLOBAL_RULES_END -->

# Project-specific rules

- Результаты сохранять и пушить в репозиторий `https://github.com/vinmusicmail2-art/Nomeolvides-210926`.
- Основная рабочая папка проекта NoMeOlvides с 2026-09-24: `U:\Ресторан Баски\GITHUB\Nomeolvides-site-clean`.
- Старую папку `U:\Ресторан Баски\GITHUB\Nomeolvides-210926-main\Nomeolvides-210926-main` считать архивной/грязной историей и не использовать как основной рабочий корень без отдельного прямого указания пользователя.
- Чистый Git/GitHub/deploy baseline находится в этой папке; тяжёлые служебные сборки, архивы, `dist`, `artifacts`, `backups`, `.sites-*`, `attached_assets`, `drafts` и старые прототипы не входят в рабочий baseline.
- Основной рабочий вариант лендинга NoMeOlvides зафиксирован в этом проекте.
- Последняя утверждённая пользователем основная рабочая версия сайта: `http://127.0.0.1:5014/landing-full-preview`.
- Для фраз «основная версия», «утверждённая версия», «рабочая версия сайта» открывать и использовать именно `http://127.0.0.1:5014/landing-full-preview`.
- Не открывать и не публиковать старые версии сайта, старые preview, архивные копии, `dist` или старую публичную ссылку как основную без отдельного прямого подтверждения пользователя.
- Публиковать сайт можно только из текущей утверждённой версии `/landing-full-preview`, если пользователь отдельно просит публикацию.
- Запрещено без отдельного явного разрешения пользователя изменять его дизайн, структуру, композицию, тексты, фотографии, размеры, цвета, градиенты, навигацию и функционал.
- Любое изменение основного лендинга выполнять только после отдельной команды пользователя с явным разрешением на конкретное изменение.
- Перед изменениями сохранять текущую рабочую версию и проверять, что запрос относится именно к разрешённой части.
- Состояние сайта, зафиксированное 2026-09-24 в `WORKING_STATE_LOCK.md`, считать основным рабочим. Не сдвигать никакие кнопки, надписи, фотографии, декоративные элементы или кликабельные зоны без отдельного прямого разрешения пользователя.
- Если пользователь просит отредактировать конкретный элемент, менять только этот элемент ровно на его текущем месте. Не перестраивать соседние элементы, шапку, сетку, фон, изображения, размеры или ссылки по собственной инициативе.
- Жёсткий режим без додумывания: пользователь сам определяет, что нужно менять. Codex не имеет права расширять задачу, додумывать цель, менять способ реализации или затрагивать соседние элементы без отдельного прямого разрешения.
- Перед любой правкой рабочего сайта Codex обязан написать scope: `Меняю только: ...`, `Действие: ...`, `Не трогаю: ...`, `Способ: ...`, `Жду: РАЗРЕШАЮ ИЗМЕНЕНИЯ`. Без отдельной фразы пользователя `РАЗРЕШАЮ ИЗМЕНЕНИЯ` после такого scope нельзя редактировать рабочий сайт; разрешены только анализ, просмотр, диагностика и объяснение.
- Если элемент запечён в PNG/JPEG/макет и не является отдельным HTML-элементом, Codex не имеет права заменять его новым блоком, переносить секцию или пересобирать соседний layout. Нужно остановиться, явно сказать, что элемент запечён, предложить варианты `наложить поверх / пересобрать PNG / не делать`, и ждать выбора пользователя.
- Любая догадка считается запретом на действие. Если Codex думает "наверное нужно ещё..." — он обязан не делать это, а спросить.
- При запросе "вставить фото в фреймы" разрешено работать только с указанными фреймами на их текущем месте. Запрещено переносить весь блок, добавлять новый раздел, менять порядок секций или трогать кнопки.
- Все визуальные макеты и изображения для согласования сохранять в обычном формате JPEG (`.jpeg`), а не PNG, если пользователь отдельно не указал другой формат.

## Правило исполнения scope

Scope после разрешения нельзя интерпретировать. Его можно только выполнить буквально или остановиться.

- После того как пользователь утвердил scope фразой `РАЗРЕШАЮ ИЗМЕНЕНИЯ`, Codex обязан выполнить именно этот scope буквально.
- Запрещено менять критерий правки после разрешения.
- Запрещено заменять указанную пользователем границу, объект или ориентир на другой "примерно похожий".
- Если в scope написано "до левой границы картины", Codex обязан сначала определить эту границу измерением, а не выбирать процент на глаз.
- Если точная координата, граница или объект не определены, Codex обязан остановиться и сообщить: "Я не могу выполнить scope буквально без уточнения/измерения".
- Любое действие "на глаз" запрещено для утверждённых макетов.
- Перед сохранением изменения Codex обязан сверить результат с исходным scope одной строкой: "Сделано ровно: ...; не менялось: ...".
- Если во время работы выяснилось, что scope был неточным, Codex не исправляет сам, а возвращается к пользователю с новым scope.

## Архитектура лендинга: PNG + HTML overlay

- Для утверждённого лендинга NoMeOlvides не конвертировать весь сайт из PNG в HTML за один раз без отдельного прямого запроса пользователя.
- Правильный рабочий подход: оставлять утверждённые PNG как фон/секцию, а в HTML overlay переводить только те зоны, которые реально редактируются или должны быть кликабельными/заменяемыми.
- Перевод в HTML overlay выполнять посекционно: сначала определить рабочую папку, конкретный файл, слой (`PNG`, `HTML`, `overlay` или `неясно`), затем описать scope и ждать `РАЗРЕШАЮ ИЗМЕНЕНИЯ`.
- Если пользователь просит изменить конкретный элемент, не перестраивать весь PNG/раздел. Сначала проверить, можно ли сделать точечный HTML overlay поверх существующей секции. Если нельзя — сообщить, что элемент запечён, и предложить варианты.
- Редактируемые элементы, которые желательно держать как overlay: кнопки, ссылки меню, кликабельные зоны, часто меняющиеся надписи, карточки блюд, фото внутри фреймов, CTA и навигация.
- Цель этого подхода: меньше трогать утверждённый макет, меньше расходовать контекст, точнее выполнять только указанное пользователем действие и не додумывать соседние изменения.
