<!--
Project: boa-remake (static-site skeleton)
Purpose: Give AI coding agents the concrete, repo-specific rules
--> 

# Copilot instructions for this repository

Purpose: Help AI coding agents make minimal, correct, and reviewable changes in this small static site repository.

**Big picture**
- **Type:** Single-page static website (no build system present).
- **Primary files:** `index.html`, `script.js`, `styles.css` at repository root.
- **Intent:** Keep changes small and orthogonal: markup in `index.html`, behavior in `script.js`, and presentation in `styles.css`.

**How to run / verify locally**
- Open `index.html` directly in the browser, or run a simple static server (e.g. `npx http-server` or `Live Server` extension).
- Debugging: use browser DevTools (Console, Network, Sources) to inspect runtime behavior from `script.js` and CSS rules from `styles.css`.

**Project-specific conventions and patterns**
- No frameworks or bundlers are present; do not introduce a build tool without explicit approval.
- Keep JavaScript vanilla and modular: attach behavior to named DOM nodes (use `id` attributes) and avoid global mutation.
- Styles belong in `styles.css`; prefer class names over inline styles.
- When adding UI elements, add minimal, semantic HTML (e.g., `<main>`, `<header>`, `<section>`, `<button id="...">`).

**Editing rules for AI agents**
- Make atomic changes: one logical change per commit/PR (e.g., "Add contact form" or "Fix header styling").
- If you change markup in `index.html`, update `script.js` and `styles.css` accordingly in the same patch.
- Avoid large-scale refactors or adding dependencies. If a dependency is necessary, add a short rationale in the PR description and wait for human approval.
- Prefer explicit, minimal examples rather than scaffolding entire frameworks.

**Examples (concrete snippets to follow repository pattern)**
- Add a button in `index.html` with `id="my-action"`, then in `script.js`:
  ```js
  document.getElementById('my-action').addEventListener('click', () => {
    // small, self-contained behavior
  });
  ```
- Add corresponding CSS in `styles.css` using a class or the `#my-action` selector.

**When to ask the human**
- If a change needs a new dependency (npm, CDN) or a build step.
- If you plan to restructure the repo (add folders, move files, change public API).
- If tests or CI should be added — this repo currently has none.

**Files to inspect for context**
- `index.html` — primary markup.
- `script.js` — client-side behavior.
- `styles.css` — styling.

If anything here is unclear or you need a different level of detail (for example, the intended UX or specific accessibility rules), ask the repository owner before making large changes.

-- End of file
