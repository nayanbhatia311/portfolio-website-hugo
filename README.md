# Nayan Bhatia Portfolio Website

Static portfolio website for [nayanbhatia.com](https://nayanbhatia.com), maintained as plain HTML/CSS with local media assets.

## Overview

This repository contains the source for Nayan Bhatia's personal academic and professional portfolio. The site highlights research projects, publications, internships, mentoring, awards, technical skills, and selected media coverage.

The project currently does not require a Hugo build step or a JavaScript package manager. The deployable site is the static file tree in this repository.

## Structure

- `index.html` - Main portfolio page.
- `nsb.html` - Network Simulation Bridge project page.
- `assets/` - Local images used by the site.
- `pdfs/` - Resume and other PDF artifacts.
- `sass/researcher.min.css` - Site stylesheet.
- `PulseFi News Links-3.pdf` - Pulse-Fi press/link reference document.

## Local Preview

From the repository root:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Opening `index.html` directly in a browser also works for most changes, but a local server is closer to production behavior for relative links and assets.

## Editing Guidelines

- Keep public-facing descriptions concise and safe for external readers.
- Put local images in `assets/` and reference them as `assets/filename.ext`.
- Keep PDFs in `pdfs/` unless they are standalone reference files.
- Use direct destination links instead of tracking or redirect URLs.
- After editing links or media paths, verify that referenced files exist and that no root-level images were reintroduced.

Useful checks:

```bash
rg -n "incoming|TODO|coming soon" index.html
find . -maxdepth 1 -type f \( -iname '*.png' -o -iname '*.jpg' -o -iname '*.jpeg' -o -iname '*.webp' -o -iname '*.heic' \)
```

## Deployment

The site is static. Deployment can be handled by any static host, including GitHub Pages, Netlify, Cloudflare Pages, or a conventional web server. Push changes to the configured remote branch used by the hosting provider.
