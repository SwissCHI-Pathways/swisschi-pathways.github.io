# SwissCHI Pathways

This repository contains the website for SwissCHI Pathways, the student chapter of the Swiss Computer-Human Interaction Association.

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

### Adding Content
- Create new pages as Markdown files in the root directory
- Add front matter at the top of each file with layout and title
- Use the existing layouts in `_layouts` or create new ones

## Project Structure
- `_layouts/`: HTML templates for pages
- `_includes/`: Reusable HTML components
- `_sass/`: SCSS stylesheets
- `assets/`: Static files (CSS, JS, images)
- `_data/`: YAML data files

## Deployment
This site is automatically deployed to GitHub Pages when changes are pushed to the main branch.

## Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request