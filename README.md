# SwissCHI Pathways

This repository contains the website for SwissCHI Pathways, the student chapter of the Swiss Computer-Human Interaction Association. The site features a modern design with a purple and red color scheme, responsive layout, and engaging animations.

## Getting Started

### Prerequisites
- Ruby (version 2.7 or higher)
- Bundler gem

### Installation
1. Clone this repository
2. Install dependencies:
   ```
   bundle install
   ```

### Development
Run the site locally:
```
bundle exec jekyll serve
```

This will start a local server at `http://localhost:4000`

For live reloading during development:
```
bundle exec jekyll serve --livereload
```

### Adding Content
- Create new pages as Markdown files in the root directory
- Add front matter at the top of each file with layout and title
- Use the established component patterns for consistency
- Follow the style guide in `STYLE_GUIDE.md`

## Project Structure
- `_layouts/`: HTML templates for pages
- `_includes/`: Reusable HTML components
- `_sass/`: SCSS stylesheets organized by function
- `assets/`: Static files (CSS, JS, images, logos)
- `_data/`: YAML data files for dynamic content
- `GUIDE.md`: Detailed development guide
- `STYLE_GUIDE.md`: Visual style guidelines

## Design System
The site uses a cohesive design system with:

- **Colors**: Purple primary (`#3C2FB3`), Red secondary (`#802355`)
- **Components**: Custom button styles, event cards, mission points
- **Typography**: Clean heading hierarchy with decorative underlines
- **Animations**: Subtle scroll animations and interactive elements
- **Responsive**: Mobile-first approach with hamburger navigation

See `STYLE_GUIDE.md` for complete design documentation.

## Logos and Branding
Multiple logo variants are available in `assets/images/` including:
- Full logo: `PathwaysLogo_CompleteLogo_BlackPurple.svg`
- Logotype only: `PatwaysLogo_Logotype_BlackPurple.svg`
- Symbol only: `PatwaysLogo_Symbol_Purple.svg`
- Additional color variants for different backgrounds

## Deployment
This site is automatically deployed to GitHub Pages when changes are pushed to the main branch.

## Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes following the style guide
4. Test thoroughly on multiple devices
5. Submit a pull request