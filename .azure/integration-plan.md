# Integration Hand-off

## Frontend
- Project folder: .
- Dev server: `python -m http.server 8000`
- Build/preview: static HTML served from repo root
- Pages: `/`, `/projects`
- Principal files: `index.html`, `projects.html`, `styles.css`, `script.js`
- Routes inventory:
  - GET `/` — home/overview page
  - GET `/projects` — portfolio project list

## Backend
- Type: None (static portfolio site)
- Runtime: N/A
- Health endpoint: N/A
- DB: None
- Migration tool: N/A
- Seed data: N/A

## Azure services
- Essential: Azure Static Web Apps
- Environment variable: `STATIC_WEB_APP_URL`
- Default value: `http://localhost`

## Shared types / API seam
- No live API layer is required for this static build.
- No mock client or mock data layer is present.
- No code generation or database migration work is needed before deployment.

## Delivery notes
- Keep this as a static, search-friendly portfolio experience for the approved design.
- Do not add seed data or backend logic unless the next phase explicitly requires it.
- UI should remain aligned with the approved preview located in `.azure/.preview-temp`.
