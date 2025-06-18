## 📁 Estructura de Carpetas - Organización por Feature (Dominio Funcional)

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

- ✔️ Escalable por feature
- ✔️ Encapsula lógica por dominio
- ✔️ Ideal para proyectos grandes
- ✔️ Fácil de eliminar/mover features

### ❌ Contras

- ❌ Más compleja de iniciar
- ❌ Requiere convención estricta
- ❌ Sobrecarga para proyectos pequeños

---

### 🗂️ Detalle por carpeta (Feature-Based)

#### `features/`

Contiene todas las funcionalidades del sistema separadas por dominio: `Auth`, `Product`, `User`, etc. Cada dominio encapsula completamente su lógica. Por ejemplo:

- `components/`: solo componentes relacionados a esa feature (formularios, tarjetas, tablas).
- `pages/`: vistas o pantallas relacionadas a esa funcionalidad.
- `hooks/`: hooks personalizados usados solo por esa feature.
- `services/`: peticiones API relacionadas solo a esa feature.
- `store/`: slices, actions, reducers específicos del dominio.
- `types.ts`: tipos e interfaces del dominio.
- `index.ts`: punto de entrada que puede exponer lo necesario al exterior.

Este enfoque promueve encapsulamiento, facilita testing y permite eliminar features sin afectar otras partes del sistema.

#### `shared/`

Contiene elementos compartidos por varias features:

- `components/`: UI genérica como botones, inputs, modales.
- `hooks/`: hooks reutilizables globalmente (`useDebounce`, `useModal`, etc.).
- `utils/`: validadores, formateadores, helpers.
- `types/`: tipos e interfaces globales.
- `styles/`: estilos globales, variables, Tailwind config.

#### `app/`

Contiene configuración general de la aplicación:

- `store.ts`: configuración del store global (puede combinar slices de cada feature).
- `routes.ts`: definición de rutas de alto nivel.
- `i18n.ts`: configuración del sistema de traducción.

#### `assets/`

Igual que en la estructura global, contiene recursos estáticos: imágenes, íconos, fuentes, etc.

#### `main.tsx`

Punto de entrada principal de la aplicación.