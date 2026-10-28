# Snapshot verification

Checks recorded in the isolated source copy on 2026-10-28. These results are not a production certification.

| Directory | Command | Result |
| --- | --- | --- |
| `backend` | `npm ci --ignore-scripts --no-audit --no-fund` | Passed |
| `backend` | `npx prisma generate --schema prisma/schema.prisma` | Passed |
| `backend` | `npm run build` | Passed |
| `frontend` | `npm ci --ignore-scripts --no-audit --no-fund` | Passed |

Python application files passed syntax parsing. This does not execute imports, launch the desktop UI, contact a portal or validate an external integration.

## Publication boundaries

- Operational sources remained read-only; only isolated copies were prepared.
- No corporate service, real-record import, live notification or production database was invoked.
- No deployment command, deploy workflow or new hosting integration is part of this update. Included Vercel configurations disable Git-driven deployments.
- New source imports exclude local environments, databases, generated outputs and operational documents.
- Existing Git history is preserved. Historical public names or assets may remain in old commits; current snapshots use neutral public presentation.

## Production npm dependency audit — world-cup-prediction-league/frontend

`npm audit --omit=dev --json` reported 0 critical, 4 high, 1 moderate, 0 low findings in the installed dependency tree on 2026-10-28. Counts include transitive packages and do not establish exploitability in this application.

| Package | Severity | Direct dependency |
| --- | --- | --- |
| `axios` | high | Yes |
| `follow-redirects` | high | No |
| `form-data` | high | No |
| `react-router` | high | No |
| `react-router-dom` | moderate | Yes |

These advisories remain a maintenance item. This documentation/publication task did not perform dependency upgrades or validate a production security posture.

## Production npm dependency audit — world-cup-prediction-league/backend

`npm audit --omit=dev --json` reported 1 critical, 6 high, 1 moderate, 0 low findings in the installed dependency tree on 2026-10-28. Counts include transitive packages and do not establish exploitability in this application.

| Package | Severity | Direct dependency |
| --- | --- | --- |
| `@nestjs/platform-express` | high | Yes |
| `@prisma/config` | high | No |
| `body-parser` | high | No |
| `deepmerge-ts` | high | No |
| `multer` | high | No |
| `prisma` | high | Yes |
| `proxy-addr` | critical | No |
| `qs` | moderate | No |

These advisories remain a maintenance item. This documentation/publication task did not perform dependency upgrades or validate a production security posture.
