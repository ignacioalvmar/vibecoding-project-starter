# Design System Inspired by Technische Hochschule Ingolstadt

## 1. Visual Theme & Atmosphere

The Technische Hochschule Ingolstadt design system embodies institutional authority with modern accessibility. It combines deep navy foundations with clean geometric shapes and purposeful accent colors that signal different academic domains. The aesthetic is professional yet approachable, leveraging white space and diagonal compositional elements to convey forward momentum and innovation. Typography balances serif warmth with contemporary sans-serif clarity, while the color palette extends beyond primary branding to include semantic signals for different program areas and institutional functions. The overall impression is one of established excellence paired with contemporary relevance—a university that honors tradition while embracing digital transformation.

**Key Characteristics**

- Authoritative navy blue as the dominant institutional color
- Multi-hued accent palette representing different academic disciplines
- Geometric diagonal compositions and layered visual depth
- Clean typography hierarchy with serif and contemporary sans-serif mixing
- Accessible contrast ratios maintained across interactive elements
- Generous whitespace supporting scannability and digital clarity

## 2. Color Palette & Roles

### Primary

- **Navy Core** (`#102A63`): Primary institutional color used extensively across navigation, buttons, and structural elements. Establishes authority and academic credibility.
- **Navy Alternative** (`#007382`): Secondary navy variant used for accent borders and alternative interactive states.

### Accent Colors

- **Teal** (`#0091AC`): Technology and innovation accent; used for interactive highlights and modern initiatives.
- **Cyan** (`#009BCD`): Digital transformation accent; signals forward-thinking programs.
- **Burgundy** (`#871932`): Heritage and tradition accent; used sparingly for premium program callouts.
- **Orange** (`#F08200`): Warmth and engineering focus; used for specific program highlights.
- **Green** (`#009664`): Sustainability and life sciences programs; signals environmental focus.
- **Lime** (`#96BE00`): Innovation and future-focused programs; energetic and contemporary accent.

### Interactive

- **Navy Button** (`#102A63`): Primary call-to-action background; ensures clear hierarchy and accessibility.
- **Link Text Navy** (`#102A63`): Semantic color for hyperlinks in body copy and navigation.
- **Charcoal Interactive** (`#333333`): Secondary interactive elements and text-based buttons; subtle but accessible.

### Neutral Scale

- **Charcoal** (`#333333`): Primary body text and navigation text; ensures readability.
- **Black** (`#000000`): High-contrast text and critical typography.
- **White** (`#FFFFFF`): Primary background and text overlay on dark surfaces.
- **Light Gray** (`#E5E5E5`): Subtle background fills and border tints; minimal visual weight.

### Surface & Borders

- **Navy Border** (`#102A63`): Form inputs and structural dividers; maintains visual hierarchy.
- **Gray Border** (`#E5E5E5`): Subtle surface separations; reduces visual noise.

### Semantic / Status

- **Error Red** (`#E6320F`): Error states and critical warnings; high urgency signal.
- **Warning Yellow** (`#FFDE00`): Warning states; moderate attention required.
- **Warning Secondary** (`#D7D700`): Alternative warning signal for less critical alerts.
- **Caution Lime** (`#BEF500`): Caution and secondary warning states; visible but not alarming.

## 3. Typography Rules

### Font Family

**Primary Font Stack (TStar family)**
`'TStar-Medium', 'TStar-Medium-Italic', 'TStar-italic', serif, Georgia, 'Times New Roman'`

**Secondary Font Stack (News Cycle)**
`'News Cycle', 'Segoe UI', Helvetica, Arial, sans-serif`

**Monospace Fallback**
`'Courier New', Courier, monospace`

### Hierarchy

| Role | Font | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|------|--------|-------------|-----------------|-------|
| Display / H1 | TStar-italic | 32px | 500 | 34px | 0px | Page titles and hero headlines; strong visual anchor |
| Heading 2 | TStar-Medium-Italic | 24px | 400 | 33.6px | 0px | Section breaks and major subsections |
| Heading 3 | TStar-Medium | 30px | 500 | 45px | 0px | Content section headers; prominent but subordinate to H2 |
| Heading 4 | TStar-italic | 20px | 700 | 19px | 0px | Tertiary headings and card titles |
| Body Large | TStar-Medium | 17px | 400 | 25.5px | 0px | Primary body copy and descriptive text |
| Body Regular | News Cycle | 17px | 400 | 26px | 0px | Secondary body copy and longer descriptions |
| Label / Button Text | News Cycle | 17px | 700 | 26px | 0px | Form labels, button labels, and emphasis text |
| Link Text | News Cycle | 16px | 400 | 20px | 0px | Hyperlinks in body and navigation |
| Input / Form | News Cycle | 14px | 400 | 18px | 0px | Text input placeholder and input values |
| List Item | TStar-italic | 16px | 400 | 22px | 0px | Bulleted and numbered list items |
| Caption / Meta | News Cycle | 14px | 400 | 18px | 0px | Captions, bylines, and metadata |
| Headline Special | News Cycle | 25.5px | 700 | 25.5px | 0px | Large promotional text and hero headlines |

### Principles

- **Serif-first leadership**: TStar family (serif) dominates headings and display text, establishing institutional gravitas and readability in print-inspired layouts.
- **Sans-serif utility**: News Cycle (contemporary sans) handles body, forms, and digital interaction—balancing warmth with clarity.
- **Generous line height**: 1.5× to 1.6× scale ensures accessibility and reduces cognitive load on longer reads.
- **Weight contrast**: Heavy reliance on weight shifts (400 to 700) rather than size alone for visual hierarchy, supporting scannability.
- **Italic emphasis**: TStar italic variants add visual interest to headings without increasing color contrast complexity.

## 4. Component Stylings

### Buttons

**Primary Button (Navy Filled)**
- Background: `#102A63`
- Text Color: `#FFFFFF`
- Font Family: TStar-Medium
- Font Size: 17px
- Font Weight: 400
- Line Height: 17px
- Padding: `10px 20px 10px 20px`
- Border Radius: `0px`
- Border: `0px none`
- Box Shadow: `none`
- Hover State: Background `#0A1A40`, Text `#FFFFFF`
- Active State: Background `#0F2450`, Text `#FFFFFF`
- Disabled State: Background `#CCCCCC`, Text `#FFFFFF`, Opacity `0.6`

**Secondary Button (Ghost Navy)**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#102A63`
- Font Family: News Cycle
- Font Size: 16px
- Font Weight: 400
- Line Height: 20px
- Padding: `0px 0px 0px 0px`
- Border Radius: `0px`
- Border: `0px none`
- Box Shadow: `none`
- Hover State: Text Color `#0A1A40`, Text Decoration `underline`
- Active State: Text Color `#0F2450`
- Disabled State: Text Color `#CCCCCC`, Opacity `0.6`

**Tertiary Button (Charcoal Text)**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#333333`
- Font Family: News Cycle
- Font Size: 17px
- Font Weight: 400
- Line Height: 26px
- Padding: `17px 0px 0px 0px`
- Border Radius: `0px`
- Border: `0px none`
- Box Shadow: `none`
- Hover State: Text Color `#102A63`, Text Decoration `underline`
- Active State: Text Color `#0A1A40`
- Disabled State: Text Color `#CCCCCC`, Opacity `0.6`

**Icon Button (Minimal)**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#333333`
- Font Family: News Cycle
- Font Size: 17px
- Font Weight: 400
- Line Height: 26px
- Padding: `9px 10px 9px 10px`
- Border Radius: `4px`
- Border: `0px none`
- Box Shadow: `none`
- Hover State: Background `#F0F0F0`, Text Color `#102A63`
- Active State: Background `#E5E5E5`, Text Color `#0A1A40`
- Disabled State: Text Color `#CCCCCC`, Opacity `0.6`

### Cards & Containers

**Standard Card**
- Background: `#FFFFFF`
- Border: `1px solid #E5E5E5`
- Border Radius: `0px`
- Padding: `24px`
- Box Shadow: `none`
- Hover State: Box Shadow `rgba(0, 0, 0, 0.1) 0px 2px 8px 0px`

**Featured Card (Navy Accent)**
- Background: `#102A63`
- Border: `0px none`
- Border Radius: `0px`
- Padding: `40px 40px 40px 40px`
- Text Color: `#FFFFFF`
- Box Shadow: `none`
- Heading Color: `#FFFFFF`
- Hover State: Box Shadow `rgba(0, 0, 0, 0.2) 0px 4px 12px 0px`

**Content Container**
- Background: `#FFFFFF`
- Padding: `52px 40px 52px 40px`
- Max Width: `1200px`
- Margin: `0 auto`
- Border: `none`

### Inputs & Forms

**Text Input (Default)**
- Background: `#FFFFFF`
- Border: `1px solid #102A63`
- Border Radius: `0px`
- Padding: `8px 10px 8px 10px`
- Font Family: News Cycle
- Font Size: 14px
- Font Weight: 400
- Line Height: 18px
- Text Color: `#000000`
- Placeholder Color: `#999999`
- Height: `auto`
- Width: `100%`
- Focus State: Border Color `#0091AC`, Box Shadow `0px 0px 0px 2px rgba(0, 145, 172, 0.2)`

**Text Input (Error)**
- Background: `#FFFFFF`
- Border: `1px solid #E6320F`
- Border Radius: `0px`
- Text Color: `#000000`
- Focus State: Box Shadow `0px 0px 0px 2px rgba(230, 50, 15, 0.2)`

**Checkbox / Radio**
- Background: `#FFFFFF`
- Border: `1px solid #102A63`
- Border Radius: `2px`
- Checked State: Background `#102A63`, Border Color `#102A63`, Checkmark Color `#FFFFFF`

**Select Dropdown**
- Background: `#FFFFFF`
- Border: `1px solid #102A63`
- Border Radius: `0px`
- Padding: `8px 10px 8px 10px`
- Font Family: News Cycle
- Font Size: 14px
- Text Color: `#000000`

**Form Label**
- Font Family: News Cycle
- Font Size: 17px
- Font Weight: 700
- Line Height: 26px
- Text Color: `#333333`
- Margin Bottom: `8px`

### Navigation

**Main Navigation Bar**
- Background: `rgba(0, 0, 0, 0)` (transparent)
- Height: `132px`
- Width: `855px`
- Display: flex
- Align Items: center
- Font Family: News Cycle
- Font Size: 17px
- Font Weight: 400
- Line Height: 26px
- Text Color: `#333333`

**Navigation Item (Active)**
- Background: `#102A63`
- Text Color: `#FFFFFF`
- Padding: `8px 12px 8px 12px`
- Border Radius: `0px`

**Navigation Item (Hover)**
- Background: `#F0F0F0`
- Text Color: `#102A63`
- Transition: `background-color 0.2s ease-in-out`

**Navigation Link**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#333333`
- Font Family: News Cycle
- Font Size: 16px
- Font Weight: 400
- Line Height: 20px
- Text Decoration: none
- Hover State: Text Color `#102A63`, Text Decoration `underline`

### Links

**Primary Link (Navy)**
- Background: `#102A63`
- Text Color: `#FFFFFF`
- Font Family: News Cycle
- Font Size: 16px
- Font Weight: 400
- Line Height: 20px
- Padding: `0px`
- Text Decoration: none
- Hover State: Text Decoration `underline`, Opacity `0.9`

**Body Link (Charcoal)**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#333333`
- Font Family: News Cycle
- Font Size: 17px
- Font Weight: 400
- Line Height: 26px
- Text Decoration: none
- Border Bottom: `1px solid currentColor`
- Hover State: Text Color `#102A63`, Opacity `0.8`

**Secondary Link (Navy Text)**
- Background: `rgba(0, 0, 0, 0)`
- Text Color: `#102A63`
- Font Family: News Cycle
- Font Size: 16px
- Font Weight: 400
- Line Height: 20px
- Text Decoration: none
- Hover State: Text Decoration `underline`, Opacity `0.8`

## 5. Layout Principles

### Spacing System

**Base Unit:** `4px`

**Spacing Scale:**
- `4px`: Micro-spacing (icon padding, tight groups)
- `8px`: Extra-small (input padding, button gaps)
- `12px`: Small (component internal spacing, list gaps)
- `16px`: Standard (padding, button padding)
- `20px`: Medium (section margins, card spacing)
- `24px`: Large (card padding, section gaps)
- `32px`: Extra-large (component spacing, section breaks)
- `40px`: Hero (major container padding, feature spacing)
- `52px`: Major (full section top/bottom, page breaks)
- `100px`: Massive (hero section padding, feature breaks)
- `136px`: Extra-massive (landing section spacing)
- `152px`: Grand (large container padding, major breaks)

**Context Usage:**
- Micro to small (`4px–12px`): Form inputs, icon spacing, tight lists
- Standard to large (`16px–32px`): Card padding, navigation spacing, body sections
- Extra-large to massive (`40px–152px`): Hero sections, container wrapping, page-level breaks

### Grid & Container

**Max Width:** `1200px`
**Column Strategy:** 12-column grid with flexible gutters
**Container Padding:** `40px` on desktop (20px on tablet, 16px on mobile)
**Section Patterns:** Full-width hero sections alternate with contained content blocks
**Asymmetric Layouts:** Diagonal compositional elements (60deg angles) used in hero sections; offset grid for dynamic visual rhythm

### Whitespace Philosophy

Whitespace is leveraged as a primary design element to improve scannability and cognitive clarity. Generous margins between sections reduce visual noise and allow complex information to breathe. Card-based layouts isolate content blocks with consistent 24px padding and subtle gray borders, encouraging users to process information in digestible chunks. Hero sections employ large padding (52px to 100px) and layered diagonal backgrounds to create immersive entry points. Negative space around typography—particularly heading-to-body transitions—follows a 1.5× to 2× line-height scale, ensuring text remains readable and visually separated.

### Border Radius Scale

- `0px`: Structural elements, buttons, cards, inputs, navigation (institutional sharpness)
- `2px`: Checkbox and radio button corners (subtle roundness for small interactive elements)
- `4px`: Icon buttons, micro-interactions (gentle, non-obtrusive)
- `6px`: Modal and overlay containers (slightly rounded for interface softness)

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (0) | `none` | Base surfaces, cards, navigation, primary containers |
| Hover / Hover Lift (+1) | `rgba(0, 0, 0, 0.1) 0px 2px 8px 0px` | Card hover states, button emphasis, interactive feedback |
| Elevated Modal / Overlay (+2) | `rgba(0, 0, 0, 0.5) 0px 5px 15px 0px` | Modals, overlays, dropdown menus, floating panels |
| Hero / Deep Lift (+3) | `rgba(0, 0, 0, 0.2) 0px 4px 12px 0px` | Featured cards, promoted content, visual anchors |

**Shadow Philosophy**

Depth is used sparingly and intentionally to support information hierarchy without introducing visual clutter. Most elements remain flat on the base plane, maintaining clarity and institutional restraint. Shadows appear only on interactive hover states and modal layers, signaling actionability and temporal layering. The shadow palette uses soft, diffused blurs (8px–15px) rather than sharp drops, creating a sophisticated lift effect that suggests digital elegance. No elements use strong directional shadows; all shadows remain centered, supporting a modern, layered aesthetic that avoids skeuomorphic depth.

## 7. Do's and Don'ts

### Do

- Use `#102A63` navy as the foundational structural color for buttons, navigation, and primary calls-to-action
- Apply generous padding (`24px` to `52px`) around content blocks to ensure readability and visual breathing room
- Maintain 1.5× to 1.6× line height on all body text; prioritize accessibility and legibility
- Employ TStar serif fonts for headings and display text to establish institutional authority
- Use accent colors (`#0091AC`, `#009664`, `#96BE00`) to denote specific academic programs and thematic areas
- Test interactive states (hover, focus, active, disabled) on all buttons and links to ensure full accessibility
- Keep border radius at `0px` for major structural elements; reserve `4px` rounding for icon buttons and micro-interactions
- Layer cards and containers with `24px` padding and subtle `#E5E5E5` borders for clean separation
- Use News Cycle sans-serif for form labels, body copy, and digital-first content
- Employ diagonal compositional elements (geometric shapes at 60deg) in hero sections for dynamic visual movement

### Don't

- Never use navy (`#102A63`) and charcoal (`#333333`) text on each other without a minimum 4:5.1 contrast boost; always test WCAG AA compliance
- Avoid mixing TStar and News Cycle fonts within a single heading or body paragraph; maintain consistent font families per role
- Don't apply rounded corners (`border-radius > 0px`) to standard buttons and cards; preserve institutional sharpness
- Never apply box shadows to base-level elements; restrict shadows to hover states, modals, and featured cards
- Avoid using accent colors as primary call-to-action backgrounds; reserve `#102A63` for all primary buttons
- Don't exceed line heights of 1.6× on body text; over-spacing reduces cohesion and increases perceived page length
- Never apply more than two levels of shadow depth on a single page; excessive layering creates visual confusion
- Avoid placing white text on light gray backgrounds; maintain minimum 7:1 contrast for critical content
- Don't use all accent colors simultaneously in a single section; limit to one or two complementary program signals per region
- Never apply padding of less than `8px` to form inputs; insufficient internal spacing reduces usability

## 8. Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | `< 640px` | Single-column layout; container padding `16px`; navigation stacks vertically; heading font sizes reduce by 20%; button padding `8px 16px` |
| Tablet | `640px – 1024px` | Two-column grid; container padding `20px`; navigation becomes horizontal with compact spacing; heading font sizes reduce by 10%; section padding `32px 20px` |
| Desktop | `1024px – 1440px` | 12-column grid; container padding `40px`; full navigation bar with `132px` height; standard heading sizes; full spacing scale active |
| Wide / Large Desktop | `> 1440px` | Max width `1200px` enforced; centered container; full spacing and typography scale; hero sections employ asymmetric layouts |

### Touch Targets

- Minimum tap target size: `44px × 44px` (recommended for mobile)
- Button padding minimum: `8px 10px 8px 10px` (desktop); scale to `12px 16px 12px 16px` (mobile)
- Link padding minimum: `4px` internal padding on smaller links; ensure surrounding whitespace reaches `44px` when clicked
- Form input minimum height: `40px` (including padding) for comfortable mobile interaction
- Navigation item spacing: `12px` horizontal gap between links (mobile); `16px` (desktop)

### Collapsing Strategy

**Mobile (< 640px):**
- Navigation collapses into hamburger menu; main nav items stack vertically in offscreen drawer
- Hero sections reduce padding from `52px` to `24px`; diagonal compositions flatten to vertical stacks
- Multi-column card layouts collapse to single column
- Section margins reduce from `52px` to `32px`; heading sizes reduce by 15–20%
- Input field width constrained to `calc(100% - 16px)` with left/right margin

**Tablet (640px – 1024px):**
- Navigation remains horizontal but condenses; link padding reduces to `8px 12px`
- Two-column layouts activate for card grids; three-column grids collapse to two
- Hero section padding reduces to `40px`; headline size reduces by 10%
- Section padding reduces to `32px` vertical, `20px` horizontal
- Form input full width with reduced padding

**Desktop (> 1024px):**
- Full horizontal navigation with `132px` height and `132px` nav bar
- Three-column card grids and complex layouts fully active
- Hero sections employ full asymmetric diagonal compositions
- All typography sizes at full scale
- Standard spacing scale (4px base unit) fully active

## 9. Agent Prompt Guide

### Quick Color Reference

- **Primary CTA Button**: Navy Core (`#102A63`)
- **Body Text**: Charcoal (`#333333`)
- **Heading Text**: TStar Serif in Charcoal (`#333333`)
- **Background (Default)**: White (`#FFFFFF`)
- **Background (Featured)**: Navy Core (`#102A63`)
- **Accent (Technology)**: Teal (`#0091AC`)
- **Accent (Sustainability)**: Green (`#009664`)
- **Link Text**: Navy Core (`#102A63`)
- **Border**: Light Gray (`#E5E5E5`) or Navy Core (`#102A63` for form inputs)
- **Error State**: Error Red (`#E6320F`)
- **Warning State**: Warning Yellow (`#FFDE00`)

### Iteration Guide

1. **Establish the navy foundation**: All primary buttons, main navigation, and structural elements use `#102A63` background with `#FFFFFF` text; no exceptions for accessibility compliance.

2. **Apply serif hierarchy**: Use TStar-Medium for body copy (17px, line-height 25.5px) and TStar-italic for headings (H1: 32px, H3: 30px, H4: 20px); reserve News Cycle sans-serif for forms, labels, and digital-first content.

3. **Implement zero-radius structure**: Apply `border-radius: 0px` to all buttons, cards, navigation, and major containers; restrict rounding to `4px` only on icon buttons and micro-interactions.

4. **Scale spacing strategically**: Use base 4px unit with scale increments (4, 8, 12, 16, 20, 24, 32, 40, 52, 100, 136, 152px); card padding defaults to 24px; hero sections use 40–100px; responsive collapse at tablet/mobile breakpoints.

5. **Shadow hierarchy only on interactions**: Keep base surfaces flat (no shadow); apply soft shadows only to hover states (`rgba(0, 0, 0, 0.1) 0px 2px 8px 0px`) and modals/overlays (`rgba(0, 0, 0, 0.5) 0px 5px 15px 0px`).

6. **Use accent colors as program signals**: Assign accents (Teal `#0091AC`, Green `#009664`, Orange `#F08200`) to specific academic disciplines; never as primary CTAs, only as secondary visual anchors.

7. **Maintain 1.5–1.6× line height on all body text**: Ensures accessibility and reduces cognitive load; headings follow proportional scaling (H1: 1.06×, H3: 1.5×, body: 1.5×).

8. **Test all interactive states**: Implement hover, focus (outline: 2px solid accent), active, and disabled states on every button, link, and form control; disabled state uses 60% opacity and `#CCCCCC` color.

9. **Prioritize contrast ratios**: Navy text on white achieves 8.2:1; charcoal on white achieves 9:1; all links and interactive text meet WCAG AA minimum 4.5:1; error states use `#E6320F` with minimum 7:1 on white.

10. **Responsive collapse follows breakpoint strategy**: Mobile (< 640px) single-column, Tablet (640–1024px) two-column, Desktop (> 1024px) full grid; heading sizes reduce 20% on mobile, 10% on tablet; container padding 16px mobile, 20px tablet, 40px desktop.