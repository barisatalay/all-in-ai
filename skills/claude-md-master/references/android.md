# Android (Gradle)

## Detection signals
- `settings.gradle` or `settings.gradle.kts`
- `build.gradle` or `build.gradle.kts`
- `gradle.properties`
- `gradle/libs.versions.toml`
- `gradlew`
- `gradle/wrapper/gradle-wrapper.properties`
- `app/src/main/AndroidManifest.xml`

## Multi-module signals
- Multiple `include(...)` or `includeBuild(...)` entries in `settings.gradle*`
- More than one module dir with `build.gradle*` and `src/`
- Common module roots like `feature/`, `core/`, `library/` (if present)

## Before generating, analyze these sources
- `settings.gradle` or `settings.gradle.kts`
- `build.gradle` or `build.gradle.kts` (root and modules)
- `gradle/libs.versions.toml`
- `gradle.properties`
- `config/detekt/detekt.yml` (if present)
- `app/src/main/AndroidManifest.xml` (or module manifests)

## Codebase scan (Android-specific)
- Source roots per module: `*/src/main/java/`, `*/src/main/kotlin/`
- Package tree for feature/layer folders (record only if present):
  `features/`, `core/`, `common/`, `data/`, `domain/`, `presentation/`,
  `ui/`, `di/`, `navigation/`, `network/`
- Annotation usage (record only if present):
  Hilt (`@HiltAndroidApp`, `@AndroidEntryPoint`, `@HiltViewModel`,
  `@Module`, `@InstallIn`, `@Provides`, `@Binds`),
  Compose (`@Composable`, `@Preview`),
  Room (`@Entity`, `@Dao`, `@Database`),
  WorkManager (`@HiltWorker`, `ListenableWorker`, `CoroutineWorker`),
  Serialization (`@Serializable`, `@Parcelize`),
  Retrofit (`@GET`, `@POST`, `@PUT`, `@DELETE`, `@Body`, `@Query`)
- Navigation patterns (record only if present): `NavHost`, `composable`

## Mandatory output (Android module CLAUDE.md)
Include these if detected (list actual names found):
- **Features inventory**: list dirs under `features/` (e.g., homepage, payment, auth)
- **Core modules**: list dirs under `core/` (e.g., data, network, localization)
- **Navigation graphs**: list `*Graph.kt` or `*Navigator*.kt` files
- **Hilt modules**: list `@Module` classes or `di/` package contents
- **Retrofit APIs**: list `*Api.kt` interfaces
- **Room databases**: list `@Database` classes
- **Workers**: list `@HiltWorker` classes
- **Proguard**: mention `proguard-rules.pro` if present

## Command sources
- README/docs or CI invoking Gradle wrapper
- Repo scripts that call `./gradlew`
- `./gradlew assemble`, `./gradlew test`, `./gradlew lint` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `app/src/main/`, `app/src/main/res/`
- `app/src/main/java/`, `app/src/main/kotlin/`
- `app/src/test/`, `app/src/androidTest/`
