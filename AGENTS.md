# AGENTS.md — Instructions for AI coding assistants

## Project Overview

Personal portfolio + blog for André Carvalho (andrevrc). Brazilian Portuguese site, static, deployed to GitHub Pages.

## Tech Stack

- **Astro** ^7.0 with `.astro` components and content collections
- **Tailwind CSS** ^4.0 via `@tailwindcss/vite` (NOT PostCSS — use `@theme` directive, no `tailwind.config`)
- **TypeScript** with Astro strict config

## Key Conventions

### Code Style
- No comments in production code
- Brazilian Portuguese for UI copy, English for code (variable names, types, etc.)
- Single quotes for imports
- No semicolons in JS/TS (Astro default)

### Components
- Components in `src/components/`, PascalCase filenames
- Use Astro `.astro` files, not JSX/TSX
- Layouts in `src/layouts/`, use `<slot />` for content injection
- Keep components focused on presentation; data comes from `src/data/` JSON files

### Routing
- File-based routing in `src/pages/`
- Blog uses dynamic routes: `writing/[slug].astro`
- Blog content via Astro content collections (`src/content/`)

### Styling
- **Use Tailwind utility classes directly in templates**
- Custom theme tokens defined in `src/styles/global.css` via `@theme` directive
- Dark mode: class-based (`.dark` on `<html>`), toggled via `@custom-variant dark`
- Prose styles for blog content are in `global.css` (not `@tailwindcss/typography`)

### Data
- Personal info: `src/data/profile.json`
- Experience: `src/data/experience.json`
- Blog posts: Markdown in `src/content/blog/`

### Design System Tokens (from me.pen)

```css
/* Typography */
--font-heading: "Sora", sans-serif;
--font-body: "Inter", sans-serif;
--font-mono: "JetBrains Mono", monospace;

/* Colors — light mode defaults, overridden in :root.dark */
--color-surface-page        /* #F8FAFC → #0B1120 */
--color-surface-card        /* #FFFFFF → #141B2D */
--color-surface-primary     /* #F1F5F9 → #111827 */
--color-surface-inverse     /* #0F172A → #F1F5F9 */
--color-foreground-primary  /* #0F172A → #F1F5F9 */
--color-foreground-secondary/* #475569 → #B0BCC8 */
--color-foreground-inverse  /* #F1F5F9 → #0F172A */
--color-accent-primary      /* #0284C7 → #38BDF8 */
--color-accent-secondary    /* #7C3AED → #A78BFA */
--color-accent-warm         /* #D97706 → #F59E0B */
--color-border-subtle       /* #E2E8F0 → #1E293B */
```

Use Tailwind classes: `text-foreground-primary`, `bg-surface-card`, `border-border-subtle`, etc.

## Important Files

| File | Purpose |
|---|---|
| `src/styles/global.css` | Theme tokens, dark mode, prose styles |
| `src/data/profile.json` | Personal info for Hero, About, Footer |
| `src/data/experience.json` | Work history |
| `src/layouts/Base.astro` | Global layout (Nav + Footer + dark mode) |
| `src/pages/index.astro` | Homepage |
| `src/content/content.config.ts` | Content collections schema |
| `me.pen` | Visual design mockup (use Pencil MCP to read) |
| `.github/workflows/deploy.yml` | CI/CD pipeline |

## Available Agent Skills

Loaded via `opencode.json`:
- `astro` — Astro framework guidance
- `tailwind-design-system` — Tailwind v4 tokens
- `frontend-design` — Visual design direction
- `web-design-guidelines` — UI/UX compliance review

## Scripts

```bash
npm run dev       # astro dev
npm run build     # astro build
npm run preview   # astro preview
npm run check     # astro check (type-checking)
```

## Key Implementation Notes

- Contact form uses Formspree (action URL, no backend)
- RSS feed at `src/pages/rss.xml.ts`
- Dark mode toggle is implemented with class toggle on `<html>`
- Section headers use a terminal-prompt aesthetic (`~ $ cat about.md`)
- Blog posts support categories: carreira, tech, security, ai
- No CMS yet (Phase 7 in initial plan — Keystatic/Decap)

## Remaining Work (from initial-plan.md)

Phases not yet implemented or partially done:
- Phase 7: CMS integration (Keystatic)
- Phase 8: Giscus comments, Umami analytics, SEO tags
- Phase 9: Domain config, final polish
- Blog images: paths reference `/images/blog/` but no images exist yet
- Formspree ID is still placeholder
