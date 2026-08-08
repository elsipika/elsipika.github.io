# CLAUDE.md — elsipika.github.io

Portfolio website for Selina Sun. Pure static HTML/CSS/JS, no build system.

## Architecture

Single `index.html` file. All CSS is inline in `<style>`. All JS is inline in `<script>`. The JS handles section-switching: only one `<section>` is visible at a time, toggled via hash navigation (`#home`, `#about`, `#works`, `#projects`).

**Section ID convention:** each nav hash maps to `[name]-section`. Adding a new section `#foo` requires a `<section id="foo-section">` in the DOM.

## Design system

| Token | Value | Usage |
|-------|-------|-------|
| Card bg | `#caabdf` | `#main` background |
| Border/overlay | `#E5BEFA` | Card border, accent color |
| Accent text | `#bc8cd6` | H1, project card headings |
| Body text | `white` | All body copy |
| Subtle text | `rgba(255,255,255,0.6–0.88)` | Dates, secondary info |
| Card width | `36rem` | `#main > .inner` width |
| Font: display | VT323 | Section headings, pixel aesthetic |
| Font: body | Roboto Condensed | All body text, buttons |

## Key CSS classes

- `.section-heading` — VT323 section labels (replaces old `#text06`)
- `.skill-group` / `.skill-label` / `.skill-list` — skill block layout
- `.project-card` — project showcase card
- `.tech-tags` / `.tech-tag` — pill tags inside project cards
- `.project-footer` / `.project-status` / `.project-link` — card bottom row
- `#buttons01` — 4-item nav (6rem wide each)
- `#buttons02` — CTA buttons on home (Resume, GitHub)
- `#icons01` — footer social icon circles

## Mini game — Feed the Bunny

Lives at the end of `#home-section`, anchored by `<div data-scroll-id="mini-game">`. Self-contained IIFE in the main `<script>` block; nothing outside it references the game.

**Loop:** treats and hazards fall down 4 lanes; move the bunny with `←`/`→`, the lane buttons, or by tapping the field. Catching a treat scores `points × combo` (combo caps at x5); catching a hazard resets the combo and can cost a life. Dodging a hazard is worth +1. Missing a treat breaks the combo.

**Brain breaks:** every 12 resolved items the field clears and a quiz overlay opens. `QUIZ_SETS` holds three categories — QA, IQ, Frontend — 12 questions each, cycled in order by `checkpointCount`, shuffled options, no repeats until a set is exhausted. A correct answer is +10 points and +1 life; a wrong one costs nothing and shows the explanation. Each break also bumps `level`, which raises fall speed and spawn rate.

The user-facing name is **"brain break"**, shown as `Brain break · QA` from each set's `tag`. Keep it category-neutral outside the tag — the fourth stat tile is labelled `Quiz` and counts all three categories, so wording like "QA checkpoints" there would be wrong.

**Intro panel:** `#intro-panel` is the idle view — it lists every item's point value, the controls, combo, lives and brain-break rules. `.bunny-field` carries `is-intro` in the HTML so the rules show even before JS runs. Start dismisses it; the `How to play` button toggles it back (pausing a run first). Its point values are hand-written, so they must be kept in sync with `TREATS` — the test suite asserts they match.

**Bunny sprite gotcha:** `images/rabbit.gif` is 32×32 with the GIF transparency flag **off**, so it renders as an opaque white square. It is clipped to a circle via `border-radius: 50%` on the `img` plus `image-rendering: pixelated` to stay crisp when upscaled. Don't remove that clipping expecting a transparent sprite.

**Audio:** synthesized at runtime via Web Audio — no files. A square-lead/triangle-bass loop over Am–F–C–G plus per-event effects. Starts only on the Start click (never on page load) and the mute state persists in `localStorage` under `bunny-sound`.

**Key IDs:** `#bunny-field`, `#field-sky`, `#bunny-runner`, `#lane-buttons`, `#quiz-overlay`, `#bunny-score` / `-lives` / `-combo` / `-quiz`, `#bunny-start` / `-stop` / `-restart` / `-sound`.

**Gotcha:** `step()` clears `rafId` at the top of every frame. Anything that stops the loop mid-frame (a checkpoint, game over) must return without rescheduling, or `startLoop()` sees a stale `rafId` and the game silently freezes.

## SVG icons

Defined inline in `<svg display="none">`. Current icons:
- `#icon-email` — email envelope
- `#icon-github` — GitHub octocat
- `#icon-linkedin` — LinkedIn

Referenced via `<use xlink:href="#icon-name">`.

## Important constraints

- No build step. Edit `index.html` directly. Changes are live immediately via GitHub Pages.
- The section-switching JS is sensitive to `id` attributes. Never rename section IDs without updating the hash navigation logic.
- Keep all CSS inside the single `<style>` block — external stylesheets break GitHub Pages caching behavior for this project.
- Do not add `onclick` or JS-based routing — the existing `hashchange` listener handles all navigation.

## Content locations

- Home bio: `#home-section > p#text03`
- About skills: `.skill-group` elements in `#about-section`
- Work history: `#works-section > p#text02`
- Projects: `.project-card` divs in `#projects-section`
- Footer social links: `#icons01` anchor hrefs
- Resume PDF link: `#buttons02 li:first-child a` href

## Updating projects

Each project card follows this structure:
```html
<div class="project-card">
    <h3>Project Title</h3>
    <p>Description sentence or two.</p>
    <div class="tech-tags">
        <span class="tech-tag">Tech</span>
    </div>
    <div class="project-footer">
        <span class="project-status">Status label</span>
        <a href="https://github.com/..." class="project-link" target="_blank" rel="noopener">View on GitHub →</a>
    </div>
</div>
```
