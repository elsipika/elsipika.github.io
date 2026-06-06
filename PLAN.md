# Portfolio Plan

## Goal

Full-featured personal portfolio for Selina Sun, junior software and QA engineer, built on `elsipika.github.io`.

## Completed

- [x] Rewrote `index.html` with updated content from resume (2026-04 version)
- [x] Added 4th nav tab: Projects
- [x] Updated Home section: current bio, Resume PDF link, GitHub link
- [x] Updated About section: full skill breakdown (Web, Testing, AI/ML, Backend, Tools), interests, languages
- [x] Updated Works section: SCRUM24, Waymo, Trillion Innovations, Digital Media Academy, UCSC education, certifications
- [x] Added Projects section with 3 showcase project cards
- [x] Added GitHub + LinkedIn SVG icons (replacing Twitter/Instagram)
- [x] Updated footer social links (GitHub, LinkedIn placeholder, email `mailto:`)
- [x] Replaced `#text06` paragraph tags with semantic `.section-heading` class
- [x] Added skill group layout (`.skill-group`, `.skill-label`, `.skill-list`)
- [x] Added project card styles (`.project-card`, `.tech-tags`, `.tech-tag`)
- [x] Widened card from 32rem to 36rem to accommodate 4-tab nav and project cards
- [x] Wrote `README.md`, `CLAUDE.md`, `PLAN.md`, `SOUL.md`

## Remaining / Next Steps

- [ ] Create GitHub repo: `elsipika/iot-solar-dashboard` (Next.js IoT admin console)
- [ ] Publish/update GitHub repo: `elsipika/qagogo-agent` (web and mobile QA automation demo)
- [ ] Create GitHub repo: `elsipika/ai-image-studio` (PyTorch image classifier)
- [ ] Add LinkedIn profile URL to footer icon `href` (currently `#`)
- [ ] Add a profile photo or custom avatar (replace Skitty GIF if desired, or keep for personality)
- [ ] Add Open Graph image for social sharing preview

## Three Showcase Projects

### 1. IoT Solar Dashboard
**Repo:** `elsipika/iot-solar-dashboard`
**Why:** Directly demonstrates SCRUM24 work — IoT device management, real-time data, modern frontend stack. Strongest signal of professional frontend experience.
**Suggested scope:** Next.js app shell, sidebar nav, mock device list with status badges, simple line chart for telemetry, TypeScript throughout.

### 2. Playwright/Detox QA Suite
**Repo:** `elsipika/qagogo-agent`
**Why:** Proves QA engineering skills across web and mobile with real automated flows, seeded bugs, and readable findings.
**Current scope:** Local BunnyBoard web/mobile demo apps, Playwright web E2E, Detox native iOS E2E, source-based mobile checks, seeded product bugs, and report-ready QA findings.
**Next polish:** Add screenshots/report artifacts to the README and keep Android Detox clearly marked as scaffolded until a native Android build is generated.

### 3. AI Image Studio
**Repo:** `elsipika/ai-image-studio`
**Why:** Ties creative interests (art + design) to AI/ML credentials from UCSC. Shows full-stack range — Python ML backend + React UI.
**Suggested scope:** Saved PyTorch checkpoint from UCSC clothing classifier, Flask API endpoint, minimal React upload UI that returns top-3 predictions with confidence scores.
