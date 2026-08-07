# Komito - Hugo Coworking Theme

A complete Hugo static site based on the Komito coworking space design. Fully responsive, data-driven, and Markdown-powered.

## Features

- **Hugo Static Site Generator** — Blazing fast builds
- **Markdown Support** — Write blog posts and pages in Markdown
- **Data-Driven Sections** — Features, services, testimonials, pricing, events, and gallery are all powered by JSON data files
- **Responsive Design** — Mobile-first, works on all devices
- **Hugo Asset Pipeline** — CSS and JS are minified and fingerprinted automatically
- **Go Templates** — Clean, reusable partials

## Project Structure

```
komito-hugo/
├── archetypes/
│   └── default.md              # Template for new content
├── assets/
│   ├── css/
│   │   └── main.css            # Main stylesheet (processed by Hugo)
│   └── js/
│       └── main.js             # Main JavaScript (processed by Hugo)
├── content/
│   ├── _index.md               # Homepage content
│   └── posts/                  # Blog posts in Markdown
│       ├── post-1.md
│       ├── post-2.md
│       └── post-3.md
├── data/
│   ├── about_list.json         # About section list items
│   ├── events.json             # Events data
│   ├── features.json           # Feature cards
│   ├── gallery.json            # Gallery images
│   ├── pricing.json            # Pricing plans
│   ├── services.json           # Service items
│   └── testimonials.json       # Testimonials
├── layouts/
│   ├── _default/
│   │   ├── baseof.html         # Base template (head, header, footer)
│   │   ├── list.html           # Blog list page
│   │   └── single.html         # Single blog post
│   ├── partials/
│   │   ├── about.html
│   │   ├── events.html
│   │   ├── features.html
│   │   ├── footer.html
│   │   ├── gallery.html
│   │   ├── head.html
│   │   ├── header.html
│   │   ├── hero.html
│   │   ├── news.html
│   │   ├── pricing.html
│   │   ├── scroll-top.html
│   │   ├── scripts.html
│   │   ├── services.html
│   │   └── testimonials.html
│   └── index.html              # Homepage layout
├── static/
│   ├── fonts/                  # Custom fonts (optional)
│   └── images/                 # Static images
└── config.toml                 # Site configuration
```

## Quick Start

### 1. Install Hugo

```bash
# macOS
brew install hugo

# Windows (Chocolatey)
choco install hugo-extended

# Linux
sudo apt install hugo
```

### 2. Run the site locally

```bash
cd komito-hugo
hugo server -D
```

Open `http://localhost:1313` in your browser.

### 3. Build for production

```bash
hugo --minify
```

The built site will be in the `public/` folder.

## Customization

### Edit Site Info
Open `config.toml` and update:
- `title` — Site title
- `params` — Phone, email, address, social links, hero text, section titles

### Edit Data (No HTML needed!)
All repeating content is stored in `data/*.json`:
- **Features**: `data/features.json` — Add/remove feature cards
- **Services**: `data/services.json` — Update service icons and titles
- **Testimonials**: `data/testimonials.json` — Add customer reviews
- **Pricing**: `data/pricing.json` — Modify plans and prices
- **Events**: `data/events.json` — Update upcoming events
- **Gallery**: `data/gallery.json` — Change gallery images

### Write Blog Posts
```bash
hugo new posts/my-new-post.md
```

Then edit `content/posts/my-new-post.md`:
```markdown
---
title: "My New Post"
date: 2026-08-08T10:00:00Z
draft: false
image: "https://images.unsplash.com/photo-xxx"
categories: ["Business"]
tags: ["coworking"]
author: "Admin"
comments: 0
---

Your Markdown content here...
```

### Add/Edit Pages
```bash
hugo new about.md
hugo new services/_index.md
```

### Change Colors
Edit CSS variables in `assets/css/main.css`:
```css
:root {
    --primary-blue: #1a1a5e;
    --orange: #ff5722;
    /* ... */
}
```

## Menu Configuration
Edit the `[[menu.main]]` entries in `config.toml`:
```toml
[[menu.main]]
  name = "Home"
  url = "/"
  weight = 10
```

## Image Handling
- **External images**: Use full URLs in front matter and data files
- **Local images**: Place in `static/images/` and reference as `/images/photo.jpg`

## License
Free to use for personal and commercial projects.
