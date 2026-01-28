# React Native

## Detection signals
- `package.json` with `react-native`
- `metro.config.js`
- `app.json` or `app.config.js` (Expo)
- `android/`, `ios/` directories
- `babel.config.js` with metro preset

## Multi-module signals
- Monorepo with `packages/`
- Multiple `app.json` files
- Nx workspace with React Native

## Pre-generation sources
- `package.json` (dependencies, scripts)
- `app.json` or `app.config.js`
- `metro.config.js`
- `babel.config.js`
- `tsconfig.json`

## Codebase scan patterns

### Source roots
- `src/`, `app/`

### Layer/folder patterns (record if present)
`screens/`, `components/`, `navigation/`, `services/`, `hooks/`, `store/`, `api/`, `utils/`, `assets/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Screen | `*Screen`, `export function *Screen` | rn-screen |
| Component | `export function *()`, `StyleSheet.create` | rn-component |
| Navigation | `createNativeStackNavigator`, `NavigationContainer` | rn-navigation |
| Hook | `use*`, `export function use*()` | rn-hook |
| Redux | `createSlice`, `configureStore` | redux-slice |
| Zustand | `create(`, `useStore` | zustand-store |
| React Query | `useQuery`, `useMutation` | react-query |
| Native Module | `NativeModules`, `TurboModule` | native-module |
| Async Storage | `AsyncStorage`, `@react-native-async-storage` | async-storage |
| SQLite | `expo-sqlite`, `react-native-sqlite-storage` | sqlite-storage |
| Push Notification | `@react-native-firebase/messaging`, `expo-notifications` | push-notification |
| Deep Link | `Linking`, `useURL`, `expo-linking` | deep-link |
| Animation | `Animated`, `react-native-reanimated` | rn-animation |
| Gesture | `react-native-gesture-handler`, `Gesture` | rn-gesture |
| Testing | `@testing-library/react-native`, `render` | rntl-test |

## Mandatory output sections

Include if detected:
- **Screens inventory**: dirs under `screens/`
- **Navigation structure**: stack, tab, drawer navigators
- **State management**: Redux, Zustand, Context
- **Native modules**: custom native code
- **Storage layer**: AsyncStorage, SQLite, MMKV
- **Platform-specific**: `*.android.tsx`, `*.ios.tsx`

## Command sources
- `package.json` scripts
- README/docs
- Common: `npm run android`, `npm run ios`, `npx expo start`
- Only include commands present in repo

## Key paths
- `src/screens/`, `src/components/`
- `src/navigation/`, `src/store/`
- `android/app/`, `ios/*/`
- `assets/`
