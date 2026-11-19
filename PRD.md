# THI GreenAI Portal: Vibe-Coding PRD (UXD Master)

**Project Vibe (1-sentence pitch):** A friendly one-page THI web portal that shows students the energy and CO2 footprint of their everyday AI use and nudges them, with a light game layer, toward greener prompting.

**Version:** v1.0 (teaching PRD for Module 4, Part 2)
**Date:** 19.11.2026
**Author:** Prof. Dr. Ignacio Alvarez
**Origin:** Module 3 on-site exercise "THI Green AI Portal" (brainstorming + AI-assisted prototyping)
**Companion files:** `DESIGN.md` (THI design system), `AGENTS.md`, `CLAUDE.md`
**Repo:** `thi-greenai-portal` (one shared GitHub repository, one git tag per demo stage)

---

## 1) Core Context ("Master Prompt")

**Problem:** Students increasingly use LLM chatbots, image generators and AI APIs every day without any awareness of the energy, cost and environmental impact of that use.

**Solution:** The THI GreenAI Portal is a single responsive web page where students estimate their weekly AI footprint, learn six concrete "green prompting" habits, and commit to a weekly challenge that earns them a badge level.

**Target Users:** THI students (bachelor and master, all faculties); secondary: lecturers who want to discuss responsible AI use in class.

**Primary Use Cases:**
1. A student enters how they use AI in a typical week and sees an estimate of energy (Wh) and CO2 (g) with everyday equivalents.
2. A student reads practical tips to reduce that footprint.
3. A student picks weekly pledges and sees their "Green Prompter" level grow.
4. (Full-stack track only) A student submits an anonymous weekly score and sees how their faculty ranks.

**North-Star Success Metric:** Share of visitors who complete the calculator AND select at least one pledge.

**Non-Goals:** Real measurement of a user's actual AI usage; user accounts or login; collecting personal data; scientifically exact footprint numbers.

---

## 2) UX Foundations

**Personas:**
- **Lena, 22, B.Sc. Computer Science:** uses ChatGPT and Copilot many times a day, curious about numbers, likes leaderboards.
- **Jonas, 25, M.A. UX Design:** generates many images for moodboards, cares about sustainability, has no idea how much energy image generation uses.

**Top Insights / Pain Points:**
- "AI feels free and weightless." There is no feedback loop on its cost.
- Footprint numbers in the media are contradictory and abstract (kWh means nothing to most students).
- Moralizing messages cause reactance; small, positive, concrete actions work better.

**Emotional and Contextual "Vibe" Principles:** Curious, not guilty. Positive, not preachy. Concrete, not abstract. Playful, but institutional (it is a THI service).

**Accessibility and Inclusion Requirements:**
- WCAG 2.1 AA: text contrast at least 4.5:1, visible keyboard focus, all inputs with labels.
- Every slider also has a number shown as text and is operable by keyboard.
- Results are announced to screen readers (`aria-live="polite"`).
- Respect `prefers-reduced-motion`.
- Layout works at 375 px (mobile) and 1440 px (desktop).
- Optional (P2): German / English language toggle.

**High-Level Journey:** Land on hero → "Calculate my AI footprint" → adjust inputs and see live results → read tips → choose pledges → see level and badge → (full-stack) submit to faculty leaderboard.

---

## 3) Scope and Priorities

**MVP (V1) Goals:** Feature Modules F1 to F4 and F6 on a single page, no backend, state in `localStorage`.

**Full-stack track (Replit / Lovable + Supabase only):** F5 Faculty Leaderboard with a persistent database.

**Out of Scope for V1:** Login, real usage tracking, browser extensions, API integrations with AI providers, analytics, cookie banner.

**Assumptions and Risks:**
- The footprint coefficients in Section 6 are **illustrative teaching values**, not measurements. The page must say so. Risk: the AI invents "more accurate" numbers. Mitigation: the coefficients are fixed in this PRD and must be used exactly.
- Risk: different tools pick different stacks. Mitigation: the stack is fixed per track in Section 4.

---

## 4) Tech Stack and Architecture

| Layer | Static track (DeepSite, Cursor, Antigravity, Codex, Claude Code) | App-builder track (Lovable) | Full-stack track (Replit) |
|---|---|---|---|
| Frontend | HTML + CSS + vanilla JavaScript, no build step | React (Vite) + TypeScript + Tailwind + shadcn/ui (Lovable default) | React (Vite) + TypeScript + Tailwind |
| Backend | none | Supabase (only for F5) | Node.js + Express |
| Database | none (`localStorage`) | Supabase Postgres (only for F5) | Replit built-in Postgres |
| Key APIs | none | none | none |
| Deployment | GitHub Pages or local preview | Lovable publish | `*.replit.app` |
| Security / Privacy | No personal data stored. | No personal data; leaderboard entries are anonymous. | Same; validate all inputs server-side. |

**Single source of truth for numbers:** all coefficients live in one constants object (`FOOTPRINT_CONFIG`) in one file. No other file may contain these numbers.

---

## 5) Feature Modules (prompt one feature at a time)

### F1: Header and Hero (P0)
**User Story:** As a student, I want to understand in five seconds what this page does, so that I decide to try it.
**Acceptance Criteria (to-prompt checklist):**
- [ ] Sticky header with "THI GreenAI" wordmark and anchor links: Calculator, Tips, Challenge.
- [ ] Hero headline: "Use AI smart. Use AI green." and one sentence of sub-copy.
- [ ] Primary button "Calculate my AI footprint" scrolls to F2.
- [ ] Uses THI Navy `#102A63` for header/button and THI Green `#009664` as accent (see `DESIGN.md`).

### F2: AI Footprint Calculator (P0)
**User Story:** As a student, I want to estimate my weekly AI footprint, so that I see what my habits cost.
**Inputs:**
- Text prompts per day: slider 0 to 200, default 20.
- Model type: segmented control "Small / fast", "Large", "Reasoning", default "Large".
- Images generated per week: slider 0 to 50, default 5.

**Outputs (live update on every change, no submit button):**
- Energy per week in Wh (1 decimal).
- CO2 per week in g (1 decimal).
- Equivalent: smartphone charges (1 decimal).
- Equivalent: hours of a 10 W LED bulb (1 decimal).
- Disclaimer under the results: "Illustrative estimates for teaching. Real values vary by model, data center and grid."

**Formula (must be implemented exactly):**
```
weeklyWh   = promptsPerDay * 7 * WH_PER_TEXT_PROMPT[modelType] + imagesPerWeek * WH_PER_IMAGE
co2Grams   = weeklyWh / 1000 * GRID_G_CO2_PER_KWH
phoneCharges = weeklyWh / WH_PER_PHONE_CHARGE
ledHours   = weeklyWh / LED_BULB_WATTS
```

**Test vectors (acceptance tests):**
| promptsPerDay | modelType | imagesPerWeek | weeklyWh | co2Grams | phoneCharges | ledHours |
|---|---|---|---|---|---|---|
| 20 | large | 5 | 155.0 | 58.9 | 10.3 | 15.5 |
| 0 | small | 0 | 0.0 | 0.0 | 0.0 | 0.0 |
| 100 | reasoning | 10 | 3530.0 | 1341.4 | 235.3 | 353.0 |
| 50 | small | 0 | 105.0 | 39.9 | 7.0 | 10.5 |

### F3: Green Prompting Tips (P0)
**User Story:** As a student, I want concrete tips, so that I know what to change.
**Acceptance Criteria:**
- [ ] Six cards in a responsive grid (1 column mobile, 3 columns desktop), each with an icon, a title and one sentence:
  1. Right-size the model: use a small model for simple tasks.
  2. Ask once, ask well: one clear prompt beats five vague ones.
  3. Batch your questions into one conversation.
  4. Skip the regenerate loop: refine the prompt instead.
  5. Text before images: describe first, generate only when needed.
  6. Turn off reasoning mode when you do not need it.
- [ ] Cards are plain text content (no images required).

### F4: Weekly Green Challenge (P1)
**User Story:** As a student, I want to commit to small actions and see progress, so that greener AI use feels rewarding.
**Acceptance Criteria:**
- [ ] Three pledge checkboxes: "Use a small model for quick questions", "Max. 3 image generations this week", "No regenerate loops".
- [ ] Level shown as a badge plus progress bar: 0 pledges = "Seedling", 1 to 2 = "Sapling", 3 = "Forest".
- [ ] Pledges persist in `localStorage` and survive a page reload.
- [ ] A short, non-blocking celebration message when "Forest" is reached (respects reduced motion).

### F5: Faculty Leaderboard (P1, full-stack track only)
**User Story:** As a student, I want to see how my faculty compares, so that I feel part of a shared effort.
**Acceptance Criteria:**
- [ ] Form: faculty dropdown (placeholder list: Business School, Computer Science, Electrical Engineering, Mechanical Engineering, Sustainable Infrastructure; replace with THI's official faculty names) and a "Submit my week" button that sends the current weeklyWh.
- [ ] No name, email or IP is stored. Only faculty, weeklyWh, timestamp.
- [ ] Leaderboard table sorted by lowest average weeklyWh, with number of submissions.
- [ ] Server rejects weeklyWh below 0 or above 100000.

### F6: Footer and About (P0)
**Acceptance Criteria:**
- [ ] Short "About the estimates" paragraph repeating that values are illustrative.
- [ ] "A THI HCIS Lab teaching prototype" and the current year.

### F7: Language toggle DE / EN (P2, stretch)
**Acceptance Criteria:**
- [ ] Toggle in header switches all UI strings; choice persists in `localStorage`; `<html lang>` updates.

---

## 6) AI Design and Prompting Strategy

**System Prompt / Project Rules (put in AGENTS.md / CLAUDE.md / tool rules):**
"You are building the THI GreenAI Portal described in PRD.md. Follow DESIGN.md for colors and typography. Implement one feature module at a time. Never invent footprint numbers: use FOOTPRINT_CONFIG exactly. Keep the page accessible (WCAG 2.1 AA). After each feature, explain what you changed and how to test it."

**Fixed coefficients (FOOTPRINT_CONFIG, illustrative teaching values):**
```js
const FOOTPRINT_CONFIG = {
  WH_PER_TEXT_PROMPT: { small: 0.3, large: 1.0, reasoning: 5.0 },
  WH_PER_IMAGE: 3.0,
  GRID_G_CO2_PER_KWH: 380,
  WH_PER_PHONE_CHARGE: 15,
  LED_BULB_WATTS: 10
};
```

**Prompt Bank (TACO examples):** see `03_Prompt_Cards.md`.

**Reasoning Boosters:** Ask for a plan first ("Plan, do not write code yet"), then approve. For F2, ask the agent to "verify the four test vectors before finishing".

**Hallucination Mitigation and Safety:** Numbers come only from FOOTPRINT_CONFIG. No external API calls. No personal data. If the AI suggests "real" data sources, decline for V1.

**Vibe-Coding History:** Every tool session ends with a commit and a git tag (`v0-deepsite`, `v1-lovable`, `v2-cursor`, and so on). Prompts used are logged in `PROMPTS.md`.

---

## 7) IA, Flows and UI

**Information Architecture (single page):** Header → Hero (F1) → Calculator (F2) → Tips (F3) → Challenge (F4) → [Leaderboard (F5)] → Footer (F6).

**Key Flow:** Hero CTA → Calculator → results → "See how to reduce it" link → Tips → Challenge.

**Design Tokens and Components:** From `DESIGN.md`: Navy Core `#102A63` (primary), Green `#009664` (sustainability accent), Lime `#96BE00` (progress / success), Light Gray `#E5E5E5` (surfaces), Charcoal `#333333` (body text), White `#FFFFFF`. Headings serif (Georgia fallback), body sans-serif (Segoe UI / Helvetica / Arial fallback). Rounded cards (8 px radius), generous whitespace. No purple or blue gradients.

**Localization and Tone:** English default; friendly, short sentences, "you" address, no guilt language.

---

## 8) Iteration Plan and Workflow

**Build Rhythm:** One feature module per prompt. Plan → approve → build → test against acceptance criteria → commit.
**Versioning and Reviews:** One shared repo, one tag per tool stage. Review every diff before committing.
**Risk / Spike Tickets:** Font licensing (TStar is not freely available: use the fallbacks).

---

## 9) Quality: Testing, A11y, Performance

**Testing:** The four F2 test vectors must pass (unit test in the static track, manual check in app builders).
**Accessibility:** Keyboard-only walkthrough of the whole page; Lighthouse accessibility score at least 90.
**Performance Budget:** Static track page weight under 200 KB, no external JS libraries.

---

## 10) Metrics and Analytics
Out of scope for V1 (teaching prototype). North-star metric is discussed conceptually only.

## 11) Launch and Ops
Static track: GitHub Pages. Lovable: Lovable publish. Replit: `*.replit.app`. Prototype only; no production support.
