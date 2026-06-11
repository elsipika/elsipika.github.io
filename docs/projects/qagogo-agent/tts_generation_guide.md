# QAgogo → Selina Voice: Generation Guide

**Goal:** regenerate the narration of `qagogo_jerry.mp4` in Selina's cloned voice, producing `qagogo_selina.mp4`. The video track stays untouched — only the audio is replaced.

## Step 1 — Clone the voice

Upload `selina_voice_reference.wav` (89 s of clean continuous speech, mono 44.1 kHz) to your cloning tool — e.g. ElevenLabs **Instant Voice Clone**, PlayHT, or a local model like XTTS-v2 / F5-TTS. If the tool accepts more material, also add `selina_full_narration.mp3` (full 3:53 track). Levels are already healthy (mean −23.6 dB, peaks −0.9 dB), no preprocessing needed.

## Step 2 — Generate 10 clips

Generate each block below as a **separate file** with the exact filename shown. Keep each clip within its duration budget (the time available before the next on-screen change). A second or two over is fine — I can compensate during assembly — but if a clip runs far over, regenerate it with a slightly faster pace.

| # | Filename | Starts at | Budget | Text to generate |
|---|----------|-----------|--------|------------------|
| 1 | `01_slide1.mp3` | 0:03 | ≤ 19 s | QAgogo is a QA automation agent for web and mobile apps. It suggests coverage, runs Playwright and Detox flows, captures evidence, and exports an HTML QA report with bugs and recommendations. |
| 2 | `02_slide2.mp3` | 0:23 | ≤ 16 s | This project shows my ability to build and verify both web and mobile product surfaces. The stack connects React, React Native, Playwright, and Detox into one working QA portfolio project. |
| 3 | `03_slide3.mp3` | 0:39 | ≤ 20 s | This is the BunnyBoard React dashboard tested with Playwright. The headed web run checks login, filters, task actions, validation, sync errors, and responsive behavior with 14 passing tests. |
| 4 | `04_slide4.mp3` | 1:00 | ≤ 19 s | This is BunnyBoard Mobile, a React Native app tested with Detox on the iOS simulator. The mobile run checks login, dashboard state, add task, complete task, sync error, and empty-title validation with 6 passing tests. |
| 5 | `05_slide5.mp3` | 1:20 | ≤ 21 s | The tests expose product risks, including empty-password login, count mismatch, missing due-time validation, and a vague sync error. QAgogo turns those results into report-ready bugs with steps, evidence, and suggested fixes. |
| 6 | `06_slide6.mp3` | 1:42 | ≤ 13 s | This project shows I can build, debug, deliver, and demo an end-to-end product suite. It also shows communication skill, because test results become clear risks, fixes, and evidence. |
| 7 | `07_mobile_intro.mp3` | 1:55 | ≤ 12 s | I run npm run test mobile e2e iOS to show Detox driving the native BunnyBoard Mobile iOS app. |
| 8 | `08_mobile_result.mp3` | 3:05 | ≤ 10 s | This run covers six mobile workflows and completes with 6 passing tests. |
| 9 | `09_web_intro.mp3` | 3:13 | ≤ 12 s | I run npm run test web e2e in headed mode to show Playwright driving the BunnyBoard React app in a visible browser. |
| 10 | `10_web_result.mp3` | 3:32 | ≤ 12 s | This run covers core web workflows and completes with 14 passing tests. |

**Notes**

- Clips 1–6 match the slide deck (slides change at ~0:22, 0:39, 1:00, 1:20, 1:42, demo starts ~1:55).
- The original narrator ad-libs extra commentary during the mobile demo (1:55–3:05); the silent gap there is the Detox run executing, so the cleaner script reads fine. If you want extra commentary lines over the demo footage, generate them as additional clips and tell me roughly where they go.
- Commands are written out phonetically (`test mobile e2e iOS` instead of `test:mobile:e2e:ios`) so the TTS doesn't stumble on colons and flags. If your tool reads the literal command well, feel free to use the original wording from `qagogo_script.txt`.
- The script differs slightly from what was actually spoken — that's fine, since the entire audio track is being replaced. Only timing against the visuals matters, and the table reflects the actual video.

## Step 3 — Send the clips back

Upload the 10 files (mp3 or wav, either is fine) to this chat. I'll place each at its anchor point on a silent 3:55 timeline, match loudness across clips, nudge or micro-stretch anything that overruns, and mux the new track with the untouched video stream into **`qagogo_selina.mp4`**.
