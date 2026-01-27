# Dart / Flutter

## Detection signals
- `pubspec.yaml`, `pubspec.lock`
- `analysis_options.yaml`
- `lib/`
- `android/`, `ios/`, `web/`, `macos/`, `windows/`, `linux/`

## Multi-module signals
- `melos.yaml` (Flutter monorepo)
- Multiple `pubspec.yaml` under `packages/`, `apps/`, or `plugins/`

## Before generating, analyze these sources
- `pubspec.yaml`, `pubspec.lock`
- `analysis_options.yaml`
- `melos.yaml` (if monorepo)
- `lib/`, `test/`, and platform folders (`android/`, `ios/`, etc.)

## Codebase scan (Flutter-specific)
- Source roots: `lib/`, `test/`
- Entry point (record only if present): `lib/main.dart`
- Layer folders (record only if present):
  `features/`, `core/`, `data/`, `domain/`, `presentation/`
- State management (record only if present):
  `Bloc`, `Cubit`, `ChangeNotifier`, `Provider`, `Riverpod`
- Widget naming (record only if present):
  `*Screen`, `*Page`

## Mandatory output (Flutter module CLAUDE.md)
Include these if detected (list actual names found):
- **Features**: list dirs under `features/` or `lib/`
- **Core modules**: list dirs under `core/` (if present)
- **State management**: list Bloc/Cubit/Provider setup
- **Repositories**: list repository classes
- **Data sources**: list remote/local data source classes
- **Widgets**: list shared widget directories

## Command sources
- README/docs or CI invoking `flutter`
- Repo scripts that call `flutter` or `dart`
- `flutter run`, `flutter test`, `flutter pub get` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `lib/`, `test/`
- `android/`, `ios/`
