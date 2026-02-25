# Dark Mode Toggle — Implementation Plan

## Step 1 — Add CSS dark mode variables `styles.css`
Define a `[data-theme="dark"]` selector that overrides every color variable. No new files, no visible UI yet — just foundation. Verify by temporarily adding `data-theme="dark"` to `<html>` in DevTools and checking colors flip.

---

## Step 2 — Add toggle button HTML to all 5 pages
Add a `<button id="theme-toggle">` to the `<nav>` in `index.html`, `about.html`, `menu.html`, `gallery.html`, and `contact.html`. Use a sun/moon icon (Unicode `☀` / `🌙` or SVG). Verify the button appears on every page.

---

## ✅ Self-Review Checkpoint 1 (after Step 2)
- Do the dark colors look intentional and readable? (Check contrast ratios mentally — cream→ near-black bg, charcoal→ near-white text)
- Does the button appear correctly on mobile and desktop?
- Are all 5 pages updated?

---

## Step 3 — Wire up toggle logic in `script.js`
Add a `initThemeToggle()` function: on click, toggle `data-theme="dark"` on `<html>`, save preference to `localStorage`, and swap the button icon. Call it from `DOMContentLoaded`. Verify: toggle persists on page refresh.

---

## Step 4 — Persist theme across page navigation
At the very top of `script.js` (before DOM ready), read `localStorage` and apply `data-theme` immediately to prevent flash of wrong theme. Verify: navigate from index → menu → about; theme stays consistent.

---

## ✅ Self-Review Checkpoint 2 (after Step 4)
- Does the theme persist across all 5 pages without a visible flash?
- Is the button icon in sync with the active theme on first load?
- Does the footer (dark green background) still look good in both modes?

---

## Step 5 — Style the toggle button in `styles.css`
Give the `#theme-toggle` button proper sizing, no default browser styles, a smooth icon transition, and hover/focus states for accessibility. Verify: button has visible focus ring, no awkward default appearance.

---

## Step 6 — Handle edge cases in `styles.css`
- Hero section: darken the overlay so the background image doesn't blow out
- Form inputs: update border/background colors under `[data-theme="dark"]`
- Card shadows: mute shadows in dark mode (dark shadows on dark bg are invisible — use colored glows instead)

---

## ✅ Self-Review Checkpoint 3 (after Step 6)
- Check every page in dark mode: hero, features cards, menu items, gallery, contact form
- Resize to mobile (375px) — does the toggle sit correctly in the nav?
- Click every interactive element in dark mode: buttons, links, form fields

---

## Step 7 — Respect `prefers-color-scheme` system preference
Add a `@media (prefers-color-scheme: dark)` block in `styles.css` that applies the dark variables **only if no manual preference is saved**. Update `script.js` to check `matchMedia` as the fallback when `localStorage` is empty. Verify: on a system set to dark mode with no saved preference, the site opens dark automatically.

---

## File Change Summary

| Step | Files Changed |
|------|--------------|
| 1 | `styles.css` |
| 2 | all 5 `.html` files |
| 3 | `script.js` |
| 4 | `script.js` |
| 5 | `styles.css` |
| 6 | `styles.css` |
| 7 | `styles.css`, `script.js` |
