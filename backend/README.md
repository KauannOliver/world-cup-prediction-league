# Prediction League API

The NestJS service owns registration and approval, tournament configuration, group/knockout predictions, score calculation and administrative results. PostgreSQL stores the data through Prisma.

## Local startup

Use a separate local PostgreSQL database. Copy `.env.example` to `.env` and configure `DATABASE_URL`, `JWT_SECRET`, `FIRST_ADMIN_EMAIL` and `FIRST_ADMIN_PASSWORD` with local values. Administrator bootstrap values are required by the seed and must never be committed.

```powershell
npm ci
npx prisma generate
# Only after verifying the target is a new local database:
npx prisma migrate dev
npx prisma db seed
npm run start:dev
```

The service uses port 3000 unless configured otherwise. Generating the Prisma client does not migrate or seed a database. Review the seed and any destructive administrative endpoint before using them; no production database was touched during source publication.

## HTTP boundaries

| Controller prefix | Responsibility |
| --- | --- |
| `/auth` | Registration, login and current account |
| `/admin/users` | Pending users and account approval |
| `/groups` | Tournament groups and their teams |
| `/predictions` | Participant settings and group/knockout selections |
| `/admin` | Deadlines, phase visibility, results, bracket generation and recalculation |

Controller guards define the access requirements; consult the actual controller and DTO before integrating. This table is an orientation guide, not a complete OpenAPI contract.

## Verification

`npm run build` compiles the API. The scaffold unit test is not evidence of complete scoring, authorization or tournament correctness. End-to-end tests require a separately configured application/database and were not run in this publication task. See [snapshot verification](../docs/VERIFICATION.md) for exact checks and dependency advisories.

The frontend is a separate Vite application in `../frontend`. No deployment workflow is included.
