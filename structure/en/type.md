## 📁 Folder Structure - Type-Based (Global) Organization

```bash
src/
├── assets/
├── components/
│   ├── Buttons/
│   │   ├── Buttons.tsx
│   │   ├── ButtonsGoogle.tsx
│   │   └── index.ts
│   └── Inputs/
├── constants/
├── hooks/ 
├── layouts/
├── locales/
├── pages/ 
├── services/ 
├── store/ 
│   ├── reducer/
│   ├── selector/ 
│   ├── state/ 
│   ├── thunk/ 
│   └── index.ts 
├── styles/
├── typings/
└── utils/
```

### ✅ Pros

- ✔️ Simple and straightforward
- ✔️ Ideal for small to medium-sized projects
- ✔️ Easy to understand in early stages

### ❌ Cons

- ❌ As it grows, logic gets mixed together
- ❌ Harder to refactor or scale
- ❌ No domain encapsulation

---

### 🗂️ Folder Details

#### `assets/`

Holds all static files that are part of the app's visual design. It's recommended to organize them by type:

```bash
assets/
├── images/     # Images like JPG, PNG, WebP
├── icons/      # Individual or grouped SVG icons
├── fonts/      # Custom fonts
├── svgs/       # Reusable SVGs as components or assets
└── logos/      # Official or institutional logos
```

Use this folder as the central reference for visual resources to avoid duplication across components or pages.

#### `components/`

Houses reusable visual components. Each subfolder represents a set of related components (e.g., Buttons, Inputs, Cards). When a group has more than one component, include an `index.ts` to simplify grouped imports.

#### `constants/`

Defines global constants not tied to a specific domain (routes, messages, static config, localStorage keys, etc.). Can be separated by file: `routes.ts`, `messages.ts`, `config.ts`.

#### `hooks/`

Custom React hooks (`useForm`, `useFetch`, `useModal`, etc.) that encapsulate reusable logic shared across components or pages.

#### `layouts/`

Contains layout components like `MainLayout`, `AuthLayout`, etc. These typically wrap pages to maintain a consistent structure across routes.

#### `locales/`

i18n (internationalization) files. Recommended structure:

```bash
locales/
├── en.json
├── es.json
└── index.ts
```

Works well with libraries like `react-i18next`.

#### `pages/`

Contains the main views of the system, directly linked to routes. They should import all the necessary components, hooks, and services for each screen.

#### `services/`

Groups all logic that communicates with external APIs (REST, GraphQL, etc.). For example: `auth.service.ts`, `user.service.ts`, etc. Each file can expose specific networking functions.

#### `store/`

Organizes the Redux Toolkit (or similar) store configuration, divided by module:

- `reducer/`: individual reducers
- `state/`: initial states
- `selector/`: common state selectors
- `thunk/`: async actions with side effects
- `index.ts`: main file to combine reducers and configure the store

#### `styles/`

Contains global styles. May include:

- Tailwind files (`tailwind.config.js`)
- Sass files
- CSS variables (`:root { --color-primary: ... }`)

#### `types/`

Interfaces, types, and enums shared across the application (`User`, `Product`, `Role`, etc.). Ideal for defining contracts used in components, services, or store slices.

#### `utils/`

Pure helper functions such as validators, date formatters, data converters, etc.
