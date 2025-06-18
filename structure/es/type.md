## 📁 Estructura de Carpetas - Organización por Tipo (Global)

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
├── types/
└── utils/
```

### ✅ Pros

- ✔️ Simple y directa
- ✔️ Ideal para proyectos pequeños o medianos
- ✔️ Fácil de entender al inicio

### ❌ Contras

- ❌ A medida que crece, se mezcla lógica
- ❌ Refactorizar o escalar es más difícil
- ❌ No hay encapsulamiento por dominio

---

### 🗂️ Detalle por carpeta

#### `assets/`

Contiene todos los archivos estáticos que forman parte del diseño visual de la aplicación. Se recomienda organizar por tipo:

```bash
assets/
├── images/     # Imágenes en formatos como JPG, PNG, WebP
├── icons/      # Íconos SVG individuales o agrupados
├── fonts/      # Tipografías personalizadas
├── svgs/       # SVGs reutilizables como componentes o recursos
└── logos/      # Logos institucionales u oficiales
```

Utiliza esta carpeta como referencia central para cualquier recurso visual, evitando la repetición en componentes o páginas.

#### `components/`

Agrupa componentes visuales reutilizables. Cada subcarpeta debe representar un conjunto de componentes relacionados (ej. Buttons, Inputs, Cards). Cuando un grupo tiene más de un componente, incluir `index.ts` para facilitar las importaciones agrupadas.

```bash
├── components/
│   ├── Buttons/
│   │   ├── Buttons.tsx
│   │   ├── ButtonsGoogle.tsx
│   │   └── index.ts            #wrapper (requerido cuando hay mas de un componente en esta carpeta)
│   └── ...
```

#### `constants/`

Define constantes globales que no dependen del dominio (rutas, mensajes, configuraciones estáticas, claves de localStorage, etc.). Puedes separarlas por archivo: `routes.ts`, `messages.ts`, `config.ts`.

#### `hooks/`

Hooks personalizados (`useForm`, `useFetch`, `useModal`, etc.) que encapsulan lógica reutilizable entre múltiples componentes o páginas.

#### `layouts/`

Contiene componentes de estructura visual como `MainLayout`, `AuthLayout`, etc. Estos suelen envolver las páginas para mantener una estructura coherente entre rutas.

#### `locales/`

Archivos de internacionalización (i18n). Estructura recomendada:

```bash
locales/
├── en.json
├── es.json
└── index.ts
```

Se pueden usar con bibliotecas como `react-i18next`.

#### `pages/`

Contiene las vistas principales del sistema, enlazadas directamente a rutas. Deben importar componentes, hooks y servicios necesarios para cada vista.

#### `services/`

Agrupa la lógica que se comunica con APIs externas (REST, GraphQL, etc.). Ejemplo: `auth.service.ts`, `user.service.ts`, etc. Cada archivo puede exponer funciones de red específicas.

#### `store/`

Organiza la configuración de Redux Toolkit o equivalente. Divide por módulo:

- `reducer/`: reducers individuales.
- `state/`: estados iniciales.
- `selector/`: selectores comunes para acceder a slices del estado.
- `thunk/`: acciones asincrónicas con side effects.
- `index.ts`: archivo central para combinar los reducers y configurar el store.

#### `styles/`

Alberga los estilos globales de la aplicación. Puede incluir:

- Archivos de Tailwind (`tailwind.config.js`)
- Archivos Sass
- Variables CSS (`:root { --color-primary: ... }`)

#### `types/`

Interfaces, tipos y enums compartidos en la aplicación (`User`, `Product`, `Role`, etc.). Ideal para definir contratos que se reutilicen en componentes, servicios o slices.

#### `utils/`

Funciones puras reutilizables como validadores, formateadores de fechas, convertidores de datos, etc.