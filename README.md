# State (Render)

Same demo as [state](https://github.com/rivet-dev/rivet/tree/main/examples/state): chat room showing persistent actor state with send/clear/history, packaged with a [`render.yaml`](./render.yaml) Blueprint for [Render](https://render.com/) + [Rivet Cloud](https://rivet.dev/).

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/ojusave/rivet-state)

## Deploy on Render

Set **Root Directory** to `examples/state-render` if deploying from the monorepo. Add **`RIVET_ENDPOINT`** (`sk_…`) and **`RIVET_PUBLIC_ENDPOINT`** (`pk_…`) from [dashboard.rivet.dev](https://dashboard.rivet.dev), then register the service HTTPS URL in Rivet. **`RIVET_ENVOY_VERSION`** is derived automatically from `RENDER_GIT_COMMIT`.

## Implementation

- **Actor** ([`src/actors.ts`](./src/actors.ts)): `chatRoom` with persistent message list, `sendMessage`, `clearMessages`, and broadcast events
- **Server** ([`src/server.ts`](./src/server.ts)): Hono app routing `/api/rivet/*` to the registry handler
- **Frontend** ([`frontend/App.tsx`](./frontend/App.tsx)): `useActor` hook with real-time event subscriptions and auto-scroll

**Reference:** [state](https://rivet.dev/docs/actors/state) · [actions](https://rivet.dev/docs/actors/actions) · [events](https://rivet.dev/docs/actors/events) · [Blueprint spec](https://render.com/docs/blueprint-spec)

MIT
