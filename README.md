# souk4711.github.io

Personal portfolio website.

## Features

- **Astro 7** — static output, zero client-side JavaScript by default
- **Tailwind CSS v4** — CSS-first config, no `tailwind.config.js` needed
- **Content Collections** with a typed Zod schema — add a project by dropping a Markdown file in `src/content/work/`
- **Light & dark mode** — class-based, no flash of unstyled theme on load
- **Astro Fonts API** — self-hosted Google Fonts, zero layout shift, no third-party requests
- **View Transitions** — smooth navigation between pages
- **SEO defaults done right** — canonical URLs, Open Graph, Twitter cards, auto-generated sitemap
- **Strict TypeScript** — `astro/tsconfigs/strict`, path aliases (`@/components/*`, etc.)
- One accent color and two font variables control the entire visual identity

No state management, no UI kit, no CMS integration —
add those yourself if your project actually needs them.

## Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
├── public/
│   ├── favicon.svg
│   ├── favicons/
│   ├── og-image.png          # replace with your own 1200×630 image
│   └── robots.txt
├── src/
│   ├── assets/               # static images and assets
│   ├── components/           # component Button, Footer, Header, etc.
│   ├── content/
│   │   └── work/*.md         # one file per project
│   ├── layouts/
│   │   └── Layout.astro      # <head>, SEO, fonts, theme script
│   ├── pages/
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── work/[id].astro
│   │   └── 404.astro
│   ├── styles/
│   │   └── global.css        # design tokens + Tailwind import
│   ├── content.config.ts     # zod schema for the "work" collection
│   └── site.config.ts        # name, bio, email, social links
├── astro.config.mjs
└── tsconfig.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## Customizing

**Your info.** Edit `src/site.config.ts` — name, tagline, email, and social links are
read from this one file by the header, footer, and homepage.

**Colors.** Edit the five custom properties at the top of `src/styles/global.css`
(`--paper`, `--ink`, `--ink-soft`, `--signal`, `--line`). Every component reads from
these tokens, so changing them re-skins the whole site.

**Fonts.** Swap the three families in the `fonts` array in `astro.config.mjs`. Any
family available from Google Fonts works — Astro self-hosts it automatically.

**Projects.** Add a Markdown file to `src/content/work/`. Required frontmatter is
enforced by the schema in `src/content.config.ts`:

```md
---
title: Project Name
summary: One sentence, shown in the list view.
url: https://example.com # optional
repo: https://github.com/... # optional
featured: true # optional, shows it first on the homepage
---

Full write-up in Markdown.
```

**Open Graph image.** Replace `public/og-image.png` with your own 1200×630 image.

## Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |
