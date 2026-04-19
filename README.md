# ShotbySpirit Photography Portfolio

A responsive multi-page photography portfolio website focused on nature and landscape work.

## Overview

ShotbySpirit is a static web portfolio that presents curated photography in a clean gallery experience. The site includes dedicated pages for home highlights, full galleries, brand story, and contact details.

This project is built with:

- HTML5
- CSS3
- Progressive Web App (PWA) basics via a web app manifest and service worker

## Pages

- Home: Featured hero section and highlighted image grid
- Galleries: Full collection view in a responsive gallery layout
- About: Story, mission, and offerings
- Contact: Contact form UI and communication details

## Key Features

- Responsive image presentation using the picture element and WebP assets
- Mobile-first responsive layout with breakpoint-based grid changes
- Accessible structure with semantic sections and descriptive image alt text
- Sticky navigation header with active page state
- Performance-minded image loading:
	- First hero/gallery image uses eager loading and high fetch priority
	- Remaining images use lazy loading and async decoding
- PWA support:
	- Web app manifest configured for standalone display
	- Service worker caching of core pages and assets for offline resilience

## Project Structure

```text
CA3/
├── index.htm         # Home page
├── galleries.htm     # Gallery page
├── about.htm         # About page
├── contact.htm       # Contact page
├── style.css         # Global styles and responsive layout rules
├── manifest.json     # PWA metadata
├── sw.js             # Service worker cache logic
├── images/           # Portfolio image assets
└── README.md
```

## Running Locally

Because this is a static website, you can run it in any of the following ways:

1. Open index.htm directly in your browser.
2. Or use a local static server (recommended for service worker testing).

Example with Python:

```bash
python3 -m http.server 8000
```

Then visit:

```text
http://localhost:8000/index.htm
```

## PWA Notes

- The service worker caches:
	- Root path and core HTML pages
	- style.css
	- manifest.json
- Cache version is controlled by CACHE_NAME in sw.js.
- When assets/pages change, increment CACHE_NAME to force old cache cleanup.

## Customization Guide

- Brand name and tagline:
	- Update the logo and hero text in index.htm and shared header/footer blocks.
- Portfolio images:
	- Replace files in images/ and update src/srcset references in index.htm and galleries.htm.
- Contact details:
	- Update email and social labels in contact.htm and footer sections.
- Color and typography:
	- Edit CSS custom properties at the top of style.css.

## Known Scope

- Contact form is currently UI-only and not connected to a backend.
- No build tooling is required; this is intentionally lightweight and framework-free.

## License

This project is intended for educational/portfolio use. Add your preferred license if distributing publicly.
