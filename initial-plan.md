# Plano de Implementação

## Fase 1 — Setup (dia 1)
- [ ] `npm create astro@latest` com template minimal + Tailwind
- [ ] Configurar Tailwind com as cores e fontes do design (`me.pen`)
- [ ] Configurar GitHub Pages no `astro.config.mjs` (`site` e `base`)
- [ ] Criar GitHub Actions workflow para deploy
- [ ] Configurar domínio no GitHub Pages
- [ ] Criar `src/data/profile.json` com dados pessoais

## Fase 2 — Layout base (dia 2)
- [ ] `Base.astro` — estrutura global: Nav + `<slot />` + Footer
- [ ] Nav component (logo `/andre`, links: about, writing, now, contact)
- [ ] Footer component (copyright, github, twitter/X, email, RSS)
- [ ] Variáveis CSS custom properties com o design system (cores, fontes, spacing)
- [ ] Dark mode toggle (o design já suporta claro/escuro)

## Fase 3 — Home page (dia 2-3)
- [ ] Hero section (tagline "WRITING & BUILDING", nome, subtítulo)
- [ ] About section (foto + biografia)
- [ ] Writing section (últimos 3 posts vindos do CMS)
- [ ] "Now" section (4 itens: trabalhando, lendo, escrevendo, aprendendo)

## Fase 4 — Blog (dia 3-4)
- [ ] Página `/writing` com todos os posts e categorias (TECH, CARREIRA, REFLEXÃO, PROJETOS)
- [ ] Página de post individual `/writing/[slug]` (breadcrumb, artigo, imagem, pull quote)
- [ ] Author bio no final do post
- [ ] Related posts
- [ ] Paginação
- [ ] RSS feed (`@astrojs/rss`)

## Fase 5 — Experiências e Currículo (dia 4)
- [ ] Criar `src/data/experience.json` com histórico profissional
- [ ] Seção de experiências na Home (ou página própria)
- [ ] Página de currículo / PDF exportável

## Fase 6 — Contato (dia 4-5)
- [ ] Página `/contact` com formulário (nome, email, assunto, mensagem)
- [ ] Integrar Formspree (action no HTML, sem backend)
- [ ] Informações de contato (email, github, twitter, localização)

## Fase 7 — CMS + Admin (dia 5)
- [ ] Configurar Keystatic (ou Decap CMS)
- [ ] Interface admin para criar/editar posts
- [ ] Preview do post antes de publicar

## Fase 8 — Extras (dia 5-6)
- [ ] Giscus para comentários nos posts
- [ ] Umami analytics
- [ ] Sitemap (`@astrojs/sitemap`)
- [ ] SEO (meta tags, Open Graph)
- [ ] Performance audit (Lighthouse)
- [ ] Página 404 customizada

## Fase 9 — Deploy (dia 6)
- [ ] Ajustar GitHub Actions workflow
- [ ] HTTPS + domínio customizado
- [ ] Testar RSS, formulário, links, dark mode
- [ ] Commit inicial e push para `main`
