# NOIR — Digital Agency Website

A high-end, award-style marketing site for a fictional creative agency called **NOIR**. Built as a modern single-page application with smooth scroll-driven animations, a preloader, custom cursor, and dynamic case-study pages.

> **Stack:** React 19 · TypeScript · Vite 7 · Tailwind CSS 3 · Framer Motion · Lenis · shadcn/ui-style components

---

## ✨ Features

- **Preloader & Custom Cursor** — branded loading sequence and a bespoke cursor that reacts across the site
- **Smooth scrolling** — Lenis inertial scrolling with a shared scroll utility (`src/lib/scroll.ts`) and automatic scroll-to-top on route change
- **Animated sections** — Hero, Marquee, Manifesto, Services (accordion), Works (portfolio grid), Recognition (awards), Footer
- **Case-study routing** — `/work/:slug` renders a full project page (brief, outcomes, deliverables, quote, CSS-gradient gallery) driven by static data in `src/data/projects.ts`
- **Rich UI kit** — 60+ accessible components (Radix UI + Tailwind + CVA) under `src/components/ui/`
- **Type-safe forms & validation** — React Hook Form + Zod
- **Charts, carousels, drawers, command palette** — Recharts, Embla Carousel, Vaul, cmdk and more already wired up
- **Responsive & accessible** — mobile-first layout, Radix primitives for keyboard/screen-reader support

---

## 📁 Project Structure

```
project/
├── index.html                 # Entry HTML (NOIR — Digital Agency)
├── package.json
├── vite.config.ts             # Vite + React plugin
├── tailwind.config.js         # Tailwind theme & animations
├── tsconfig.json              # TypeScript project references
├── eslint.config.js           # ESLint flat config
└── src/
    ├── main.tsx               # React entry point
    ├── App.tsx                # Router, Lenis setup, Nav, Cursor
    ├── index.css              # Global styles / design tokens
    ├── components/
    │   ├── Cursor.tsx         # Custom cursor
    │   ├── Nav.tsx            # Navigation
    │   ├── Preloader.tsx      # Loading screen
    │   └── ui/                # shadcn/ui-style primitives
    ├── pages/
    │   ├── Home.tsx           # Landing page (all sections)
    │   └── ProjectPage.tsx    # Case-study detail page
    ├── sections/
    │   ├── Hero.tsx
    │   ├── Marquee.tsx
    │   ├── Manifesto.tsx
    │   ├── Services.tsx       # Accordion service list
    │   ├── Works.tsx          # Portfolio grid
    │   ├── Recognition.tsx    # Awards / press
    │   └── Footer.tsx
    ├── data/
    │   └── projects.ts        # Case-study content (typed)
    ├── hooks/
    │   └── use-mobile.ts
    └── lib/
        ├── scroll.ts          # Lenis instance helpers
        └── utils.ts           # cn() class utility
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 20+ (LTS recommended)
- **npm** (comes with Node) — or pnpm/yarn/bun of your choice

### Installation

```bash
# 1. Clone the repository
git clone <your-repo-url>.git
cd <repo-folder>

# 2. Install dependencies
npm install

# 3. Start the dev server
npm run dev
```

The app runs at **http://localhost:5173** by default (Vite).

---

## 📜 Available Scripts

| Script            | Description                                    |
| ----------------- | ---------------------------------------------- |
| `npm run dev`     | Start Vite dev server with HMR                 |
| `npm run build`   | Type-check with `tsc -b` and build for production |
| `npm run preview` | Preview the production build locally            |
| `npm run lint`    | Run ESLint across the project                  |

### Production build

```bash
npm run build
npm run preview
```

Output is emitted to `dist/`.

---

## 🧱 Tech Stack & Key Libraries

| Category            | Libraries                                                                  |
| ------------------- | -------------------------------------------------------------------------- |
| Framework           | React 19, React Router 7                                                   |
| Build tool          | Vite 7, TypeScript 5.9                                                     |
| Styling             | Tailwind CSS 3, PostCSS, Autoprefixer, `tailwind-merge`, `clsx`, CVA        |
| Components          | Radix UI (30+ primitives), shadcn/ui patterns, lucide-react icons          |
| Animation           | Framer Motion, Embla Carousel, `tailwindcss-animate`, Lenis smooth scroll  |
| Forms & Validation  | React Hook Form, Zod, `@hookform/resolvers`                                |
| Extras              | Recharts, cmdk, Vaul (drawer), sonner (toasts), next-themes, date-fns      |
| Linting             | ESLint 9 flat config, `typescript-eslint`, react-hooks & react-refresh     |

---

## 🗂️ Content & Customization

- **Case studies** — edit `src/data/projects.ts`. Each project is a typed `Project` object with `slug`, copy, deliverables, and CSS gradient strings for `art` / `gallery` (no image assets required).
- **Services** — update the array at the top of `src/sections/Services.tsx`.
- **Colors / typography** — adjust the Tailwind theme in `tailwind.config.js` and tokens in `src/index.css`.
- **Meta & title** — edit `index.html` (title is currently `NOIR — Digital Agency`).

---

## 🔧 Configuration Notes

- **Path aliases** — none configured; imports are relative from `src/`.
- **Environment variables** — no env vars required for local development. If you add any, create a `.env.local` file (`.env` files are git-ignored).
- **`node_modules/` and `dist/` are ignored** via `.gitignore` and must never be committed.

---

## 📦 Deployment

Any static host works after `npm run build`:

- **Vercel** — import the repo, framework preset *Vite*, build command `npm run build`, output `dist`
- **Netlify** — build `npm run build`, publish directory `dist`
- **GitHub Pages / Cloudflare Pages** — same build settings; ensure SPA fallback (rewrite all routes to `index.html`) so `/work/:slug` deep links work

---

## 🤝 Contributing

1. Fork the repository and create a feature branch: `git checkout -b feature/my-change`
2. Make your changes and verify with `npm run lint` and `npm run build`
3. Commit with a clear message and open a Pull Request

---

## 📄 License

This project is provided as-is for demonstration and portfolio purposes. Replace this section with your chosen license (MIT, etc.) if you plan to distribute it.
