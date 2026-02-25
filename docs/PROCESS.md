# PROCESS Reflection — Week 5 (Claude Web + Micro-Iteration)

## What I built
I added a dark mode toggle to my Moonlight Matcha Cafe multi-page static site. The feature adds a theme button in the navigation, switches the site color palette using CSS variables, updates the icon and aria-pressed state, and saves the user’s preference in localStorage so it persists across refreshes and page navigation.

## Micro-iteration experience
Micro-iteration felt slower at first, but it was easier to stay organized because each step had a clear “done” point. Doing it in small chunks also made it easier to take screenshots and understand what changed, instead of getting a giant code dump I didn’t fully follow.

## What self-review caught (and patterns)
Self-review caught real issues I would have missed. The biggest example was that my dark-mode variable overrides accidentally broke the footer and CTA section. The review correctly identified that `--dark-green` was being used for both headings and background areas, so overriding it for readability caused the footer background to turn mint and made text contrast confusing. A smaller self-review catch was accessibility: it recommended adding `aria-pressed` and setting an initial value in the HTML. A pattern I noticed is that self-review often caught design/UX and accessibility issues (contrast, semantics, consistency) more than syntax errors.

## One issue I caught myself
I personally got stuck on previewing changes because Claude Web worked on a separate branch. My local site looked unchanged until I created/merged a pull request and pulled the updated main branch.

## Browser tool vs CLI
Claude Web was convenient for planning and making multi-file edits, but the branch/PR workflow added extra steps compared to the CLI, where changes feel more direct and immediate. CLI is better when I want tight feedback loops on my own machine, while Claude Web is nice when I want guided edits with clear diffs.

## When I’d use this workflow
I’d use micro-iteration + self-review for features that touch multiple files or UX, where small mistakes can spread quickly. I’d skip it for simple one-line fixes or setup tasks where a larger prompt is faster.
