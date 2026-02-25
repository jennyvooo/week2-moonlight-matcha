# BUILD PLAN — Dark Mode Toggle (Micro-Iteration)

Goal: Add a dark mode toggle to the Moonlight Matcha Cafe static website using micro-iteration (small steps, frequent review/testing).

## Step 1 — Add CSS dark mode variables (styles.css)
- Add a `body.dark-mode` block that overrides existing CSS variables (background, text, accents, shadows).
- No UI yet.
- Quick test: temporarily add `class="dark-mode"` to `<body>` in devtools and confirm colors flip.

## Step 2 — Add toggle button HTML to all pages
- Add `<button id="theme-toggle" aria-label="Toggle dark mode" aria-pressed="false">🌙</button>` to the nav.
- Pages: index.html, about.html, menu.html, contact.html, gallery.html (all pages).
- Verify the button appears on every page.

### Self-Review Checkpoint 1 (after Step 2)
- Are dark colors readable and intentional?
- Does the button appear correctly on mobile and desktop?
- Are all pages updated consistently?

## Step 3 — Toggle logic (script.js)
- Add a click handler that toggles `body.dark-mode` and swaps the icon.
- Add `aria-pressed` updates for accessibility.
- Verify clicking works.

## Step 4 — Persist theme with localStorage (script.js)
- Save theme to localStorage on toggle.
- Restore on load so it persists after refresh and navigation.

### Self-Review Checkpoint 2 (after Step 4)
- Does it persist across pages and refresh?
- Does the icon match the active theme on first load?
- Any sections that look wrong in dark mode?

## Step 5 — Style the toggle button (styles.css)
- Remove default button styling.
- Add sizing, hover, focus-visible states, and smooth transitions.
- Verify focus ring is visible for keyboard users.

## Step 6 — Full audit + cleanup
- Check all pages in dark mode.
- Fix missing toggle on any page.
- Remove redundant JS logic and keep behavior consistent.
- Verify nothing unrelated changed.
