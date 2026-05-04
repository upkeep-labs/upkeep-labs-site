# Upkeep Labs Design System

## 1. Visual Theme & Atmosphere

Upkeep Labs presents as a **warm, approachable software studio** — professional but human, confident without being corporate. The site uses a two-tone architecture: a dark shell (header/footer) frames a warm, light content area, creating natural visual hierarchy without heavy design. The dark chrome signals technical credibility while the warm interior says "real people work here."

The tone is **builder-friendly** — short, confident copy without buzzwords. The brand identity is faceless (no team photos or personal names), letting the work speak for itself. Each venture (FlightPack, Beyond the Commit, Flight Deck Labs) brings its own brand color through its logo, while the site itself stays neutral and consistent.

**Key Characteristics:**
- Two-tone layout: dark header/footer (`#0f1117`) + warm light content (`#f5f3f0`)
- Inter as the sole typeface — clean, readable, modern without being cold
- Indigo accent (`#6366f1`) as the only site-level brand color — used for links, badges, labels
- Venture logos provide color variety naturally (teal, navy, purple) — the site doesn't compete
- Conservative border-radius (8px buttons, 12px cards) — rounded but not bubbly
- Subtle hover transitions (0.2s) on all interactive elements
- No gradients, no decorative elements, no illustrations — content-first

## 2. Color Palette & Roles

### Dark Chrome (Header & Footer)
- **Background** (`#0f1117`): Primary dark surface. Header, footer, CTA button.
- **Surface** (`#1a1d27`): Elevated dark elements, card dark variants.
- **Border** (`#2a2d3a`): Borders and dividers on dark surfaces.
- **Text** (`#e4e4e7`): Primary text on dark backgrounds.
- **Text Muted** (`#9ca3af`): Secondary text, nav links, footer links on dark.

### Warm Light (Main Content)
- **Background** (`#f5f3f0`): Primary light surface. Hero, about section.
- **Background Alt** (`#eae7e3`): Slightly darker warm. "Our Work" section background.
- **Surface** (`#ffffff`): Cards and elevated content containers.
- **Border** (`#d6d3d1`): Card borders, dividers on light surfaces.
- **Text** (`#1c1917`): Primary headings and body text on light.
- **Text Muted** (`#57534e`): Secondary text, descriptions, captions on light.

### Accent
- **Indigo** (`#6366f1`): Links, section labels, badges, hover accents. The only "brand" color.
- **Indigo Hover** (`#818cf8`): Lighter indigo for hover states on links and accents.
- **Indigo Tint** (`rgba(99, 102, 241, 0.1)`): Badge backgrounds, subtle accent fills.

### Stats Bar
- **Background** (`#f0ede9`): Stats bar background within featured cards.

## 3. Typography Rules

### Font Family
- **Primary**: `Inter`, with fallback: `system-ui, -apple-system, sans-serif`
- **Source**: Google Fonts (`wght@400;500;600;700`)
- **Rendering**: `-webkit-font-smoothing: antialiased`

### Hierarchy

| Role | Size | Weight | Line Height | Letter Spacing | Color | Notes |
|------|------|--------|-------------|----------------|-------|-------|
| Hero Headline | clamp(2rem, 5vw, 3.25rem) | 700 | 1.15 | -0.03em | `#1c1917` | Responsive scaling, one per page |
| Section Heading | 1.75rem | 700 | default | -0.02em | `#1c1917` | "What we're building", "Built by builders." |
| Card Heading (Featured) | 1.3rem | 700 | default | normal | `#1c1917` | FlightPack card title |
| Card Heading | 1.2rem | 700 | default | normal | `#1c1917` | Venture card titles |
| Hero Subline | 1.125rem | 400 | 1.6 | normal | `#57534e` | Max-width 560px, centered |
| Body | 1rem | 400 | 1.8 | normal | `#57534e` | About section paragraphs, max-width 640px |
| Card Body | 0.9rem | 400 | 1.7 | normal | `#57534e` | Card descriptions |
| CTA Button | 0.95rem | 600 | default | normal | `#ffffff` | "Get in touch" |
| Nav Link | 0.875rem | 500 | default | normal | `#9ca3af` | Header navigation |
| Card Link | 0.875rem | 500 | default | normal | `#6366f1` | "beyondthecommit.com →" |
| Section Label | 0.8rem | 600 | default | 0.1em | `#6366f1` | "OUR WORK", "ABOUT" — uppercase |
| Stat Label | 0.65rem | 400 | default | 0.05em | `#57534e` | "PLATFORM", "SIMULATORS" — uppercase |
| Stat Value | 0.8rem | 400 | default | normal | `#1c1917` | "Desktop + Web", "MSFS · X-Plane" |
| Badge | 0.65rem | 600 | default | 0.05em | `#6366f1` | "LAUNCHING SOON" — uppercase, pill |
| Footer Text | 0.8rem | 400 | default | normal | `#9ca3af` | Copyright, footer links |

### Principles
- **One typeface**: Inter handles everything. No secondary font.
- **Weight restraint**: 400 for body, 500 for UI/nav, 600 for buttons/labels, 700 for headings only.
- **Negative tracking on headings**: -0.03em on hero, -0.02em on section headings. Body text is normal.
- **Uppercase sparingly**: Only section labels, stat labels, and badges. Never headings or body.

## 4. Component Stylings

### Venture Card (Side-Column Logo)
All three venture cards share this layout — logo as a left column, text content to the right.

- Background: `#ffffff`
- Border: `1px solid #d6d3d1`
- Radius: 12px
- Overflow: hidden
- Layout: `display: flex` (horizontal, stacks vertical on mobile)
- Hover: border shifts to `#6366f1`, shadow `0 4px 24px rgba(0,0,0,0.06)`
- Transition: `0.2s` on box-shadow and border-color

**Logo Column:**
- Width: 180px (featured), 180px (standard)
- Padding: 28px
- Background: white (logos bring their own color)
- Image: `width: 100%`, `border-radius: 12px`

**Body Column:**
- Padding: 28px
- Flex: 1
- Vertical centering via `justify-content: center`

### Featured Card (FlightPack)
Extends the venture card with an additional stats bar spanning the full bottom.

- Structure: `.featured-card-top` (flex row: logo + body) + `.stats-bar` (full width)
- Stats bar background: `#f0ede9`
- Stats bar border-top: `1px solid #d6d3d1`
- Stats bar padding: `14px 28px`
- Stats bar layout: `display: flex`, `gap: 32px`
- Stat items: centered text, label above value

### Badge (Pill)
- Background: `rgba(99, 102, 241, 0.1)`
- Text: `#6366f1`
- Padding: `2px 8px`
- Radius: 99px (full pill)
- Font: 0.65rem, weight 600, uppercase
- Width: fit-content

### CTA Button
- Background: `#0f1117`
- Text: `#ffffff`
- Padding: `12px 28px`
- Radius: 8px
- Font: 0.95rem, weight 600
- Hover: background `#2a2d3a`
- Transition: `0.2s` on background

### Links
- Color: `#6366f1`
- Hover: `#818cf8`
- No underline
- Arrow suffix: ` →` (using `&rarr;`)
- Transition: `0.2s` on color

## 5. Layout Principles

### Container
- Max-width: 960px
- Margin: `0 auto`
- Padding: `0 24px`

### Section Spacing
- Hero: `100px 0 80px` (generous breathing room)
- Content sections: `80px 0`
- Mobile sections: reduced to `48px 0` / `64px 0 48px`

### Card Grid
- Standard cards: `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))`
- Gap: 24px
- Featured card: full-width, standalone with `margin-bottom: 24px`

### Content Width Constraints
- Hero subline: `max-width: 560px`, centered
- About paragraphs: `max-width: 640px`, left-aligned

### Spacing Patterns
- Section label to heading: 12px
- Heading to content: 48px (work section), 20px (about section)
- Paragraph spacing: 16px between paragraphs
- Card body elements: 8-10px between heading/description, 16px to link

## 6. Depth & Elevation

The design is intentionally **flat** with minimal elevation. Depth is communicated through background color changes (dark → light → slightly darker light) rather than shadows.

### Shadows
- **Card hover only**: `0 4px 24px rgba(0,0,0,0.06)` — very subtle, warm-toned
- **No resting shadows**: Cards are flat at rest, elevated only on hover
- **No layered shadows**: Single shadow layer keeps things simple

### Surface Hierarchy (top to bottom)
1. Dark header (`#0f1117`)
2. Hero (`#f5f3f0`)
3. Our Work section (`#eae7e3`) — slightly darker to create separation
4. Cards (`#ffffff`) — pop against the `#eae7e3` background
5. Stats bar (`#f0ede9`) — slightly recessed within cards
6. About (`#f5f3f0`) — returns to primary light
7. Dark footer (`#0f1117`)

## 7. Do's and Don'ts

### Do
- **Let logos speak**: Venture logos bring their own color (teal, navy, purple). The site stays neutral.
- **Keep copy short**: One sentence per idea. No paragraphs over 2 lines on desktop.
- **Use the two-tone structure**: Dark chrome for framing, warm light for content. Don't mix.
- **Stay faceless**: No team member names, photos, or personal attribution. The studio speaks as "we."
- **Use indigo as the sole accent**: Links, labels, badges, hover borders — all `#6366f1`.
- **Maintain card consistency**: All venture cards use the same side-column logo layout.

### Don't
- **Don't add background colors behind logos**: The logos are colorful enough. White column backgrounds only.
- **Don't use gradients**: No CSS gradients anywhere. Flat colors only.
- **Don't introduce new accent colors**: No teal, purple, or navy as site-level accents, even if a venture uses them.
- **Don't add team photos or bios**: The site is intentionally faceless for now.
- **Don't use dark cards in light sections**: The FlightPack card was moved from dark to light — keep all content-area cards on white backgrounds.
- **Don't use shadows at rest**: Only on hover. Flat by default.
- **Don't add decorative illustrations or icons**: Content only. No SVG illustrations, no emoji, no decorative dividers.

## 8. Responsive Behavior

### Breakpoint
- Single breakpoint: `600px` (mobile threshold)

### Mobile Adaptations
- **Header**: Stacks vertically (logo above nav), `gap: 16px`
- **Nav links**: Reduced left margin (16px instead of 32px), first child has no margin
- **Hero**: Padding reduces to `64px 0 48px`
- **Venture cards**: Flex direction changes to `column` — logo stacks above text
- **Logo column**: Becomes `width: 100%`, `height: 160px` (centered)
- **Stats bar**: Items stack vertically, centered, `gap: 12px`
- **Content sections**: Padding reduces to `48px 0`
- **Footer links**: Wrap naturally via `flex-wrap: wrap`
- **Card grid**: Single column (auto-fit handles this naturally)

### Touch Targets
- CTA button: `12px 28px` padding — comfortable tap target
- Nav links: adequate spacing via margins
- Card links: 16px top margin provides separation from description

## 9. Agent Prompt Guide

### Quick Color Reference
```
Dark bg:      #0f1117
Dark surface: #1a1d27
Dark border:  #2a2d3a
Light bg:     #f5f3f0
Light alt bg: #eae7e3
Card bg:      #ffffff
Card border:  #d6d3d1
Stats bar bg: #f0ede9
Text dark:    #1c1917
Text muted:   #57534e
Text on dark: #e4e4e7
Text muted dk:#9ca3af
Accent:       #6366f1
Accent hover: #818cf8
Accent tint:  rgba(99,102,241,0.1)
```

### When Adding a New Venture Card
1. Use the `.venture-card` class with side-column logo layout
2. Logo column: white background, 180px wide, 28px padding, image with 12px border-radius
3. Body column: 28px padding, heading (1.2rem/700), description (0.9rem/400 muted), link (accent color with →)
4. Do NOT add a colored background behind the logo
5. If it's a featured/flagship product, wrap in `.featured-card` with a `.stats-bar`

### When Adding a New Section
1. Alternate backgrounds: `#f5f3f0` → `#eae7e3` → `#f5f3f0`
2. Start with `.section-label` (uppercase, accent color) then `h2`
3. Content within `.container` (960px max-width)
4. Padding: `80px 0` desktop, `48px 0` mobile

### When Writing Copy
- Lead with what we do, not who we are
- One sentence descriptions. No fluff.
- Use "we" not "I" or specific names
- Links use → arrow suffix
- Warm but professional — "we'd love to hear from you" not "contact us today"

### CSS Variables Available
```css
--color-bg: #0f1117;
--color-surface: #1a1d27;
--color-border: #2a2d3a;
--color-text: #e4e4e7;
--color-text-muted: #9ca3af;
--color-accent: #6366f1;
--color-accent-hover: #818cf8;
--color-main-bg: #f5f3f0;
--color-main-text: #1c1917;
--color-main-muted: #57534e;
--color-main-border: #d6d3d1;
--color-main-surface: #ffffff;
```
