# SwissCHI Pathways Website Modification Guide

This guide provides detailed instructions on how to modify each aspect of the SwissCHI Pathways website, including the updated design system with purple and red color scheme.

## Table of Contents
1. [Getting Started](#getting-started)
2. [Content Modification](#content-modification)
3. [Layout Modification](#layout-modification)
4. [Styling Modification](#styling-modification)
5. [Components & UI Elements](#components-and-ui-elements)
6. [Navigation Modification](#navigation-modification)
7. [Logo & Brand Assets](#logo-and-brand-assets)
8. [Adding New Pages](#adding-new-pages)
9. [Working with Data](#working-with-data)
10. [Animation & Interactivity](#animation-and-interactivity)
11. [Deployment](#deployment)

## Getting Started

### Prerequisites
- Ruby (version 2.7 or higher)
- Bundler gem
- Basic knowledge of HTML, CSS/SCSS, and Liquid templating

### Local Development
1. Install dependencies:
   ```bash
   bundle install
   ```

2. Run the site locally:
   ```bash
   bundle exec jekyll serve
   ```

3. View the site at `http://localhost:4000`

4. For live reloading during development:
   ```bash
   bundle exec jekyll serve --livereload
   ```

## Content Modification

### Main Pages
The main content pages are Markdown files in the root directory:

- `index.md` - Homepage with animated logo and call-to-action buttons
- `about.md` - About page with mission sections and animated elements
- `events.md` - Events page with styled event cards and date badges
- `join.md` - Membership page with form styling
- `contact.md` - Contact page with social links and contact form

### Front Matter
Each content file begins with front matter (between `---` marks):

```yaml
---
layout: default
title: Page Title
---
```

You can add custom front matter variables for use in templates.

### Adding In-Page CSS
For page-specific styling, you can add a `<style>` block directly in the markdown:

```html
<style>
  .my-custom-element {
    color: #3C2FB3; /* Primary purple */
  }
</style>
```

## Layout Modification

### Main Layouts
Layouts are in the `_layouts` directory:

- `default.html` - Main layout template for all pages
- `home.html` - Specific layout for the homepage with animated hero section

### Modifying Layouts
1. Edit `_layouts/default.html` to change the overall structure
2. Edit `_layouts/home.html` to change the homepage layout

### Include Files
Reusable components are in the `_includes` directory:

- `header.html` - Website header with logo and responsive navigation
- `footer.html` - Website footer with logo, links, and contact information

## Styling Modification

### SASS Structure
The CSS is organized in SASS files in the `_sass` directory:

- `_sass/variables.scss` - Colors (purple/red scheme), fonts, sizes, and other variables
- `_sass/base.scss` - Basic styling elements including typography and utility classes
- `_sass/layout.scss` - Page layout components including header, footer, and responsive grid
- `_sass/components.scss` - UI components like buttons, cards, animations, etc.

### Main CSS File
The main CSS file that imports all SASS files is `assets/css/main.scss`.

### Modifying the Color Scheme
To adjust the color scheme:
1. Open `_sass/variables.scss`
2. Modify the color variables:
   ```scss
   $primary-color: #3C2FB3; // Purple
   $secondary-color: #802355; // Red
   $accent-color: #1f2937; // Dark gray
   // Other colors...
   ```

### Modifying Typography
To change fonts:
1. Open `_sass/variables.scss`
2. Update the font variables:
   ```scss
   $font-family: 'Your-Font', sans-serif;
   $heading-font-family: 'Your-Heading-Font', serif;
   ```
3. Adjust heading styles in `_sass/base.scss` including the decorative underlines

## Components and UI Elements

### Buttons
The site uses several button styles:
```html
<!-- Primary (purple) button -->
<a href="/join" class="btn btn-primary">Join Us</a>

<!-- Secondary (red) button -->
<a href="/events" class="btn btn-secondary">Upcoming Events</a>

<!-- Outline button -->
<a href="/about" class="btn btn-outline">Learn More</a>
```

### Cards
Event cards have a special design with date badges:
```html
<div class="event-card">
  <div class="event-date-badge">
    <span class="month">SEP</span>
    <span class="day">15</span>
    <span class="year">2025</span>
  </div>
  <div class="event-content">
    <h3>Event Title</h3>
    <p>Event description...</p>
    <!-- Event details and button -->
  </div>
</div>
```

### Mission Points
Mission points use icons with colored backgrounds:
```html
<div class="mission-point">
  <div class="mission-icon">
    <!-- SVG icon here -->
  </div>
  <div>
    <h3>Title</h3>
    <p>Description</p>
  </div>
</div>
```

## Navigation Modification

### Desktop Navigation
To modify the navigation menu:
1. Open `_includes/header.html`
2. Edit the `<nav class="site-nav">` section to add/remove menu items

```html
<nav class="site-nav">
  <ul>
    <li><a href="{{ '/' | relative_url }}">Home</a></li>
    <li><a href="{{ '/about' | relative_url }}">About</a></li>
    <li><a href="{{ '/new-page' | relative_url }}">New Page</a></li>
  </ul>
</nav>
```

### Mobile Navigation
The mobile navigation uses a hamburger menu toggle:
```html
<button class="nav-toggle" aria-label="Toggle navigation">
  <span></span>
  <span></span>
  <span></span>
</button>
```

The JavaScript in `assets/js/main.js` handles the toggle functionality.

## Logo and Brand Assets

### Available Logo Files
Multiple logo variants are available in `assets/images/`:
- Full logo: `PathwaysLogo_CompleteLogo_BlackPurple.svg` (primary)
- Logotype only: `PatwaysLogo_Logotype_BlackPurple.svg` (footer)
- Symbol only: `PatwaysLogo_Symbol_Purple.svg` (favicon, icon)
- Additional color variants including white versions for dark backgrounds

### Using Logos
```html
<!-- Header logo -->
<img src="{{ '/assets/images/PathwaysLogo_CompleteLogo_BlackPurple.svg' | relative_url }}" alt="SwissCHI Pathways" height="60">

<!-- Footer logo -->
<img src="{{ '/assets/images/PatwaysLogo_Logotype_BlackPurple.svg' | relative_url }}" alt="SwissCHI Pathways" height="40">

<!-- Symbol only for icon -->
<img src="{{ '/assets/images/PatwaysLogo_Symbol_Purple.svg' | relative_url }}" alt="Pathways Symbol" class="home-logo">
```

## Adding New Pages

To add a new page:
1. Create a new markdown file in the root directory (e.g., `new-page.md`)
2. Add front matter:
   ```yaml
   ---
   layout: default
   title: Your New Page Title
   ---
   ```
3. Add content in Markdown format
4. Use the established component patterns for consistency
5. Update navigation in `_includes/header.html` if needed

## Working with Data

### Data Files
Data files are in the `_data` directory in YAML format:
- `features.yml` - Contains feature items for the homepage

### Modifying Data
To update features on the homepage:
1. Edit `_data/features.yml`
2. Follow the existing format:
   ```yaml
   - title: Feature Title
     description: Feature description text
   ```

### Using Data in Templates
Data is accessed in templates using Liquid syntax:
```liquid
{% for feature in site.data.features %}
  <div class="feature">
    <h3>{{ feature.title }}</h3>
    <p>{{ feature.description }}</p>
  </div>
{% endfor %}
```

## Animation and Interactivity

### CSS Animations
The site uses several CSS animations:
- Fade-in and translate effects for content on scroll
- Hover effects for buttons and cards
- Navigation underline animations
- Logo animations

### JavaScript Interactions
Key interactions in `assets/js/main.js`:
- Mobile navigation toggle
- Smooth scrolling for anchor links
- Scroll animations for content
- Active state for current navigation item

### Adding New Animations
To add scroll animations to new elements:
1. Add the appropriate class to your HTML element (e.g., `mission-point`, `activity-card`)
2. The JavaScript will automatically apply the `animate` class when scrolled into view
3. Customize the animation in `_sass/components.scss`

## Deployment

### GitHub Pages Deployment
1. Push changes to the `main` branch
2. GitHub will automatically build and deploy the site

### Important Deployment Notes
- Ensure all links use `relative_url` filter
- Test the site locally before pushing changes
- Optimize images to keep file sizes small
- Keep the design consistent with the style guide

### Custom Domain (Optional)
1. Add a file named `CNAME` to the repository root
2. Add your custom domain to this file (e.g., `www.swisschi-pathways.ch`)
3. Configure DNS settings with your domain provider