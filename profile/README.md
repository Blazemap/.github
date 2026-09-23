<div align="center">
  <img src="https://raw.githubusercontent.com/Blazemap/.github/main/profile/logo.png" alt="Blazemap" width="100" />
  <h1>Blazemap</h1>
  <p>Forest and land fire awareness for Kalimantan, Indonesia.</p>
</div>

Blazemap brings community observations, satellite indications, weather context, and structured analysis into one human-reviewed workflow. Citizen reports remain observations until authorized reviewers assess them; satellite detections and AI suggestions are not automatic fire confirmations.

Website: [blazemap.my.id](https://blazemap.my.id/) (frontend application). The backend API and AI service are separate services; their public origins are not specified here.

## Source code and documentation

| Repository URL | Purpose | Technology | Installation and technical guide |
| --- | --- | --- | --- |
| [Blazemap-FE](https://github.com/Blazemap/Blazemap-FE) | Public web pages, citizen reporting, account dashboard, and restricted monitoring interface | React 19, TypeScript, Vite 8, TanStack Query, MapLibre GL | [Frontend README](https://github.com/Blazemap/Blazemap-FE#readme) |
| [Blazemap-BE](https://github.com/Blazemap/Blazemap-BE) | API, authentication, PostgreSQL data, evidence, case workflow, and integrations | Node.js 24, Express 5, Prisma 7, PostgreSQL | [Backend README](https://github.com/Blazemap/Blazemap-BE#readme) |
| [Blazemap-AI](https://github.com/Blazemap/Blazemap-AI) | Internal source-referenced decision-support analysis | Python 3.12+, FastAPI, Pydantic, Google Gen AI SDK | [AI README](https://github.com/Blazemap/Blazemap-AI#readme) |

Each linked source repository contains its installation guide, environment-variable instructions, architecture overview, and development commands. The backend also serves reference-only API documentation at `/api/docs` and OpenAPI JSON at `/api/openapi.json` on its configured origin. No real credentials are required to read the source or documentation; running external integrations requires your own authorized provider configuration.

## How the system fits together

1. The frontend collects citizen reports and displays role-appropriate case and publication information.
2. The backend authenticates users, stores reports and private evidence, assembles satellite and weather context, and enforces review, permission, and publication boundaries.
3. The internal AI service returns cited analysis with uncertainty for authorized human review. It does not verify fires or make operational decisions.

Start with the README in the repository you want to run. For the full local workflow, configure and migrate the backend separately, configure the AI service only if analysis is needed, then point the frontend at the backend origin.
