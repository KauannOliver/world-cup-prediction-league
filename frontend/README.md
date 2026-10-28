# Prediction League Web Client

React, TypeScript, Vite and Tailwind interface for group-stage predictions, knockout selections, rankings and administration. The app communicates with the separate NestJS backend through `src/api/api.ts`.

```powershell
npm ci
npm run dev
npm run build
```

Start the API with a new local database before testing registration and predictions. The Vite development server normally runs on port 5173. Review the API base configuration before connecting to an environment; no live game was modified during source review.

`npm run build` runs TypeScript project checks before bundling. `npm run lint` is a separate quality check. Source publication preserves the Portuguese interface and the scoring implementation. Tests of actual tournament rules, account approval and browser flows require an isolated integration environment.

The included Vercel configuration disables Git-triggered deployments. See [verification and limitations](../docs/VERIFICATION.md).
