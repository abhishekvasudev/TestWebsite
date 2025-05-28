# Personal Portfolio & Blog

A modern, automated Jekyll-based portfolio and blog website built with Bootstrap 5.

## Features

- Modern, responsive design using Bootstrap 5
- Blog with categories and tags
- Travel diary with photo gallery
- Curated links section
- Contact form
- SEO optimized
- Dark/Light mode support
- Automated deployment with GitHub Actions

## Prerequisites

- Ruby 3.2 or higher
- Bundler
- Git

## Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/portfolio.git
   cd portfolio
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Start the development server:
   ```bash
   bundle exec jekyll serve
   ```

4. Visit `http://localhost:4000` in your browser

## Project Structure

```
├── _config.yml          # Jekyll configuration
├── _data/              # Data files
├── _includes/          # Reusable components
├── _layouts/           # Page layouts
├── _posts/             # Blog posts
├── _travel/            # Travel diary posts
├── _sass/              # SCSS files
├── assets/             # Static assets
├── pages/              # Static pages
└── index.md            # Homepage
```

## Adding Content

### Blog Posts

Create a new file in `_posts/` with the format `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD
categories: [Category]
tags: [Tag1, Tag2]
---

Your content here...
```

### Travel Posts

Create a new file in `_travel/` with the format `YYYY-MM-DD-location.md`:

```markdown
---
layout: travel
title: "Location Name"
date: YYYY-MM-DD
location: "City, Country"
images:
  - path: /assets/images/travel/location/image1.jpg
    caption: "Image description"
---

Your travel content here...
```

### Links

Add new links to `_data/links.yml`:

```yaml
- title: "Link Title"
  url: "https://example.com"
  description: "Link description"
  category: "Category"
```

## Customization

### Theme Colors

Edit `_sass/_variables.scss` to customize colors and other Bootstrap variables.

### Layouts

Modify files in `_layouts/` to change page layouts.

### Styles

Edit `assets/css/main.scss` to customize styles.

## Deployment

The site is automatically deployed to GitHub Pages when changes are pushed to the main branch. The deployment process is handled by GitHub Actions.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Jekyll](https://jekyllrb.com/)
- [Bootstrap](https://getbootstrap.com/)
- [Font Awesome](https://fontawesome.com/)
- [GitHub Pages](https://pages.github.com/) 