## 📁 Folder Structure - Feature-Based (Domain-Driven) Organization

```bash
src/
├── features/
│   ├── Auth/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── store/
│   │   ├── types.ts
│   │   └── index.ts
│   └── Product/
│       ├── components/
│       ├── pages/
│       ├── services/
│       ├── store/
│       ├── types.ts
│       └── ...
├── shared/
│   ├── components/
│   ├── hooks/
│   ├── utils/
│   ├── types/
│   └── styles/
├── app/
│   ├── store.ts
│   ├── routes.ts
│   ├── i18n.ts
│   └── ...
├── assets/
└── main.tsx
```

### ✅ Pros

- ✔️ Scalable by feature
- ✔️ Encapsulates logic per domain
- ✔️ Ideal for large projects
- ✔️ Easy to remove/move features

### ❌ Cons

- ❌ More complex to start
- ❌ Requires strict conventions
- ❌ Too heavy for small projects

---

### 🗂️ Folder Details (Feature-Based)

#### `features/`

Contains all the business logic of the app, organized by domain: `Auth`, `Product`, `User`, etc. Each feature encapsulates its logic entirely. For example:

- `components/`: only components related to that feature (forms, cards, tables)
- `pages/`: views or screens related to that functionality
- `hooks/`: custom hooks used only by that feature
- `services/`: API requests for that feature only
- `store/`: domain-specific slices, actions, and reducers
- `types.ts`: domain-specific types and interfaces
- `index.ts`: entry point that can export what's needed outside the feature

This approach promotes encapsulation, facilitates testing, and makes it easier to remove features with minimal impact.

#### `shared/`

Holds cross-feature elements:

- `components/`: generic UI like buttons, inputs, modals
- `hooks/`: globally reusable hooks (`useDebounce`, `useModal`, etc.)
- `utils/`: validators, formatters, helpers
- `types/`: global types and interfaces
- `styles/`: global styles, variables, Tailwind config

#### `app/`

Contains general app configuration:

- `store.ts`: global store configuration (can combine feature slices)
- `routes.ts`: top-level route definitions
- `i18n.ts`: translation system setup

#### `assets/`

Same as in the global structure: holds static resources like images, icons, fonts, etc.

#### `main.tsx`

Main entry point of the application.