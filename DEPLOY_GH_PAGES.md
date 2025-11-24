# Deploying the frontend to GitHub Pages

This repo contains a frontend built with Vite + React located in the `frontend/` folder.

Setup performed by the project assistant:
- `vite.config.js` is configured with `base: '/Health-Fit/'` and `build.outDir: '../docs'`.

What to do locally to build and publish:

1. Install Node.js (LTS) and npm if not already installed.
2. From the `frontend/` folder, install dependencies and build:

```powershell
cd "d:\M Tech\Sem_01\Agile Lab\Health Fit\frontend"
npm install
npm run build     # or npm run build:ghpages
```

3. After build completes, the production site will be in the repository `docs/` folder. GitHub Pages can serve the site directly from `main` branch `docs/` directory. In the repository Settings => Pages use `main` branch / `docs` folder.

Notes:
- The `base` value in `vite.config.js` is set to `/Health-Fit/`. If the repository name differs, update the `base` value accordingly.
- If you prefer to publish to the `gh-pages` branch instead, you can add the `gh-pages` npm package and use it to push the `docs/` content to `gh-pages` branch.

If you want me to remove the backend files so the repo contains only the frontend and `docs/` for Pages, confirm and I'll prune the backend into a branch or delete it from `main` (confirm which you prefer).
