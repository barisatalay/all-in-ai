# Node.js

## Detection signals
- `package.json` (without react/react-native)
- `tsconfig.json`
- `node_modules/`
- `*.js`, `*.ts`, `*.mjs`, `*.cjs` entry files

## Multi-module signals
- `pnpm-workspace.yaml`, `lerna.json`
- `nx.json`, `turbo.json`
- Multiple `package.json` in subdirs
- `packages/`, `apps/` directories

## Pre-generation sources
- `package.json` (dependencies, scripts)
- `tsconfig.json` (paths, compiler options)
- `.env.example` (env vars)
- `docker-compose.yml` (services)

## Codebase scan patterns

### Source roots
- `src/`, `lib/`, `app/`

### Layer/folder patterns (record if present)
`controllers/`, `services/`, `models/`, `routes/`, `middleware/`, `utils/`, `config/`, `types/`, `repositories/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Express Route | `app.get(`, `app.post(`, `Router()` | express-route |
| Express Middleware | `(req, res, next)`, `app.use(` | express-middleware |
| NestJS Controller | `@Controller`, `@Get`, `@Post` | nestjs-controller |
| NestJS Service | `@Injectable`, `@Service` | nestjs-service |
| NestJS Module | `@Module`, `imports:`, `providers:` | nestjs-module |
| Fastify Route | `fastify.get(`, `fastify.post(` | fastify-route |
| GraphQL Resolver | `@Resolver`, `@Query`, `@Mutation` | graphql-resolver |
| TypeORM Entity | `@Entity`, `@Column`, `@PrimaryGeneratedColumn` | typeorm-entity |
| Prisma Model | `prisma.*.create`, `prisma.*.findMany` | prisma-usage |
| Mongoose Model | `mongoose.Schema`, `mongoose.model(` | mongoose-model |
| Sequelize Model | `Model.init`, `DataTypes` | sequelize-model |
| Queue Worker | `Bull`, `BullMQ`, `process(` | queue-worker |
| Cron Job | `@Cron`, `node-cron`, `cron.schedule` | cron-job |
| WebSocket | `ws`, `socket.io`, `io.on(` | websocket-handler |
| Unit Test | `describe(`, `it(`, `expect(`, `jest` | jest-test |
| E2E Test | `supertest`, `request(app)` | e2e-test |

## Mandatory output sections

Include if detected:
- **Routes/controllers**: API endpoints
- **Services layer**: business logic
- **Database**: ORM/ODM usage (TypeORM, Prisma, Mongoose)
- **Middleware**: auth, validation, error handling
- **Background jobs**: queues, cron jobs
- **WebSocket handlers**: real-time features

## Command sources
- `package.json` scripts section
- README/docs
- CI workflows
- Common: `npm run dev`, `npm run build`, `npm test`
- Only include commands present in repo

## Key paths
- `src/`, `lib/`
- `src/routes/`, `src/controllers/`
- `src/services/`, `src/models/`
- `prisma/`, `migrations/`
