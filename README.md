# elsipika.github.io — Selina Sun Portfolio

Personal portfolio website for Selina Sun, software engineer and QA engineer.

**Live:** https://elsipika.github.io

---

## Sections

| Tab | Content |
|-----|---------|
| Home | Intro, bio, resume + GitHub links |
| About | Technical skills, interests, languages |
| Works | Work experience, education, certifications |
| Projects | Three showcase projects |

## Stack

Pure HTML/CSS/JavaScript — no build step, no dependencies, deploys directly via GitHub Pages.

Fonts: VT323 (pixel headings), Roboto Condensed (body), Space Mono — all from Google Fonts.

## Local development

```bash
# Any static file server works
npx serve .
# or
python3 -m http.server 8080
```

Open http://localhost:8080

## Suggested Project Repos

These three repos are showcased in the Projects tab and should be created separately:

| Repo | Description | Stack |
|------|-------------|-------|
| `elsipika/iot-solar-dashboard` | IoT device monitoring admin console | Next.js, TypeScript, Tailwind CSS |
| `elsipika/qagogo-agent` | Playwright/Detox QA suite for web and mobile apps | React, React Native, Expo, Playwright, Detox |
| `elsipika/ai-image-studio` | CNN image classifier web app | Python, PyTorch, VGG16, React, Flask |

`qagogo-agent` is the most QA-focused showcase repo: it includes a BunnyBoard demo web app, a BunnyBoard Expo/React Native mobile app, Playwright browser flows, Detox native iOS E2E, static mobile checks, and documented seeded findings.

## File structure

```
elsipika.github.io/
├── index.html              # Main portfolio (single page)
├── images/
│   ├── lavender.jpg        # Background
│   ├── skitty.gif          # Home section
│   ├── gameboy.gif         # About section
│   └── laptop.gif          # Works / Projects sections
└── docs/cv_resume/
    ├── Selina_Sun_Resume_*.pdf
    └── Selina_Sun_Cover_Letter_*.pdf
```

## Updating content

All content is inline in `index.html`. Key areas:
- **Home bio:** `#home-section > #text03`
- **Skills:** `.skill-group` divs in `#about-section`
- **Work history:** `#works-section > #text02`
- **Projects:** `.project-card` divs in `#projects-section`
- **Social links:** `#footer > #icons01` and `#home-section > #buttons02`

Update the LinkedIn href in the footer once the profile URL is known.
