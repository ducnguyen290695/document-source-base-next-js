## I. Technical stacks

### 1. **Frontend Framework**

### **Next.js 12**

- ✅ Supports **Pages Router** only (uses `/pages`)
- ✅ **SSR** (Server-side), **SSG** (Static), **ISR**
- ✅ Built-in **Image Optimization**, **SEO**, and **API routes**
- ✅ Supports **Middleware**

### **React 18**

- ✅ **Concurrent Rendering** for faster UX
- ✅ **Suspense** & **Streaming** (great for SSR with Next.js)
- ✅ Hooks: `useState`, `useEffect`, `useContext`.

### 2. **State Management**

### **Redux Toolkit**

- ✅ Modern & simplified Redux
- ✅ Built-in support for **async thunks** and slices
- ✅ DevTools support

### 3. **UI Libraries & Styling**

### **Ant Design 5**

- ✅ Enterprise-ready UI components
- ✅ Supports **dark mode**
- ✅ Built-in **form validation**
- ✅ Internationalization (i18n) supported out of box
- ✅ Import on demands

### **Styled Components**

- ✅ **CSS-in-JS** styling
- ✅ Supports **dynamic styling** with props
- ✅ Built-in **SSR** support for Next.js
- ✅ Avoids class name collisions

### **Tailwind CSS 3**

- ✅ Utility-first CSS framework
- ✅ **JIT engine** (super fast)
- ✅ Works great with **responsive design**
- ✅ Plugins like `prettier-plugin-tailwindcss` auto-sort classes

### **Sass**

- ✅ CSS preprocessor with **variables**, **mixins**, and **nesting**
- ✅ Optional if Tailwind/Styled Components already used

### **tailwind-merge**

- ✅ Merges and deduplicates Tailwind class names
- ✅ Helpful in conditional `className` logic

### 4. **API Request**

### **React Query**

- ✅ **SSR Support** with Next.js
- ✅ **Client-side caching** with hydration
- ✅ **Background refetching** for fresh data
- ✅ Supports **pagination**, **infinite scroll**
- ✅ **Mutations** with optimistic updates
- ✅ Built-in **loading/error states**
- ✅ Devtools for query debugging

### **Axios**

- ✅ Promise-based HTTP client
- ✅ Supports **interceptors** (auth tokens, error handling)
- ✅ Supports **cancel tokens** for aborting requests
- ✅ Easy to create custom instances (`apiClient`)

### 5. **Animations**

### **Framer Motion**

- ✅ Declarative animation library for React
- ✅ Supports **variants**, **gestures** (drag, hover)
- ✅ Works with **AnimatePresence** for exit animations

### 7. **Internationalization (i18n)**

### **i18next**

- ✅ Core i18n engine (language switching, translation)
- ✅ Supports **pluralization**, **interpolation**, **fallbacks**

### **react-i18next**

- ✅ React bindings for i18next
- ✅ Supports **hooks** (`useTranslation`), and SSR
- ✅ Works with React Suspense

### **next-i18next**

- ✅ Next.js wrapper for i18next
- ✅ Supports SSR, static, and dynamic routes translation
- ✅ Auto language detection

### **i18next-scanner**

- ✅ CLI tool to scan `.ts/.tsx` files for translation keys
- ✅ Auto-generates translation JSON files

### 8. **Linting & Formatting**

### **ESLint**

- ✅ Linting JavaScript & TypeScript code
- ✅ **Airbnb config** ensures best practices
- ✅ Next.js-specific lint rules with `eslint-config-next`
- ✅ Prevents bugs before runtime

### **Prettier**

- ✅ Code formatter (standardizes quotes, spacing)
- ✅ Works with **Tailwind plugin** to auto-sort class names

### **Husky (via pre-commit)**

- ✅ Runs linting/formatting **before git commits**
- ✅ Prevents bad code from being pushed

### 9. **Type Checking**

### **TypeScript**

- ✅ Type safety for components, hooks, API calls
- ✅ Catches errors at compile-time
- ✅ Supports strict mode (`strict: true`)
- ✅ Works great with Next.js + React Query + Axios

---

## II. Code base structure

```bash
.husky/
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
├── api/
├── components/
│   ├── layouts/
│   ├── templates/
│   └── ui/
├── constants/
├── enums/
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

### `.husky/`

Git hooks managed by Husky.
Used for running checks (like linting, tests) before commits or pushes.

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

#### `api/`

API request functions. Handles communication with backend services.

#### `components/`

Reusable UI components.

- `layout/`: Page layout wrappers (e.g., `Header`, `Footer`, `Sidebar`).
- `seo/`: SEO components like `<Head>` management.
- `template/`: Page templates or section-level components.
- `ui/`: Atomic UI components (e.g., `Button`, `Input`, `Modal`).

#### `constants/`

App-wide constants and static configuration values.

#### `enums/`

TypeScript `enum` definitions for standardizing constant values
(e.g., `UserRole`, `OrderStatus`).

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
