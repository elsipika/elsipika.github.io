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
