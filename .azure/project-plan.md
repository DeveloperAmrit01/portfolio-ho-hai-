# Project Plan

**Status**: Approved
**Created**: 2026-10-04
**Mode**: NEW

---

## 1. Project Overview

**Goal**: Build a polished, responsive AI Engineer portfolio as a simple standalone HTML experience with navigation, hero, skills, featured projects, and direct contact actions; the supplied image and corporate theme are treated as brand inputs for the final design. The project is designed so that every module is independently testable.

**App Type**: Static + API
**API Login**: No
**Mode**: NEW

**Deployment Plan**: No deployment plan found

---

## 2. Frontend — Web App

| Component | Technology |
|-----------|-----------|
| **Language** | JavaScript |
| **Runtime** | Node |
| **Framework** | Plain HTML, CSS, and vanilla JavaScript |
| **Package Manager** | npm |
| **Test Runner** | Vitest |
| **Mocking Library** | vi.mock |
| **Test Command** | npm test |
| **Orchestration** | docker-compose |

---

## 3. Services Required

| Azure Service | Role in App | Environment Variable | Default Value (Local) | Classification |
|---------------|------------|---------------------|----------------------|----------------|
| Azure Static Web Apps | Host the portfolio and serve the landing page and project content publicly | STATIC_WEB_APP_URL | http://localhost | Essential |

---

## 4. Prerequisites

### Run

| Tool | Service(s) | Installed | Version |
|------|------------|-----------|---------|
| Node.js | frontend | ✅ | v26.10.0 |
| npm | frontend | ✅ | available through Node tooling |
| Python | frontend | ✅ | 3.14.7 |
| Git | frontend | ❓ | not detected |

### Debug

| Tool | Service(s) | Installed | Version |
|------|------------|-----------|---------|
| VS Code | frontend | ✅ | 1.140.0 |
| Docker Desktop | frontend | ❓ | not detected |

---

## 5. Project Structure

```
.
├── .azure/
│   ├── requirements.json
│   └── project-plan.md
├── .preview-temp/
│   ├── theme.css
│   ├── manifest.json
│   ├── home.html
│   └── projects.html
├── index.html
├── guitar 1.jpeg
└── images.jpg
```

---

## 6. Design System & UI

**Component Library**: Pico.css + native form controls
**Style Direction**: Modern product-story portfolio with calm contrast, editorial spacing, and a strong emphasis on technical credibility without feeling overly corporate.
**Typography**: Inter, system-ui

### Color Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `primary` | `#111827` | Brand color — primary button states, active navigation, focus highlights |
| `accent`  | `#38bdf8` | Secondary accents, highlight tags, hover emphasis |
| `surface` | `#f8fafc` | Page and card backgrounds |
| `text`    | `#0f172a` | Body text and headings |
| `muted`   | `#475569` | Secondary text, metadata, captions |
| `border`  | `#dfe7f1` | Dividers, card borders, input edges |

### Pages

| Page | Route | Purpose | Layout |
|------|-------|---------|--------|
| Home | `/` | Introduce the engineer, highlight experience, and direct visitors to key portfolio areas | `header + hero + grid + card-list + footer` |
| Projects | `/projects` | Showcase selected AI and engineering work with outcomes and technical stack | `header + list + split(a|b) + actions` |

### Sample Content

```
Home — portfolio overview:
| Role | Focus | Impact | Status |
| AI Engineer | LLM systems + product delivery | Built end-to-end workflows from ideation to deployment | Available |
| Product Builder | Human-centered tooling | Turned prototype ideas into dependable product experiences | Available |
| Systems Thinker | Applied AI in real business contexts | Improved clarity, speed, and product quality across teams | Available |

Projects — featured work:
| Project | Stack | Outcome | Status |
| Agentic Research Assistant | Python, RAG, LLM orchestration | Reduced manual investigation time for domain experts | Shipping |
| Portfolio + Case Study Microsite | JavaScript, HTML, CSS | Presented technical impact clearly and succinctly | Live |
| Internal Knowledge Copilot | Prompt design, retrieval, evaluation | Improved team access to reliable project context | Pilot |
```

---

## 7. Route Definitions

| # | Method | Path | Description | Request Body | Response Body | Status Codes |
|---|--------|------|-------------|-------------|--------------|-------------|
| 1 | GET | `/` | Landing page for the portfolio overview and hero section | — | HTML page content | 200 |
| 2 | GET | `/projects` | Showcase page for featured work and impact stories | — | HTML project list | 200 |

---

## 8. Next Steps

1. Run **azure-project-scaffold** to execute this plan
2. Run **azure-project-integrate** to wire the frontend to live data, smoke-test the backend, and create the migrations
3. Run **azure-debug-plan** → **azure-debug-generate** for Docker emulators and VS Code debugging
4. Run the **azure-deploy** agent when ready; it uses **azure-app-onboard** for architecture, cost estimation, IaC generation, provisioning, and health verification
