# Repository Guidelines

## Project Structure & Module Organization
- `weblog/` holds posts. Use `YYYY-MM-DD_HH_MM_slug.md`, keep YAML front matter with `Date`/`Tags`, then a single H1 title.
- `configuration/` contains `configuration.txt` plus `template.html`; edit them in the same change whenever you introduce a new token or navigation element.

## Build, Test, and Development Commands
- `npx prettier ./weblog --write` — formats the contents.
- `git push origin main` — triggers the `neatnik/weblog.lol` GitHub Action that imports content to omg.lol; push only after linting passes.

## Coding Style & Naming Conventions
- Prefer a single H1 followed by H2/H3 sections; soft-wrap around 100 characters so diffs stay narrow.
- Use American English for template copy, but keep quoted text in its original language.
- Inline HTML inside posts should stay minimal; heavier markup belongs in `template.html` with tab indentation and double-quoted attributes.

## Testing Guidelines
- After linting, preview edited Markdown locally (VS Code preview or similar) to verify headings, links, and assets resolve.
- For `template.html`, open the file directly in a browser, watch dev tools for console errors, then verify the published omg.lol render once the Action run completes.

## Commit & Pull Request Guidelines
- History favors short, lowercase summaries (`update`, `readme`). Stick to one imperative line (e.g., `add soccer recap`) and add detail in the body when touching multiple folders.
- PRs should describe content vs. configuration changes, link any related omg.lol post, attach before/after screenshots for template tweaks, and note if secrets such as `WEBLOG_API_KEY` are impacted.

## Security & Configuration Tips
- Keep omg.lol API keys in the `WEBLOG_API_KEY` repository secret only.
- Treat `weblog/` as the source of truth; if edits occur on omg.lol, pull a new export before changing files locally to prevent drift.
