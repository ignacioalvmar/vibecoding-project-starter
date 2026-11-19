# Prompt Cards: THI GreenAI Portal (Module 4, Part 2)

Copy-paste ready. One card = one prompt. Card codes match the Instructor Guide.

---

## [K] Kick-off prompt (identical for Lovable, Replit and DeepSite)

Self-contained on purpose: DeepSite cannot read files, and the bake-off is only fair if every tool gets the same words.

```
Build a single-page, responsive website called "THI GreenAI Portal" for students of Technische Hochschule Ingolstadt (THI).

Goal: show students the energy and CO2 footprint of their everyday AI use and give them tips to use AI more sustainably. Tone: curious and positive, never guilt-tripping.

Sections, in this order:
1. Sticky header with the wordmark "THI GreenAI" and anchor links: Calculator, Tips, Challenge.
2. Hero: headline "Use AI smart. Use AI green.", one sentence of sub-copy, and a primary button "Calculate my AI footprint" that scrolls to the calculator.
3. AI Footprint Calculator with live results (no submit button):
   - Inputs: text prompts per day (slider 0-200, default 20); model type (segmented control: small, large, reasoning; default large); images generated per week (slider 0-50, default 5).
   - Use exactly these constants, do not invent other numbers:
     WH_PER_TEXT_PROMPT = { small: 0.3, large: 1.0, reasoning: 5.0 }, WH_PER_IMAGE = 3.0, GRID_G_CO2_PER_KWH = 380, WH_PER_PHONE_CHARGE = 15, LED_BULB_WATTS = 10
   - weeklyWh = promptsPerDay * 7 * WH_PER_TEXT_PROMPT[model] + imagesPerWeek * WH_PER_IMAGE
   - Show four result cards (1 decimal): energy per week (Wh), CO2 per week (g = weeklyWh / 1000 * 380), smartphone charges (weeklyWh / 15), hours of a 10 W LED bulb (weeklyWh / 10).
   - Under the results: "Illustrative estimates for teaching. Real values vary by model, data center and grid."
4. Green Prompting Tips: six cards (1 column on mobile, 3 on desktop): Right-size the model; Ask once, ask well; Batch your questions; Skip the regenerate loop; Text before images; Turn off reasoning mode when you do not need it. One sentence each.
5. Footer: "A THI HCIS Lab teaching prototype" and a short note that all values are illustrative.

Design: THI design language. Primary Navy #102A63 (header, buttons), accent Green #009664, success Lime #96BE00, surfaces #E5E5E5, body text #333333 on white. Serif headings (Georgia fallback), sans-serif body (Segoe UI, Helvetica, Arial). Rounded cards, generous whitespace, no purple or blue gradients.

Accessibility: WCAG 2.1 AA contrast, labels on all inputs, visible keyboard focus, results announced with aria-live="polite", respect prefers-reduced-motion. Must look good at 375 px and 1440 px.

Check before you finish: with 20 prompts/day, large model and 5 images/week the page must show 155.0 Wh and 58.9 g CO2.
```

---

## Lovable

**[L1] Plan F4 in Chat mode (no credits wasted on code)**
```
Investigate but do not write code yet. Plan how to add a "Weekly Green Challenge" section between Tips and Footer:
- Three pledge checkboxes: "Use a small model for quick questions", "Max. 3 image generations this week", "No regenerate loops".
- Level badge + progress bar: 0 pledges = Seedling, 1-2 = Sapling, 3 = Forest.
- Pledges persist in localStorage and survive reload.
- Short non-blocking celebration message at Forest, respecting prefers-reduced-motion.
List the components you will create or change and how I can test it.
```
**[L2] Build it (Builder mode)**
```
Implement the plan for the Weekly Green Challenge exactly as described. Do not change other sections.
```

---

## Replit

**[R1] Add to the end of [K] (stack line)**
```
Stack: React (Vite) + TypeScript + Tailwind for the frontend, Node.js + Express backend, Replit Postgres database. Propose a plan first and wait for my approval.
```
**[R2] F5 Faculty Leaderboard**
```
Add a "Faculty Leaderboard" section after the Tips.
- Form: faculty dropdown (Business School, Computer Science, Electrical Engineering, Mechanical Engineering, Sustainable Infrastructure) and a "Submit my week" button that sends the current weeklyWh from the calculator.
- Store only faculty, weeklyWh and timestamp. No names, emails or IP addresses.
- Server-side validation: reject weeklyWh < 0 or > 100000 with a clear error message.
- Table sorted by lowest average weeklyWh, showing faculty, average Wh (1 decimal) and number of submissions.
Show me the plan first. After building, tell me how to test it with two submissions.
```

---

## DeepSite

**[D1] Add to the end of [K]**
```
Deliver everything as one single index.html file with inline CSS and vanilla JavaScript. No frameworks, no external libraries, no build step.
```

---

## Cursor

**[C1] Ask mode: understand before changing**
```
Explain the architecture of this project in 5 bullets: stack, folder structure, where the calculator logic lives, where colors are defined, and anything that contradicts PRD.md or DESIGN.md.
```
**[C2] Plan mode: design-token refactor**
```
Using @DESIGN.md and @PRD.md: refactor the styling so that no raw hex color appears in components. Create (or update) one design-token source: CSS variables or the Tailwind theme, matching the THI palette: navy #102A63, green #009664, lime #96BE00, gray #E5E5E5, charcoal #333333, white #FFFFFF. Replace every hard-coded color with a token. Do not change layout or behavior. Show the plan first, then implement file by file.
```
**[C3] Commit**
```
Commit my changes to git with a short but meaningful commit message that references the token refactor.
```

---

## Antigravity

**[A1] F7 language toggle with browser verification**
```
Read PRD.md (feature F7) and DESIGN.md. Create an implementation plan artifact first and wait for my approval.
Then add a DE / EN language toggle in the header:
- All UI strings come from one translations object (en, de). Translate all visible text, including tips and disclaimers.
- The choice persists in localStorage and updates the <html lang> attribute.
- Numbers in German use a decimal comma (155,0 Wh).
When done, open the page in the browser, switch to DE and back to EN, and give me screenshots as proof.
```

---

## Codex

**[X0] Initialize**
```
/init
```
**[X1] Accessibility audit, then fix**
```
Audit this site against WCAG 2.1 AA and the accessibility requirements in PRD.md section 2. First output a numbered list of issues with file and line, severity (high / medium / low) and the fix you propose. Then fix all high and medium issues. Do not add dependencies. Finish with how I can verify each fix with the keyboard only.
```
**[X2] Review**
```
/review
```

---

## Claude Code

**[CC1] Plan mode (Shift+Tab): tests for the calculator**
```
Read PRD.md section 5, feature F2. Plan how to make the calculator logic testable and cover it with unit tests for the four test vectors in the table. Use Node's built-in test runner; no new dependencies. If a test fails, fix the code, not the test. Keep FOOTPRINT_CONFIG as the only place where the coefficients live.
```
**[CC2] Verify visually**
```
Run the site, take screenshots at 375 px and 1440 px width, and check them against PRD.md section 7 and DESIGN.md. List anything that does not match, fix it, and show me before/after.
```
**[CC3] Wrap up**
```
Add the prompts used in this session to PROMPTS.md, commit with a meaningful message and tag the commit v5-claude.
```

---

## Universal debugging prompt (any tool)

```
Something is wrong: [describe what you see vs. what you expected].
Here is the full error message / a screenshot: [paste].
First explain the likely cause in 2-3 sentences. Do not change code until I confirm.
```
