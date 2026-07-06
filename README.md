# andrevrc.dev

Personal portfolio and blog of **André Carvalho** — a full-stack engineer exploring AI, security, and ideas.

Built with [Astro](https://astro.build) and [Tailwind CSS v4](https://tailwindcss.com). Published at [andrevrc.github.io](https://andrevrc.github.io).

## Tech Stack

| Tech | Role | Status |
|---|---|---|
| **Astro** ^7.0 | Static site generator | ✅ |
| **Tailwind CSS** ^4.0 | Styling (Vite plugin) | ✅ |
| **TypeScript** | Type safety | ✅ |
| **@astrojs/rss** | RSS feed | ✅ |
| **@astrojs/sitemap** | Sitemap | ✅ |
| **GitHub Actions** | CI/CD → GitHub Pages | ✅ |
| **Keystatic** | Headless CMS for blog management | 📋 |
| **Giscus** | Comments via GitHub Discussions | 📋 |
| **Umami** | Privacy-friendly analytics | 📋 |
| **Formspree** | Contact form backend | ✅ |

## Scripts

```bash
npm run dev       # Start dev server
npm run build     # Build for production
npm run preview   # Preview production build
npm run check     # Run Astro type checking
```

## Project Structure

```
src/
├── components/   # Reusable Astro components
├── content/      # Blog posts (content collections)
├── data/         # Profile and experience data (JSON)
├── layouts/      # Page layouts
├── pages/        # Routes and endpoints
└── styles/       # Global CSS and theme tokens
content/          # Keystatic CMS content (when integrated)
keystatic/        # Keystatic admin config (when integrated)
```

## Design

The visual system is defined in [`me.pen`](./me.pen) — a Pencil design file with full color, typography, and layout tokens mirrored in [`src/styles/global.css`](./src/styles/global.css). The site supports light and dark modes via a `.dark` class toggle.

## Planned Integrations

- **Keystatic** — Headless CMS for managing blog posts via a local admin UI
- **Giscus** — Comment system powered by GitHub Discussions
- **Umami** — Privacy-first, self-hostable analytics

The [implementation plan](./initial-plan.md) covers these in phases 7–9.

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that builds the site and deploys to GitHub Pages.

## License

MIT
