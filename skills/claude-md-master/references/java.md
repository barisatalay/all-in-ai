# Java / JVM

## Detection signals
- `pom.xml` or `build.gradle*`
- `settings.gradle`, `gradle.properties`
- `mvnw`, `gradlew`
- `gradle/wrapper/gradle-wrapper.properties`
- `src/main/java`, `src/test/java`, `src/main/kotlin`
- `src/main/resources/application.yml`, `src/main/resources/application.properties`

## Multi-module signals
- `settings.gradle*` includes multiple modules
- Parent `pom.xml` with `<modules>` (packaging `pom`)
- Multiple `build.gradle*` or `pom.xml` files in subdirs

## Before generating, analyze these sources
- `settings.gradle*` and `build.gradle*` (if Gradle)
- Parent and module `pom.xml` (if Maven)
- `gradle/libs.versions.toml` (if present)
- `gradle.properties` / `mvnw` / `gradlew`
- `src/main/resources/application.yml|application.properties` (if present)

## Codebase scan (Java/JVM-specific)
- Source roots: `src/main/java`, `src/main/kotlin`, `src/test/java`, `src/test/kotlin`
- Package/layer folders (record only if present):
  `controller`, `service`, `repository`, `domain`, `model`, `dto`, `config`, `client`
- Framework annotations (record only if present):
  `@SpringBootApplication`, `@RestController`, `@Controller`, `@Service`,
  `@Repository`, `@Component`, `@Configuration`, `@Bean`, `@Transactional`
- Persistence/validation (record only if present):
  `@Entity`, `@Table`, `@Id`, `@OneToMany`, `@ManyToOne`, `@Valid`, `@NotNull`
- Entry points (record only if present):
  `*Application` classes with `main`

## Mandatory output (Java/JVM module CLAUDE.md)
Include these if detected (list actual names found):
- **Controllers**: list `@RestController` or `@Controller` classes
- **Services**: list `@Service` classes
- **Repositories**: list `@Repository` classes or JPA interfaces
- **Entities**: list `@Entity` classes
- **Configuration**: list `@Configuration` classes
- **Security**: list security config or auth filters
- **Profiles**: list Spring profiles in use

## Command sources
- Maven/Gradle wrapper scripts
- README/docs or CI
- `./mvnw spring-boot:run`, `./gradlew bootRun` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/main/java`, `src/test/java`
- `src/main/kotlin`, `src/test/kotlin`
- `src/main/resources`, `src/test/resources`
- `src/main/java/**/controller`, `src/main/java/**/service`, `src/main/java/**/repository`
