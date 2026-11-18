# this design system UI Style Guide

## A reusable design system for clean, premium, Apple-inspired websites

A practical UI reference based on the visual direction used for
**this design system**. Use it as a starting point for personal projects,
portfolio websites, SaaS landing pages, dashboards, and student
projects.

The goal is not to copy this design system page-for-page. The goal is to reuse
its design principles: clear hierarchy, restrained colour, generous
spacing, rounded surfaces, purposeful layouts, and subtle motion.

------------------------------------------------------------------------

## 1. Design philosophy

The principles in this section define the visual foundation of the Laksh Apple UI Guide. Apply them consistently, while adapting each decision to the needs of the product and its audience.

### The visual direction

-   **Minimal, not empty:** use whitespace intentionally, while making
    every section feel complete.
-   **Premium, not flashy:** rely on typography, alignment, spacing, and
    composition rather than decorative effects.
-   **Product-led:** show the actual product or interface wherever
    possible. For a SaaS site, a believable dashboard mockup is more
    useful than a generic stock illustration.
-   **Consistent, not repetitive:** use a shared design system, but vary
    section composition when it improves the story.
-   **Motion with purpose:** animations should guide attention or
    communicate state, not distract from the content.

### Avoid the "vibe-coded" look

Avoid: - random gradients, glowing blobs, and excessive glassmorphism; -
the same three-column card layout in every section; - oversized shadows
on every element; - decorative icons that communicate nothing; -
arbitrary spacing and inconsistent corner radii; - fake metrics or
product claims presented as verified facts; - animations on every
element just because an animation library is available.

Prefer deliberate art direction, a consistent spacing scale, believable
content, and a small number of strong visual moments.

------------------------------------------------------------------------

## 2. Colour system

Use a restrained neutral palette with one primary accent. These are the
this design system starting colours; adjust them only when the brand requires it.

  -----------------------------------------------------------------------
  Token                   Colour                  Typical use
  ----------------------- ----------------------- -----------------------
  Page background         `#F5F5F7`               Main page canvas

  Surface                 `#FFFFFF`               Cards, panels,
                                                  navigation

  Primary text            `#171717`               Headlines and important
                                                  text

  Secondary text          `#77777D`               Descriptions, metadata

  Accent blue             `#477BFF`               Primary actions, links,
                                                  highlights

  Dark surface            `#111113`               Contrast sections and
                                                  dark product previews

  Border                  `#E8E8EA`               Dividers, card
                                                  outlines, input borders
  -----------------------------------------------------------------------

### Colour rules

1.  Use the page background for the overall canvas and white for
    elevated content surfaces.
2.  Reserve accent blue for actions, links, selected states, and a few
    key highlights.
3.  Use secondary text for supporting information, not for essential
    instructions that need strong contrast.
4.  Use the dark surface selectively to create contrast between major
    sections.
5.  Do not introduce extra accent colours without a clear functional
    reason.
6.  Check text contrast, especially for small labels and muted text.

### CSS variables

``` css
:root {
  --color-bg: #F5F5F7;
  --color-surface: #FFFFFF;
  --color-text: #171717;
  --color-muted: #77777D;
  --color-accent: #477BFF;
  --color-dark: #111113;
  --color-border: #E8E8EA;
}
```

------------------------------------------------------------------------

## 3. Typography

Use a clean sans-serif typeface. **Inter** or **Manrope** are good
starting choices.

### Type hierarchy

  Role                      Suggested desktop size     Weight
  ----------------- ------------------------------ ----------
  Hero headline       `clamp(2.8rem, 6vw, 5.5rem)`   600--700
  Section heading      `clamp(2rem, 4vw, 3.25rem)`   600--700
  Card heading                    `1.15rem–1.4rem`        600
  Body copy                        `1rem–1.125rem`        400
  Supporting text               `0.875rem–0.95rem`        400
  Small labels                  `0.75rem–0.825rem`   500--600

### Typography rules

-   Keep hero headlines short and confident.
-   Use a comfortable line height for paragraphs (usually around
    `1.5–1.7`).
-   Tighten line height for large headings (usually around `1.0–1.15`).
-   Limit paragraph width so long lines do not become difficult to read.
-   Use weight and size to create hierarchy before adding colour.
-   Avoid using too many font families or weights.

Example:

``` css
body {
  font-family: Inter, Manrope, -apple-system, BlinkMacSystemFont,
    "Segoe UI", sans-serif;
  color: var(--color-text);
  background: var(--color-bg);
  line-height: 1.6;
}

h1,
h2,
h3 {
  line-height: 1.1;
  letter-spacing: -0.035em;
}
```

------------------------------------------------------------------------

## 4. Spacing and layout

Use a consistent spacing scale instead of choosing random values.

  Token          Value
  ------------ -------
  `space-1`        4px
  `space-2`        8px
  `space-3`       12px
  `space-4`       16px
  `space-5`       20px
  `space-6`       24px
  `space-8`       32px
  `space-10`      40px
  `space-12`      48px
  `space-16`      64px
  `space-20`      80px
  `space-24`      96px

### Container

-   Use a centred content container.
-   Start with a maximum width of approximately `1200px`.
-   Add responsive side padding.
-   Keep section content aligned to the same container edges.

``` css
.container {
  width: min(100% - 48px, 1200px);
  margin-inline: auto;
}

.section {
  padding-block: clamp(64px, 9vw, 112px);
}

@media (max-width: 600px) {
  .container {
    width: min(100% - 36px, 1200px);
  }
}
```

### Layout principles

-   Give major sections enough vertical breathing room.
-   Align headings, cards, and content to a consistent grid.
-   Use whitespace to separate ideas rather than adding unnecessary
    divider lines.
-   Keep text blocks readable and avoid stretching paragraphs across the
    full screen.
-   Use asymmetry when it creates a clear focal point; do not make
    layouts uneven without a reason.

------------------------------------------------------------------------

## 5. Corners, borders, and shadows

Rounded corners are a key part of the style, but they should follow a
system.

  Component                         Suggested radius
  --------------------------- ----------------------
  Large section panels                      32--40px
  Feature and content cards                 20--28px
  Inputs                                    12--16px
  Buttons                       Pill-shaped or 999px
  Small tags                                   999px

Use subtle borders to define surfaces. Shadows should be soft and
selective, not applied to every card.

``` css
.card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: 24px;
}

.surface-shadow {
  box-shadow: 0 12px 36px rgba(20, 20, 30, 0.06);
}
```

------------------------------------------------------------------------

## 6. Buttons and interaction states

### Primary button

-   Accent-blue background.
-   White text.
-   Pill-shaped corners.
-   Clear, concise label.
-   Visible hover, focus, and pressed states.

### Secondary button

-   White or transparent background.
-   Dark text.
-   Subtle border.
-   Same height and corner treatment as the primary button.

``` css
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 48px;
  padding: 0 24px;
  border: 1px solid transparent;
  border-radius: 999px;
  font: inherit;
  font-weight: 600;
  text-decoration: none;
  transition:
    transform 180ms ease,
    background-color 180ms ease,
    border-color 180ms ease;
}

.button-primary {
  color: #fff;
  background: var(--color-accent);
}

.button-primary:hover {
  transform: translateY(-2px);
}

.button-secondary {
  color: var(--color-text);
  background: var(--color-surface);
  border-color: var(--color-border);
}

.button:focus-visible {
  outline: 3px solid rgba(71, 123, 255, 0.35);
  outline-offset: 3px;
}
```

Every element that looks clickable must do something meaningful. Do not
leave decorative buttons or dead links in the final website.

------------------------------------------------------------------------

## 7. Cards and bento layouts

Use cards to group related information, not as a default wrapper for
every piece of content.

### Card guidelines

-   Use consistent internal padding.
-   Keep headings and descriptions visually distinct.
-   Use a subtle border and a clean surface.
-   Add an illustration, chart, or UI preview only when it helps explain
    the feature.
-   Keep card content concise.
-   Use a restrained hover state only if the card is interactive or
    benefits from feedback.

### Bento layout

An asymmetric grid can create visual interest while maintaining
structure. A useful pattern is one larger feature card alongside two
smaller cards, but the exact arrangement should fit the content.

``` css
.feature-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 20px;
}

.feature-card--large {
  grid-column: span 2;
}

@media (max-width: 760px) {
  .feature-grid {
    grid-template-columns: 1fr;
  }

  .feature-card--large {
    grid-column: auto;
  }
}
```

Do not force every feature into the same card size. Let the importance
and content determine the layout.

------------------------------------------------------------------------

## 8. Navigation and hero sections

### Navigation

-   Keep the logo and primary navigation easy to locate.
-   Use concise labels.
-   Make the main call to action visually distinct.
-   On mobile, use a clear menu control with an accessible name and
    working open/close behaviour.
-   Ensure navigation links lead to real sections or pages.

### Hero

A strong hero usually contains: 1. A short headline that communicates
the value proposition. 2. A supporting sentence or two. 3. One primary
action and, optionally, one secondary action. 4. A product preview,
dashboard, or visual that explains what the product does.

Avoid filling the hero with unrelated badges, floating decorations, and
multiple competing calls to action.

------------------------------------------------------------------------

## 9. Product previews and dashboards

For SaaS and productivity websites, a custom dashboard preview can make
the product feel tangible.

A dashboard may include: - a simple sidebar; - a clear page title or
welcome message; - a small number of useful summary cards; - a task or
project list; - one chart or progress visual; - a recent activity or
insight panel.

Keep the interface believable. Use sample data when needed, but label it
as sample or illustrative data. Do not imply that integrations, AI
features, security certifications, analytics, or performance results are
real unless they have actually been implemented and verified.

------------------------------------------------------------------------

## 10. Dark contrast sections

A dark section can break up a mostly light website and create a strong
visual moment.

Use: - the dark surface colour (`#111113`); - high-contrast headings; -
muted but readable supporting text; - a limited use of the accent
colour; - one focused product visual or metric group.

Do not make every section dark. The contrast works because it is used
selectively.

------------------------------------------------------------------------

## 11. Motion, GSAP, and smooth scrolling

Motion should feel calm and intentional.

### Suitable effects

-   Fade and slight upward movement when sections enter the viewport.
-   Small staggered reveals for related cards.
-   A restrained hero or dashboard entrance.
-   Subtle hover feedback on interactive cards and buttons.
-   Gentle parallax only when it improves depth and does not affect
    readability.

### Motion rules

-   Prefer `transform` and `opacity` for animation.
-   Avoid animating layout-heavy properties such as `width`, `height`,
    `top`, and `left` when possible.
-   Do not animate every element.
-   Avoid scroll hijacking.
-   Keep animations short and subtle.
-   Support `prefers-reduced-motion`.
-   If using Lenis with GSAP ScrollTrigger, integrate their scroll
    updates correctly and avoid creating multiple competing animation
    loops.

Example reduced-motion CSS:

``` css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

------------------------------------------------------------------------

## 12. Responsive behaviour

Design for small screens from the start, rather than treating mobile as
a compressed desktop layout.

Test at these viewport widths:

-   360px
-   390px
-   430px
-   768px
-   1024px
-   1440px

Check: - no horizontal page overflow; - readable headings and body
text; - buttons that fit and are easy to tap; - cards that stack in a
logical order; - dashboard previews that remain legible; - mobile
navigation that opens and closes; - charts and decorative elements that
do not get clipped; - forms and footer links that fit the viewport.

Use flexible widths, `minmax()`, `clamp()`, and responsive grid changes
rather than fixed desktop dimensions.

------------------------------------------------------------------------

## 13. Accessibility and quality checks

Before shipping a website:

-   Use semantic HTML (`header`, `nav`, `main`, `section`, `footer`).
-   Give form controls visible labels.
-   Make interactive elements keyboard accessible.
-   Provide visible focus states.
-   Add useful alternative text to meaningful images.
-   Maintain sufficient text contrast.
-   Do not rely on colour alone to communicate state.
-   Respect reduced-motion preferences.
-   Check that every link and button works.
-   Check the browser console for errors.
-   Test the production build, not only the development server.

Do not claim accessibility compliance unless you have actually tested
against the relevant standard.

------------------------------------------------------------------------

## 14. Starter CSS foundation

This is a compact starting point. Add component-specific styles as the
project grows.

``` css
:root {
  --color-bg: #F5F5F7;
  --color-surface: #FFFFFF;
  --color-text: #171717;
  --color-muted: #77777D;
  --color-accent: #477BFF;
  --color-dark: #111113;
  --color-border: #E8E8EA;

  --radius-card: 24px;
  --radius-panel: 36px;
  --radius-pill: 999px;

  --container-width: 1200px;
  --page-gutter: 24px;

  --shadow-soft: 0 12px 36px rgba(20, 20, 30, 0.06);
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  color: var(--color-text);
  background: var(--color-bg);
  font-family: Inter, Manrope, -apple-system, BlinkMacSystemFont,
    "Segoe UI", sans-serif;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
}

img,
svg,
video {
  display: block;
  max-width: 100%;
}

button,
input,
textarea,
select {
  font: inherit;
}

.container {
  width: min(calc(100% - 2 * var(--page-gutter)), var(--container-width));
  margin-inline: auto;
}

.section {
  padding-block: clamp(64px, 9vw, 112px);
}

.card {
  border: 1px solid var(--color-border);
  border-radius: var(--radius-card);
  background: var(--color-surface);
}

@media (max-width: 600px) {
  :root {
    --page-gutter: 18px;
  }
}
```

------------------------------------------------------------------------

## 15. Reusable prompt for AI coding tools

Copy this prompt into Antigravity, Cursor, or another coding assistant
when starting a new website:

> Act as a senior product designer and frontend engineer. Build the
> website using the design principles in this guide.
>
> Use a clean, premium, Apple-inspired visual direction: restrained
> neutral colours, one clear accent colour, strong typography, generous
> whitespace, rounded surfaces, subtle borders, and purposeful layouts.
>
> Make the design feel art-directed and intentional, not generic or
> AI-generated. Avoid random gradients, excessive glassmorphism,
> repetitive card grids, unnecessary shadows, decorative clutter, and
> meaningless animations.
>
> Establish a consistent colour, typography, spacing, radius, and
> component system before building the page. Use a clear visual
> hierarchy and vary section composition only when it helps the content.
>
> Make the website responsive, accessible, and functional. Every visible
> button and link must have a meaningful action. Respect reduced-motion
> preferences and keep animation restrained.
>
> Treat this guide as a design system, not a rigid template. Adapt the
> layout to the website's actual purpose and content. Do not copy
> this design system sections when they are not relevant.

------------------------------------------------------------------------

## 16. How to use this guide

1.  Share this Markdown file with them or add it to a project
    repository.
2.  Ask them to use it as the visual design reference for their website.
3.  Tell their coding assistant what kind of website they are building
    and which sections they need.
4.  Ask the assistant to adapt the design system to that project rather
    than copying this design system exactly.
5.  Review the site at desktop and mobile sizes before publishing.

**Remember:** a good-looking interface is not created by rounded corners
and blue buttons alone. The real difference comes from consistency,
hierarchy, spacing, believable content, and attention to small details.

*Design reference: this design system --- "Make room for better work."*
