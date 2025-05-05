## 1. Code base structure

```bash
docs/
public/
├── assets/
├── favicon/
├── locales/
├── favicon.ico
├── next.svg
├── site.webmanifest
└── vercel.svg
server-fake/
src/
├── components/
│   ├── layouts/
│   ├── templates/
│   └── ui/
├── constants/
├── hooks/
├── pages/
├── redux/
├── services/
├── styles/
├── types/
└── utils/
.env.local
.eslintignore
.eslintrc.json
.gitignore
.prettierignore
.prettierrc
next-i18next.config.js
next.config.js
package.json
postcss.config.js
README.md
tailwind.config.js
tsconfig.json
yarn.lock
```

---

## Folders

### `docs/`

Project documentation, guides, and technical specs.

### `public/`

Static assets served directly at the root (`/`)

- `assets/`: Images, icons, and media files.
- `favicon/`: All favicon-related files.
- `locales/`: Translation files for i18n (internationalization).
- `favicon.ico`: Default site favicon.
- `next.svg`, `vercel.svg`: Example assets (can be cleaned up if unused).
- `site.webmanifest`: Manifest for PWA (Progressive Web App) support.

### `server-fake/`

Mock server or fake API endpoints used during development and testing.

### `src/`

Main source code for the application.

#### `components/`

Reusable UI components.

- `layout/`: Page layout wrappers (e.g., `Header`, `Footer`, `Sidebar`).
- `seo/`: SEO components like `<Head>` management.
- `template/`: Page templates or section-level components.
- `ui/`: Atomic UI components (e.g., `Button`, `Input`, `Modal`).

#### `constants/`

App-wide constants and static configuration values.

#### `hooks/`

Custom React hooks (`useXYZ`) to encapsulate logic.

#### `pages/`

Next.js pages. Maps directly to routes (`/about` → `pages/about.tsx`).

#### `redux/`

Redux state management:

- Slices, store setup, selectors, and actions.

#### `services/`

API service handlers and business logic (e.g., API calls, external services).

#### `styles/`

Global and module-based stylesheets. Likely contains Tailwind or custom CSS/SCSS.

#### `types/`

TypeScript type declarations and interfaces for consistent typing.

#### `utils/`

Helper functions and utilities used across the app.

---

## Files

### `.env.local`

Local environment variables (API keys, base URLs).

### `.eslintignore`

Specifies files and folders for ESLint to ignore.

### `.eslintrc.json`

ESLint configuration for code linting and quality checks.

### `.gitignore`

Git ignore rules to exclude files/folders from version control.

### `.prettierignore`

Specifies files and folders for Prettier to skip formatting.

### `.prettierrc`

Prettier configuration for code formatting rules (e.g., tabs, semicolons, quotes).

### `next-i18next.config.js`

Configuration for `next-i18next`, enabling internationalization in Next.js.

### `next.config.js`

Core Next.js configuration (custom Webpack, redirects, environment setup).

### `package.json`

Project dependencies, scripts, and metadata.

### `postcss.config.js`

Configures PostCSS (used with TailwindCSS and autoprefixing).

### `README.md`

Project overview, setup instructions, and documentation.

### `tailwind.config.js`

TailwindCSS configuration (custom themes, breakpoints, plugins).

### `tsconfig.json`

TypeScript compiler options and path aliases.

### `yarn.lock`

Yarn lock file to ensure consistent dependency versions.

---
