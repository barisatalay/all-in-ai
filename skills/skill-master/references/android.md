# Android (Gradle/Kotlin)

## Detection signals
- `settings.gradle` or `settings.gradle.kts`
- `build.gradle` or `build.gradle.kts`
- `gradle.properties`, `gradle/libs.versions.toml`
- `gradlew`, `gradle/wrapper/gradle-wrapper.properties`
- `app/src/main/AndroidManifest.xml`

## Multi-module signals
- Multiple `include(...)` in `settings.gradle*`
- Multiple dirs with `build.gradle*` + `src/`
- Common roots: `feature/`, `core/`, `library/`, `domain/`, `data/`

## Pre-generation sources
- `settings.gradle*` (module list)
- `build.gradle*` (root + modules)
- `gradle/libs.versions.toml` (dependencies)
- `config/detekt/detekt.yml` (if present)
- `**/AndroidManifest.xml`

## Codebase scan patterns

### Source roots
- `*/src/main/java/`, `*/src/main/kotlin/`

### Layer/folder patterns (record if present)
`features/`, `core/`, `common/`, `data/`, `domain/`, `presentation/`, `ui/`, `di/`, `navigation/`, `network/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| ViewModel | `@HiltViewModel`, `ViewModel()`, `MVI<` | viewmodel-mvi |
| Repository | `*Repository`, `*RepositoryImpl` | data-repository |
| UseCase | `operator fun invoke`, `*UseCase` | domain-usecase |
| Room Entity | `@Entity`, `@PrimaryKey`, `@ColumnInfo` | room-entity |
| Room DAO | `@Dao`, `@Query`, `@Insert`, `@Update` | room-dao |
| Migration | `Migration(`, `@Database(version=` | room-migration |
| Type Converter | `@TypeConverter`, `@TypeConverters` | type-converter |
| DTO | `@SerializedName`, `*Request`, `*Response` | network-dto |
| Compose Screen | `@Composable`, `NavGraphBuilder.` | compose-screen |
| Bottom Sheet | `ModalBottomSheet`, `*BottomSheet(` | bottomsheet-screen |
| Navigation | `@Route`, `NavGraphBuilder.`, `composable(` | navigation-route |
| Hilt Module | `@Module`, `@Provides`, `@Binds`, `@InstallIn` | hilt-module |
| Worker | `@HiltWorker`, `CoroutineWorker`, `WorkManager` | worker-task |
| DataStore | `DataStore<Preferences>`, `preferencesDataStore` | datastore-preference |
| Retrofit API | `@GET`, `@POST`, `@PUT`, `@DELETE` | retrofit-api |
| Mapper | `*.toModel()`, `*.toEntity()`, `*.toDto()` | data-mapper |
| Interceptor | `Interceptor`, `intercept()` | network-interceptor |
| Paging | `PagingSource`, `Pager(`, `PagingData` | paging-source |
| Broadcast Receiver | `BroadcastReceiver`, `onReceive(` | broadcast-receiver |
| Android Service | `: Service()`, `ForegroundService` | android-service |
| Notification | `NotificationCompat`, `NotificationChannel` | notification-builder |
| Analytics | `FirebaseAnalytics`, `logEvent` | analytics-event |
| Feature Flag | `RemoteConfig`, `FeatureFlag` | feature-flag |
| App Widget | `AppWidgetProvider`, `GlanceAppWidget` | app-widget |
| Unit Test | `@Test`, `MockK`, `mockk(`, `every {` | unit-test |

## Mandatory output sections

Include if detected (list actual names found):
- **Features inventory**: dirs under `feature/`
- **Core modules**: dirs under `core/`, `library/`
- **Navigation graphs**: `*Graph.kt`, `*Navigator*.kt`
- **Hilt modules**: `@Module` classes, `di/` contents
- **Retrofit APIs**: `*Api.kt` interfaces
- **Room databases**: `@Database` classes
- **Workers**: `@HiltWorker` classes
- **Proguard**: `proguard-rules.pro` if present

## Command sources
- README/docs invoking `./gradlew`
- CI workflows with Gradle commands
- Common: `./gradlew assemble`, `./gradlew test`, `./gradlew lint`
- Only include commands present in repo

## Key paths
- `app/src/main/`, `app/src/main/res/`
- `app/src/main/java/`, `app/src/main/kotlin/`
- `app/src/test/`, `app/src/androidTest/`
- `library/database/migration/` (Room migrations)
