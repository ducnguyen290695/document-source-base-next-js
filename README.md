## I. Technical stacks

### 1. **Frontend Framework**

### **Next.js Ver 14**

- ✅ **App Router** and **Server Components** support
- ✅ Built-in **SSR** / **SSG**
- ✅ Image and Font optimization

### 2. **State Management**

### **Redux Toolkit**

- ✅ Modern & simplified Redux
- ✅ Built-in support for **async thunks** and slices
- ✅ DevTools support

### 3. **UI Libraries**

### **Option 1: Ant Design 5**

- ✅ Enterprise-ready UI components
- ✅ Supports **dark mode**
- ✅ Built-in **form validation**
- ✅ Internationalization (i18n) supported out of box
- ✅ Tree-shakable and optimized for performance

### **Option 2: Chakra UI**

- ✅ Built-in support for **dark mode**
- ✅ Easy to customize colors, fonts,...
- ✅ Tree-shakable and optimized for performance
- ✅ Built-in support for **responsive design**

### **Option 3: Shadcn UI**

- ✅ Dark Mode Support
- ✅ Server Components Friendly
- ✅ Styled with Tailwind CSS

### 4. **Styling**

### **Tailwind CSS 3**

- ✅ Utility-first CSS framework
- ✅ **JIT engine** (super fast)
- ✅ Works great with **responsive design**
- ✅ Plugins like `prettier-plugin-tailwindcss` auto-sort classes

### **Sass**

- ✅ CSS preprocessor with **variables**, **mixins**, and **nesting**
- ✅ Optional if Tailwind/Styled Components already used

### **styled-components**

- ✅ CSS-in-JS with **tagged template literals**
- ✅ Supports **dynamic styling** based on props
- ✅ Built-in **theming** support
- ✅ Prevents class name clashes with **scoped styles**

### 5. **API Request**

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

### 6. **Internationalization (i18n)**

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

### 7. **Linting & Formatting**

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

### 8. **Type Checking**

### **TypeScript**

- ✅ Type safety for components, hooks, API calls
- ✅ Catches errors at compile-time
- ✅ Supports strict mode
- ✅ Works great with Next.js + React Query + Axios

---

## II. Code base structure

```bash
├── .husky/                         # Git hooks configuration
├── docs/                           # Documentation files for the project
├── public/                         # Static files publicly accessible
│   ├── images/                     # Image assets for the app
│   ├── videos/                     # Video assets for the app
│   ├── audio/                      # Audio assets for the app
│   ├── favicon/                    # Favicon files
│   ├── documents/                  # Document files
│   ├── locales/                    # Localization files for internationalization
│   │   ├── index.ts                # Index file for i18n
│   │   ├── en/                     # English translation files
│   │   │   ├── home.json           # English content for the home page
│   │   │   └── about.json          # English content for the about page
│   │   └── jp/                     # Japanese translation files
│   │       ├── home.json           # Japanese content for the home page
│   │       └── about.json          # Japanese content for the about page
│   ├── next.svg                    # Next.js logo (or related branding)
│   ├── site.webmanifest            # Web app manifest for PWA
│   └── vercel.svg                  # Vercel logo (branding for deployment)
├── server-fake/                    # Fake server to simulate backend API responses
├── src/                            # Source code folder containing the app’s logic
│   ├── api/                        # API configurations and services
│   │   ├── axios-instance.ts       # Axios instance with base URL and interceptors
│   │   └── api-request.ts          # API request
│   ├── components/                 # Reusable UI components and layouts
│   │   ├── layouts/                # Layout components for different app sections
│   │   │   ├── MainLayout.tsx      # Main layout with sidebar and header
│   │   │   ├── AuthLayout.tsx      # Layout for authentication pages
│   │   │   ├── DashboardLayout.tsx # Admin dashboard layout
│   │   │   ├── PublicLayout.tsx    # Layout for public pages
│   │   │   ├── Header/             # Header components
│   │   │   │   └── Header.tsx      # Main header component
│   │   │   ├── Sidebar/            # Sidebar components
│   │   │   │   └── Sidebar.tsx     # Sidebar navigation
│   │   │   ├── Footer/             # Footer components
│   │   │   │   └── Footer.tsx      # Footer component
│   │   │   └── Breadcrumbs/        # Breadcrumbs component
│   │   │       └── Breadcrumbs.tsx # Breadcrumb navigation component
│   │   ├── templates/              # Templates for pages like user, profile, settings
│   │   │   ├── Auth/               # Authentication-related templates
│   │   │   │   ├── LoginForm.tsx   # Login form template
│   │   │   │   └── RegisterForm.tsx # Register form template
│   │   │   ├── Profile/            # Profile-related templates
│   │   │   │   ├── ProfileCard.tsx # Profile card template
│   │   │   │   └── ProfileForm.tsx # Profile form template
│   │   │   └── Settings/           # Settings-related templates
│   │   │       ├── AccountSettings.tsx # Account settings form template
│   │   │       └── NotificationSettings.tsx # Notification settings form template
│   │   └── ui/                     # UI components
│   │       ├── Button/             # Button component
│   │       ├── Input/              # Input component
│   │       ├── Table/              # Table component
│   │       ├── Form/               # Form component
│   │       ├── Select/             # Select component
│   │       ├── Checkbox/           # Checkbox component
│   │       ├── Notification/       # Notification component
│   │       ├── Upload/             # File upload component
│   │       ├── Avatar/             # Avatar component
│   │       ├── Tabs/               # Tab navigation component
│   │       ├── Tag/                # Tag component
│   │       ├── Tooltip/            # Tooltip component
│   │       ├── Drawer/             # Drawer component
│   │       ├── Image/              # Image component
│   │       ├── Radio/              # Radio button component
│   │       └── Loading/            # Loading spinner component
│   ├── constants/                  # Constants used throughout the app
│   │   ├── routes.ts               # Route paths constants
│   │   ├── api-endpoints.ts        # API endpoint paths
│   │   ├── roles.ts                # User roles
│   │   ├── messages.ts             # Success & error message templates
│   │   ├── regex.ts                # Common regex patterns
│   │   ├── i18n-keys.ts            # Translation keys
│   │   ├── app-config.ts           # General app configuration settings
│   │   └── index.ts                # Barrel export
│   ├── enums/                      # Enums for various app values
│   │   ├── role.ts                 # Enum for user roles
│   │   ├── status.ts               # Enum for common statuses
│   │   ├── language.ts             # Enum for supported languages
│   │   ├── theme.ts                # Enum for theme options
│   │   ├── storage-key.ts          # Enum for localStorage keys
│   │   ├── route.ts                # Enum for app routes
│   │   ├── api-endpoint.ts         # Enum for API endpoints
│   │   └── index.ts                # Barrel export
│   ├── hooks/                      # Custom React hooks for reusable logic
│   │   ├── index.ts                # Barrel export for hooks
│   │   ├── useBoolean.ts           # Hook for boolean state
│   │   ├── useNetworkState.ts      # Hook for network state
│   │   ├── useParams.ts            # Hook for retrieving URL parameters
│   │   ├── useToggle.ts            # Hook for toggle behavior
│   │   ├── useResponsive.ts        # Hook for responsive design
│   │   ├── useIsFirstRender.ts     # Hook for detecting first render
│   │   ├── useDebounce.ts          # Hook for debouncing input
│   │   ├── useCopyToClipboard.ts   # Hook for copying content to clipboard
│   │   ├── useMediaQuery.ts        # Hook for media query state
│   │   ├── usePrevious.ts          # Hook for tracking previous state
│   │   ├── useWindowScroll.ts      # Hook for tracking window scroll position
│   │   ├── useWindowSize.ts        # Hook for window size
│   │   ├── useOnClickOutside.ts    # Hook for handling clicks outside elements
│   │   └── usePagination.ts        # Hook for pagination logic
│   ├── pages/                      # Pages corresponding to app routes
│   │   ├── _app.tsx                # Global app wrapper
│   │   ├── _document.tsx           # Custom document configuration
│   │   ├── index.tsx               # Homepage
│   │   ├── auth/                   # Authentication-related pages
│   │   │   ├── login.tsx           # Login page
│   │   │   └── register.tsx        # Register page
│   │   ├── dashboard/              # Admin dashboard pages
│   │   │   └── index.tsx           # Dashboard homepage
│   │   ├── users/                  # User management pages
│   │   │   ├── index.tsx           # Users listing page
│   │   │   └── [id].tsx            # User detail page
│   │   ├── products/               # Product management pages
│   │   │   ├── index.tsx           # Products listing page
│   │   │   └── [id].tsx            # Product detail page
│   │   ├── settings/               # User settings page
│   │   │   └── index.tsx           # Settings page
│   │   ├── 404.tsx                 # Custom 404 Page
│   │   └── 403.tsx                 # Custom 403 Page
│   ├── redux/                      # Redux store and state management
│   │   ├── index.ts                # Redux store setup
│   │   ├── slices/                 # Redux slices
│   │   ├── hooks.ts                # Custom Redux hooks
│   │   └── root-reducer.ts         # Combines reducers
│   ├── services/                   # Services to interact with APIs
│   │   ├── auth.service.ts         # Auth-related API calls
│   │   ├── user.service.ts         # User CRUD operations
│   │   ├── product.service.ts      # Product CRUD operations
│   │   ├── file.service.ts         # File handling (upload, download)
│   │   ├── setting.service.ts      # App and user settings APIs
│   │   ├── common.service.ts       # Common API utilities
│   │   └── index.ts                # Optional barrel export
│   ├── styles/                     # CSS and style configuration
│   │   ├── globals.scss            # Global styles (applied globally)
│   │   ├── tailwind.css            # Tailwind CSS import
│   │   ├── variables.scss          # SCSS variables for global styling
│   │   ├── mixins.scss             # SCSS mixins and functions
│   │   ├── antd.override.scss      # Custom overrides for Ant Design
│   │   ├── theme.ts                # Theme configuration (Styled Components)
│   │   └── index.ts                # Barrel export
│   ├── types/                      # TypeScript type definitions
│   │   ├── index.ts                # General app types
│   │   ├── api.ts                  # API response types
│   │   ├── user.ts                 # User-related types
│   │   └── product.ts              # Product-related types
│   ├── utils/                      # Utility functions
│   │   ├── index.ts                # Barrel export
│   │   ├── date.ts                 # Date manipulation utilities
│   │   ├── file.ts                 # File-related utilities
│   │   ├── object.ts               # Object manipulation utilities
│   │   ├── array.ts                # Array utilities
│   │   ├── form.ts                 # Form-related utilities
│   │   ├── string.ts               # String manipulation utilities
│   │   ├── url.ts                  # URL utilities
│   │   ├── local-storage.ts        # localStorage utility functions
│   │   ├── i18n.ts                 # i18n utilities
│   │   └── cookie.ts               # Cookie manipulation utilities
├── .env.local                      # Local environment variables
├── .eslintignore                   # ESLint ignore configuration
├── .eslintrc.json                  # ESLint configuration file
├── .gitignore                      # Git ignore configuration
├── .prettierignore                 # Prettier ignore configuration
├── .prettierrc                     # Prettier configuration
├── next-i18next.config.js          # Configuration for next-i18next
├── next.config.js                  # Next.js configuration
├── package.json                    # Project metadata and dependencies
├── postcss.config.js               # PostCSS configuration for CSS processing
├── README.md                       # Project documentation
├── tailwind.config.js              # Tailwind CSS configuration
├── tsconfig.json                   # TypeScript configuration
└── yarn.lock                       # Yarn lock file
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
