# React (Web)

## Detection signals
- `package.json` with `react`, `react-dom`
- `vite.config.ts`, `next.config.js`, `craco.config.js`
- `tsconfig.json` or `jsconfig.json`
- `src/App.tsx` or `src/App.jsx`
- `public/index.html` (CRA)

## Multi-module signals
- `pnpm-workspace.yaml`, `lerna.json`
- Multiple `package.json` in subdirs
- `packages/`, `apps/` directories
- Nx workspace (`nx.json`)

## Pre-generation sources
- `package.json` (dependencies, scripts)
- `tsconfig.json` (paths, compiler options)
- `vite.config.*`, `next.config.*`, `webpack.config.*`
- `.env.example` (env vars)

## Codebase scan patterns

### Source roots
- `src/`, `app/`, `pages/`

### Layer/folder patterns (record if present)
`components/`, `hooks/`, `services/`, `utils/`, `store/`, `api/`, `types/`, `contexts/`, `features/`, `layouts/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Component | `export function *()`, `export const * =` with JSX | react-component |
| Hook | `use*`, `export function use*()` | custom-hook |
| Context | `createContext`, `useContext`, `*Provider` | react-context |
| Redux | `createSlice`, `configureStore`, `useSelector` | redux-slice |
| Zustand | `create(`, `useStore` | zustand-store |
| React Query | `useQuery`, `useMutation`, `QueryClient` | react-query |
| Form | `useForm`, `react-hook-form`, `Formik` | form-handling |
| Router | `createBrowserRouter`, `Route`, `useNavigate` | react-router |
| API Client | `axios`, `fetch`, `ky` | api-client |
| Testing | `@testing-library/react`, `render`, `screen` | rtl-test |
| Storybook | `*.stories.tsx`, `Meta`, `StoryObj` | storybook |
| Styled | `styled-components`, `@emotion`, `styled(` | styled-component |
| Tailwind | `className="*"`, `tailwind.config.js` | tailwind-usage |
| i18n | `useTranslation`, `i18next`, `t()` | i18n-usage |
| Auth | `useAuth`, `AuthProvider`, `PrivateRoute` | auth-pattern |

## Mandatory output sections

Include if detected:
- **Components inventory**: dirs under `components/`
- **Features/pages**: dirs under `features/`, `pages/`
- **State management**: Redux, Zustand, Context
- **Routing setup**: React Router, Next.js pages
- **API layer**: axios instances, fetch wrappers
- **Styling approach**: CSS modules, Tailwind, styled-components
- **Form handling**: react-hook-form, Formik

## Command sources
- `package.json` scripts section
- README/docs
- CI workflows
- Common: `npm run dev`, `npm run build`, `npm test`
- Only include commands present in repo

## Key paths
- `src/components/`, `src/hooks/`
- `src/pages/`, `src/features/`
- `src/store/`, `src/api/`
- `public/`, `dist/`, `build/`
