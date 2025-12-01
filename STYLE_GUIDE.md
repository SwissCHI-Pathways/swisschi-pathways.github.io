# SwissCHI Pathways Style Guide

This style guide defines the visual and content standards for the SwissCHI Pathways website.

## Brand Identity

### Logo
- Multiple logo variants are available in `assets/images/`:
  - Full logo: `PathwaysLogo_CompleteLogo_BlackPurple.svg` (primary choice)
  - Logotype only: `PatwaysLogo_Logotype_BlackPurple.svg` (for footer, narrow spaces)
  - Symbol only: `PatwaysLogo_Symbol_Purple.svg` (for favicon, icon)
- Maintain minimum spacing around the logo (1.5x height of the symbol)
- Do not stretch, distort, or change the colors of the logo
- For dark backgrounds, use white variants (`PathwaysLogo_CompleteLogo_White.svg`)

### Colors
Primary palette:
- Primary Purple: `#3C2FB3` - Main brand color for headings, links, and primary elements
- Secondary Red: `#802355` - Used for secondary buttons and accent elements
- Accent Dark: `#1f2937` - Used for text and supporting elements
- Background: `#ffffff` - Main background color
- Text: `#1f2937` - Main text color
- Light Gray: `#f3f4f6` - Used for backgrounds of sections, cards
- Dark Gray: `#374151` - Used for footers and secondary text

### Typography
- Heading Font: Inter (sans-serif)
- Body Font: Inter (sans-serif)
- Heading Sizes:
  - H1: 2.8rem (with purple underline accent)
  - H2: 2rem (with subtle purple underline)
  - H3: 1.75rem (in primary purple)
  - H4: 1.3rem (font-weight: 600)
- Body Text: 1rem (16px)
- Line Height: 1.6 for body text
- Decorative Elements:
  - Use underlines for headings
  - Use purple background with rounded corners for special elements

## Content Guidelines

### Writing Style
- Be clear, concise, and direct
- Use active voice rather than passive
- Write in a friendly, approachable academic tone
- Avoid jargon and technical terms without explanation
- Focus on benefits to the reader and community aspects

### Images
- Use high-quality, relevant images
- Images should be optimized for web (file size < 200KB when possible)
- All images must have appropriate alt text for accessibility
- Preferred formats: SVG for logos/icons, JPEG for photos, PNG for graphics with transparency

### Buttons and CTAs
- Primary buttons: Purple background (`#3C2FB3`), white text, rounded corners (30px)
- Secondary buttons: Red background (`#802355`), white text, rounded corners (30px)
- Outline buttons: Transparent background with colored border
- Button text should be action-oriented (e.g., "Join Now" rather than "Membership")
- Use subtle hover effects (slight elevation with shadow)
- Limit to one primary CTA per section

## Layout Patterns

### Headers
- Keep headers concise (ideally under 6 words)
- Include a decorative underline for H1 and H2 elements
- Use purple color for emphasis
- Include a clear hierarchy (H1 → H2 → H3)

### Cards
- Use cards with subtle shadows for grouping related content
- Add a colored top border (3-4px) in primary or secondary color
- Rounded corners (12px) for all cards
- Hover effects for interactive cards (slight elevation)
- Include a heading, short description, and optional icon

### Event Cards
- Use a distinctive design with date badge in purple
- Include location and time with appropriate icons
- Clear CTA button for registration
- Horizontal layout with responsive design for mobile

### Mission Points
- Include distinctive colored icon in circular background
- Left-aligned layout with icon + content
- Use animations for enhanced engagement

## Animations and Interactions

### Navigation
- Underline animation for navigation links on hover
- Active state highlighting for current page
- Smooth mobile menu toggle animation

### Scroll Animations
- Subtle fade-in and translate effects for content sections
- Staggered animations for list items and cards
- Performance-optimized (no heavy animations)

### Hover Effects
- Elevation effect (translateY + shadow) for buttons and cards
- Color transitions for links and interactive elements
- Scale effects for logo and important elements

## Accessibility Guidelines

### General
- Maintain color contrast ratios of at least 4.5:1 for normal text
- All interactive elements must be keyboard accessible
- Provide text alternatives for all non-text content
- Use semantic HTML elements throughout the site
- Test with screen readers when possible

### Skip Link
- Include a "Skip to main content" link as the first focusable element
- Hidden by default, visible on focus
- Links to `#main-content` on the main element

### Decorative Elements
- Add `aria-hidden="true"` to decorative SVG icons
- Icons accompanying text labels should be hidden from screen readers
- Only icons that convey unique information need accessible names

### Forms and Iframes
- Ensure all form inputs have associated labels
- Add `title` attribute to iframes (e.g., Google Forms embeds)
- Provide alternative access methods for embedded content

### ARIA Attributes
- Use `aria-hidden="true"` for purely decorative elements
- Use `aria-label` for interactive elements without visible text
- Avoid redundant ARIA that duplicates native semantics

## Responsive Design

### Mobile Navigation
- Hamburger menu with animated toggle
- Full-width expanded menu
- Clear active states

### Content Adaptation
- Single column layouts on mobile
- Reduced padding and margins
- Adjusted font sizes for readability
- Stacked elements instead of side-by-side

### Breakpoints
- Mobile: up to 576px
- Tablet: 577px to 768px
- Desktop: 769px to 992px
- Large desktop: 993px and above

## SEO Guidelines

### Meta Descriptions
- Each page must have a unique `description` in front matter
- Keep descriptions under 160 characters
- Include relevant keywords naturally
- Write compelling copy that encourages clicks

### Canonical URLs
- Canonical link is automatically added via `_layouts/default.html`
- Prevents duplicate content issues with trailing slashes

### Structured Data (Schema.org)
- Organization schema is included site-wide in the default layout
- Event schema is generated for each upcoming event
- Use JSON-LD format embedded in `<script>` tags

### Page Titles
- Format: `Page Title | SwissCHI Pathways`
- Keep titles under 60 characters
- Front-load important keywords

## Event Calendar Files

### iCalendar (.ics) Format
- Store event calendar files in `assets/calendar/`
- Filename format: `{event-slug}.ics`
- Required fields: DTSTART, DTEND, SUMMARY, DESCRIPTION, LOCATION
- Include ORGANIZER and URL for completeness
- Use UTC timestamps or specify timezone