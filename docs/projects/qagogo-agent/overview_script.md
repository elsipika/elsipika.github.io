# QAgogo Agent Overview Script

Target length: about 1 minute.

## 60-second talk track

Hi, this is QAgogo Agent, a Playwright and Detox QA suite built around a small product called BunnyBoard.

The main point of this project is to show that Selina can both build product surfaces and verify them. On the web side, BunnyBoard is a React task dashboard with login, filtering, task creation, completion states, validation cases, and seeded bugs. Playwright tests cover realistic user flows, invalid input, responsive layout, and state changes.

On the mobile side, BunnyBoard Mobile is a React Native app with a real login flow and phone-sized workflow. Detox is used to validate native iOS behavior, so the QA coverage is not limited to browser simulation.

The automation output is turned into clear QA findings: login accepts an empty password, completed count is off by one, due time is not validated, and the sync error message is too vague. Each finding can include severity, environment, reproduction steps, expected versus actual behavior, evidence, and a suggested fix.

So the portfolio takeaway is simple: Selina can build, debug, deliver, and demo an end-to-end product suite, including web app, mobile app, and end-to-end web and mobile automated testing.

## Slide pacing

- Slide 1: 5 seconds - introduce QAgogo Agent.
- Slide 2: 10 seconds - state the capability signal: React, React Native, Playwright, Detox.
- Slide 3: 12 seconds - explain the web app and Playwright coverage.
- Slide 4: 12 seconds - explain the mobile login flow and Detox coverage.
- Slide 5: 11 seconds - show how checks become QA findings.
- Slide 6: 10 seconds - close with why hire Selina.

## Mobile and web test demo script

Target length: about 1 minute.

This is the combined mobile and web test demo for BunnyBoard.

On the mobile side, BunnyBoard Mobile is built with React Native, and Detox validates the real iOS app flow. The demo starts at the login screen, checks the email, password, and sign-in controls, then moves into the care-task workflow. This shows that native screens, state changes, accessibility labels, and error cases can be tested repeatedly.

On the web side, BunnyBoard is a React task dashboard tested with Playwright. The demo covers login, filtering, task creation, completion behavior, validation states, sync error handling, and responsive layout. These are realistic user actions, not isolated unit checks.

The key takeaway is that Selina can build both product surfaces and test both product surfaces. Detox proves the mobile app behavior, Playwright proves the web app behavior, and the failures become clear QA findings with reproduction steps, expected versus actual results, evidence, and suggested fixes.
