# React Native

## Detection signals
- `package.json` with `react-native`
- `react-native.config.js`
- `metro.config.js`
- `ios/`, `android/`
- `babel.config.js`, `app.json`, `app.config.*`
- `eas.json`, `expo` in `package.json`

## Multi-module signals
- `pnpm-workspace.yaml`, `lerna.json`, `nx.json`, `turbo.json`
- Root `package.json` with `workspaces`
- `packages/` or `apps/` each with `package.json`

## Before generating, analyze these sources
- Root `package.json` and workspace config (`pnpm-workspace.yaml`, `lerna.json`,
  `nx.json`, `turbo.json`)
- `react-native.config.js`, `metro.config.js`
- `ios/` and `android/` native folders
- `app.json` / `app.config.*` / `eas.json` (if Expo)

## Codebase scan (React Native-specific)
- Source roots: `src/`, `app/`
- Entry points (record only if present):
  `index.js`, `index.ts`, `App.tsx`
- Native folders (record only if present): `ios/`, `android/`
- Navigation/state (record only if present):
  `react-navigation`, `redux`, `mobx`
- Native module patterns (record only if present):
  `NativeModules`, `TurboModule`

## Mandatory output (React Native module CLAUDE.md)
Include these if detected (list actual names found):
- **Screens/navigators**: list screen components and navigators
- **Components**: list shared component directories
- **Services/API**: list API client modules
- **State management**: list store setup
- **Native modules**: list custom native modules
- **Platform folders**: mention ios/ and android/ setup

## Command sources
- `package.json` scripts
- README/docs or CI
- Native build files in `ios/` and `android/`
- `expo` script usage in docs/scripts (if Expo)
- Only include commands present in repo

## Key paths to mention (only if present)
- `ios/`, `android/`
- `src/`, `app/`
