# andrevrc.dev

Personal portfolio and blog of **André Carvalho** — a full-stack engineer exploring AI, security, and ideas.

Built with [Astro](https://astro.build) and [Tailwind CSS v4](https://tailwindcss.com). Published at [andrevrc.github.io](https://andrevrc.github.io).

## Tech Stack

| Tech | Role |
|---|---|
| **Astro** ^7.0 | Static site generator |
| **Tailwind CSS** ^4.0 | Styling (Vite plugin) |
| **TypeScript** | Type safety |
| **@astrojs/rss** | RSS feed |
| **@astrojs/sitemap** | Sitemap |
| **GitHub Actions** | CI/CD → GitHub Pages |

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
```

## Design

The visual system is defined in [`me.pen`](./me.pen) — a Pencil design file with full color, typography, and layout tokens mirrored in [`src/styles/global.css`](./src/styles/global.css). The site supports light and dark modes via a `.dark` class toggle.

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that builds the site and deploys to GitHub Pages.

## License

MIT
