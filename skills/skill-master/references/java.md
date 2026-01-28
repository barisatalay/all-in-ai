# Java/JVM (Spring, etc.)

## Detection signals
- `pom.xml` (Maven)
- `build.gradle`, `build.gradle.kts` (Gradle)
- `settings.gradle` (multi-module)
- `src/main/java/`, `src/main/kotlin/`
- `application.properties`, `application.yml`

## Multi-module signals
- Multiple `pom.xml` with `<modules>`
- Multiple `build.gradle` with `include()`
- `modules/`, `services/` directories

## Pre-generation sources
- `pom.xml` or `build.gradle*` (dependencies)
- `application.properties/yml` (config)
- `settings.gradle` (modules)
- `docker-compose.yml` (services)

## Codebase scan patterns

### Source roots
- `src/main/java/`, `src/main/kotlin/`
- `src/test/java/`, `src/test/kotlin/`

### Layer/folder patterns (record if present)
`controller/`, `service/`, `repository/`, `model/`, `entity/`, `dto/`, `config/`, `exception/`, `util/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| REST Controller | `@RestController`, `@GetMapping`, `@PostMapping` | spring-controller |
| Service | `@Service`, `class *Service` | spring-service |
| Repository | `@Repository`, `JpaRepository`, `CrudRepository` | spring-repository |
| Entity | `@Entity`, `@Table`, `@Id` | jpa-entity |
| DTO | `class *DTO`, `class *Request`, `class *Response` | dto-pattern |
| Config | `@Configuration`, `@Bean` | spring-config |
| Component | `@Component`, `@Autowired` | spring-component |
| Security | `@EnableWebSecurity`, `SecurityFilterChain` | spring-security |
| Validation | `@Valid`, `@NotNull`, `@Size` | validation-pattern |
| Exception Handler | `@ControllerAdvice`, `@ExceptionHandler` | exception-handler |
| Scheduler | `@Scheduled`, `@EnableScheduling` | scheduled-task |
| Event | `ApplicationEvent`, `@EventListener` | event-listener |
| Flyway Migration | `V*__*.sql`, `flyway` | flyway-migration |
| Liquibase | `changelog*.xml`, `liquibase` | liquibase-migration |
| Unit Test | `@Test`, `@SpringBootTest`, `MockMvc` | spring-test |
| Integration Test | `@DataJpaTest`, `@WebMvcTest` | integration-test |

## Mandatory output sections

Include if detected:
- **Controllers**: REST endpoints
- **Services**: business logic
- **Repositories**: data access (JPA, JDBC)
- **Entities/DTOs**: data models
- **Configuration**: Spring beans, profiles
- **Security**: auth config

## Command sources
- `pom.xml` plugins, `build.gradle` tasks
- README/docs, CI
- Common: `./mvnw`, `./gradlew`, `mvn test`, `gradle test`
- Only include commands present in repo

## Key paths
- `src/main/java/`, `src/main/kotlin/`
- `src/main/resources/`
- `src/test/`
- `db/migration/` (Flyway)
