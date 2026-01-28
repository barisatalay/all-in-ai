# Flutter/Dart

## Detection signals
- `pubspec.yaml`
- `lib/main.dart`
- `android/`, `ios/`, `web/` directories
- `.dart_tool/`
- `analysis_options.yaml`

## Multi-module signals
- `melos.yaml` (monorepo)
- Multiple `pubspec.yaml` in subdirs
- `packages/` directory

## Pre-generation sources
- `pubspec.yaml` (dependencies)
- `analysis_options.yaml`
- `build.yaml` (if using build_runner)
- `lib/main.dart` (entry point)

## Codebase scan patterns

### Source roots
- `lib/`, `test/`

### Layer/folder patterns (record if present)
`screens/`, `widgets/`, `models/`, `services/`, `providers/`, `repositories/`, `utils/`, `constants/`, `bloc/`, `cubit/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Screen/Page | `*Screen`, `*Page`, `extends StatefulWidget` | flutter-screen |
| Widget | `extends StatelessWidget`, `extends StatefulWidget` | flutter-widget |
| BLoC | `extends Bloc<`, `extends Cubit<` | bloc-pattern |
| Provider | `ChangeNotifier`, `Provider.of<`, `context.read<` | provider-pattern |
| Riverpod | `@riverpod`, `ref.watch`, `ConsumerWidget` | riverpod-provider |
| GetX | `GetxController`, `Get.put`, `Obx(` | getx-controller |
| Repository | `*Repository`, `abstract class *Repository` | data-repository |
| Service | `*Service` | service-layer |
| Model | `fromJson`, `toJson`, `@JsonSerializable` | json-model |
| Freezed | `@freezed`, `part '*.freezed.dart'` | freezed-model |
| API Client | `Dio`, `http.Client`, `Retrofit` | api-client |
| Navigation | `Navigator`, `GoRouter`, `auto_route` | flutter-navigation |
| Localization | `AppLocalizations`, `l10n`, `intl` | flutter-l10n |
| Testing | `testWidgets`, `WidgetTester`, `flutter_test` | widget-test |
| Integration Test | `integration_test`, `IntegrationTestWidgetsFlutterBinding` | integration-test |

## Mandatory output sections

Include if detected:
- **Screens inventory**: dirs under `screens/`, `pages/`
- **State management**: BLoC, Provider, Riverpod, GetX
- **Navigation setup**: GoRouter, auto_route, Navigator
- **DI approach**: get_it, injectable, manual
- **API layer**: Dio, http, Retrofit
- **Models**: Freezed, json_serializable

## Command sources
- `pubspec.yaml` scripts (if using melos)
- README/docs
- Common: `flutter run`, `flutter test`, `flutter build`
- Only include commands present in repo

## Key paths
- `lib/`, `test/`
- `lib/screens/`, `lib/widgets/`
- `lib/bloc/`, `lib/providers/`
- `assets/`
