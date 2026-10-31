# LONDON IS... — server-backed MVP

## Start
Requires Node.js 20+. No npm dependencies.

```bash
export ADMIN_PASSWORD='your-unique-password-at-least-12-chars'
export SESSION_SECRET='a-random-secret-at-least-32-characters-long'
export FOOTBALL_DATA_TOKEN='your-football-data-org-key'
export OPENAI_API_KEY='your-openai-key' # optional; uses template drafts otherwise
npm start
```

Open http://localhost:3000. Click EDITORIAL to sign in. CHECK NEW RESULTS creates draft suggestions from recent qualifying EPL matches; APPROVE & PUBLISH changes the public page. No draft can self-publish. Manual verdicts are also possible.

## Important before public launch
- Use HTTPS and NODE_ENV=production behind a trusted reverse proxy.
- Persistent storage: data.json must live on a persistent volume; otherwise history is lost on redeploy.
- Password login is a starter implementation. Add rate limiting, audit logs, CSRF protection, and preferably managed authentication before internet exposure.
- API results are EPL only; cup competitions and cultural context need separate licensed sources.
- Club list is fixed for this prototype; update automatically from PL teams data before each season.
- The current default verdict and any initial history are illustrative, not verified records.
- Polling is manual in this MVP; a scheduled job is the next step.
- Football API terms and AI API costs must be reviewed before launch.
