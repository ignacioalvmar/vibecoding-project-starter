# AGENTS.md: THI GreenAI Portal

## Read first
- PRD.md: what to build (feature modules F1 to F7, acceptance criteria, test vectors)
- DESIGN.md: THI design system (colors, typography, components)

## Commands
- Static version: open index.html, or run `npx serve .`
- React version: `npm install`, `npm run dev`, `npm test`

## Rules
- Build one feature module at a time. Plan first, then implement.
- Footprint numbers come ONLY from FOOTPRINT_CONFIG (PRD.md section 6). Never invent or "correct" them.
- Colors only through design tokens (THI navy #102A63, green #009664, lime #96BE00, gray #E5E5E5, charcoal #333333, white). No raw hex in components. No purple or blue gradients.
- Accessibility: WCAG 2.1 AA, labels on inputs, visible focus, aria-live on results, prefers-reduced-motion.
- Never add new dependencies without asking.
- No personal data. No external API calls.

## Definition of done
- Acceptance criteria of the feature are met.
- Test vector 1 (20 prompts/day, large, 5 images) shows 155.0 Wh and 58.9 g CO2.
- Works at 375 px and 1440 px.
- Changes committed with a meaningful message; prompts logged in PROMPTS.md.
