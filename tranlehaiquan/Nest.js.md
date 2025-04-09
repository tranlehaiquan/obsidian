## Term
- Controller
- Services | Repo
- DTO (Validate)
- Modules
- Providers (Injectable)
- Decorator
- Guard

## Setup mono repo with Nest

Can setup easy with CLI 

```bash
npm install -g @nestjs/cli
nest new my-nest-project
pnpm run start:dev
```

Or manual setup

```bash
pnpm add @nestjs/core @nestjs/common rxjs reflect-metadata
```

A basic structure will be:

```bash
src
- app.controller.spec.ts
- app.controller.ts
- app.module.ts
- app.service.ts
- main.ts # -> app start here
```

## Controller

Controller using for handle incoming request. A sample Controller:

```typescript
import { Controller, Get } from '@nest/commn';

@Controller('cats')

```

## Life Circle
## Nest Cli

Service vs Repository
- **Service:** Executes business rules, performs calculations, orchestrates data retrieval from multiple sources, and may involve complex logic based on application needs.
- **Repository:** Performs CRUD (Create, Read, Update, Delete) operations on data within the database, providing a simple interface to retrieve and manipulate data without exposing underlying database details.


## More info

IOC https://en.wikipedia.org/wiki/Inversion_of_control
