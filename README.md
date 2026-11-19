<div align="center">

<img width="100%" alt="Kevin Chansa, animated forest banner" src="assets/forest-banner.svg" />

<a href="https://github.com/yesterdaygrace">
  <img alt="typing" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=800&color=4ADE80&center=true&vCenter=true&width=720&height=44&lines=Junior+Software+Engineer+%40+Sahabat+Unggul;Backend+%C2%B7+Databases+%C2%B7+DevOps;Laravel+%E2%86%92+Go+%2B+TypeScript;Database+%E2%86%92+API+%E2%86%92+Infra+%E2%86%92+Security" />
</a>

<a href="https://www.linkedin.com/in/kevin-van-diesel-chansa/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="https://yesterdaygrace.github.io/portfolio/"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-live-16a34a?style=for-the-badge&logo=githubpages&logoColor=white" /></a>
<a href="https://dev-scout-lac.vercel.app"><img alt="DevScout demo" src="https://img.shields.io/badge/DevScout-demo-000?style=for-the-badge&logo=vercel&logoColor=white" /></a>
<img alt="Profile views" src="https://komarev.com/ghpvc/?username=yesterdaygrace&style=for-the-badge&color=16a34a&label=VIEWS&labelColor=0f172a" />

**[Projects](#-projects) · [Experience](#-experience) · [Stack](#-stack) · [Stats](#-stats) · [Learning](#-learning-next)**

</div>

<details open>
<summary><b>👋 Pick your path</b></summary>

<br/>

| If you are | Start here |
|---|---|
| **Hiring** | [Experience](#-experience) · [LinkedIn](https://www.linkedin.com/in/kevin-van-diesel-chansa/) |
| **Reviewing code** | [SijiSiyu](https://github.com/yesterdaygrace/SijiSiyu) · [Inventra](https://github.com/yesterdaygrace/Inventra) (each has a `docs/` folder) |
| **Short on time** | [DevScout live demo](https://dev-scout-lac.vercel.app) · [Portfolio](https://yesterdaygrace.github.io/portfolio/) |

</details>

I'm a junior software engineer working across backend, frontend, databases and DevOps. Informatics Engineering graduate (UKSW), 2+ years shipping and maintaining business software. At **PT Sahabat Unggul International** I maintain a factory's web and desktop apps and run its MySQL/MariaDB, Docker and Apache stack. Outside work I build Go and TypeScript projects to move beyond my Laravel base.

---

## 🚀 Projects

<table>
<tr>
<td width="50%" valign="top">

**🧵 [SijiSiyu](https://github.com/yesterdaygrace/SijiSiyu)**<br/>
Local-first Threads library with a Chromium extension that scans and syncs your saved posts.<br/>
`Nuxt` `SQLite` `SSE` `AES-256-GCM`<br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/SijiSiyu?style=flat-square&color=16a34a&labelColor=0f172a" />

</td>
<td width="50%" valign="top">

**🔎 [DevScout](https://github.com/yesterdaygrace/DevScout)** · [live](https://dev-scout-lac.vercel.app)<br/>
Search, compare and score GitHub developers. Collections, notes, per-user RLS.<br/>
`Vue 3` `Hono` `Supabase` `Vercel`<br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DevScout?style=flat-square&color=16a34a&labelColor=0f172a" />

</td>
</tr>
<tr>
<td width="50%" valign="top">

**📦 [Inventra](https://github.com/yesterdaygrace/Inventra)**<br/>
Multi-warehouse inventory: append-only ledger, reservations, idempotent stock operations.<br/>
`Go` `PostgreSQL 17` `React 19` `Docker`<br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/Inventra?style=flat-square&color=16a34a&labelColor=0f172a" />

</td>
<td width="50%" valign="top">

**🏦 [DAPENSE](https://github.com/yesterdaygrace/DAPENSE)**<br/>
Pension fund accounting: double-entry journals, period close, role-gated reports.<br/>
`Laravel` `PHP 8.3` `MySQL 8.4` `Redis`<br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DAPENSE?style=flat-square&color=16a34a&labelColor=0f172a" />

</td>
</tr>
</table>

<details>
<summary><b>🧵 SijiSiyu: how the scanner works</b></summary>

<br/>

```mermaid
flowchart LR
    X([Extension]) -->|sync| N[Nitro API] --> S[(SQLite WAL)]
    N <-->|OAuth| M[Threads API]
    N -- SSE --> U([Nuxt UI])
```

- Saving a post on `threads.net` streams it to the local app and shows a toast
- `MutationObserver` captures new bookmarks as the `/saved` feed scrolls; a bulk scan walks the full history
- Offline queue in `chrome.storage.local` flushes when the backend returns
- Why an extension: Meta's Threads API has no Saved or Unsave endpoint, so the project reads the logged-in site instead
- Tokens are AES-256-GCM encrypted at rest; sessions store only a SHA-256 hash; OAuth state guards against login CSRF

</details>

<details>
<summary><b>🔎 DevScout: how it's built</b></summary>

<br/>

```mermaid
flowchart LR
    A([Vue 3]) --> B[Hono proxy] --> G[GitHub API]
    A --> C[(Supabase + RLS)]
```

- The GitHub token stays server-side behind a Zod-validated Hono proxy with rate limiting and a request queue
- 6-factor candidate score (0 to 100) and a language breakdown over up to 20 non-fork repos
- Row Level Security on all 7 tables; Vitest unit tests and Playwright E2E

</details>

<details>
<summary><b>📦 Inventra: how it protects stock</b></summary>

<br/>

```mermaid
flowchart LR
    A([React]) --> B[Gin] --> C[Service] --> D[GORM] --> E[(PostgreSQL)]
```

- Append-only ledger: corrections add a row, balances are derived on read
- `SELECT ... FOR UPDATE` row locks inside transactions; idempotency keys return `409` on a changed body
- JWT with refresh rotation and reuse detection, DB-backed RBAC, failure-safe audit trail
- 17 tables, 13 migrations, CI coverage gate at 80% per package

</details>

<details>
<summary><b>🏦 DAPENSE: how it keeps books</b></summary>

<br/>

```mermaid
flowchart LR
    H[header_coas] --> C[coas] --> J[jurnalings] --> V[(views)]
    P[periodes] --> J
```

- 3NF schema, 8 core tables, `NUMERIC(15,2)` money columns and a balanced-journal guard
- Open, closed, then trial-balance snapshot per period
- 4 roles enforced by Policies and Gates; encrypted backups with 30-day retention

</details>

**More:** [CinemaSystem](https://github.com/yesterdaygrace/CinemaSystem) (Go, PostgreSQL `btree_gist` schedule-overlap guard; its Redis seat lock is a design proposal only) · [Nodex](https://github.com/yesterdaygrace/Nodex) (Go + Gin CRUD API with a contract-locking test suite) · [portfolio](https://github.com/yesterdaygrace/portfolio) (React 19, GitHub Pages CI)

---

## 💼 Experience

| When | Role |
|---|---|
| `Oct 2026 → now` | **Junior Software Engineer**, PT Sahabat Unggul International (contract) |
| `Aug 2024 → Dec 2025` | **Full Stack Web Developer (intern)**, Dana Pensiun Sekolah Kristen Salatiga |
| `Aug → Dec 2024` | **Teaching Assistant**, Web Developer course, UKSW |

<details open>
<summary><b>🏭 Sahabat Unggul: factory systems</b></summary>

<br/>

- Fix bugs and add features to SUI APPS V2.0 (web and desktop) from factory operations requirements
- Run MySQL/MariaDB: backups, query tuning, monitoring
- Support Linux servers: Docker containers, Apache and MySQL services, log monitoring
- Gather requirements with HR, Production, Finance and Warehouse; document code changes and procedures

`PHP` `JavaScript` `MySQL/MariaDB` `Docker` `Apache` `Linux`

</details>

<details>
<summary><b>🏦 Dana Pensiun: legacy VDOS to Laravel</b></summary>

<br/>

- Migrated a legacy VDOS-based financial system to Laravel
- Built General Ledger, Journal Processing, Cash & Bank, Financial Reporting and Balance Reconciliation modules
- Turned accounting workflows into features with finance stakeholders; 1 to 2 week sprints
- Tested at unit, integration and UAT level before releases
- Self-reported results: about 30 to 40% better operational efficiency and 25 to 30% fewer manual input errors

</details>

<details>
<summary><b>🎓 Teaching assistant</b></summary>

<br/>

4 classes, 100+ students, 400+ assignments reviewed. Taught HTML, CSS, PHP and MySQL, and standardized grading across classes.

</details>

---

## 🛠️ Stack

<div align="center">

<img alt="stack" src="https://skillicons.dev/icons?i=php,laravel,go,ts,js,react,vue,nuxt,tailwind,vite,postgres,mysql,sqlite,supabase,redis,linux,fedora,docker,nginx,githubactions,vercel,git&perline=11" />

</div>

<details>
<summary><b>Full breakdown</b></summary>

<br/>

| Layer | Tools |
|---|---|
| **Backend** | Laravel, Livewire, Go (Gin, GORM), Nuxt/Nitro, Hono, Zod, REST, OpenAPI, JWT, OAuth 2.0, SSE |
| **Frontend** | React 19, Vue 3, Nuxt, Pinia, TanStack Query, Tailwind, Vite, TypeScript, Chart.js |
| **Data** | PostgreSQL, MySQL/MariaDB, SQLite (WAL), Redis, Supabase, ERD design, indexing, query tuning |
| **Infra** | Linux, Docker Compose, Nginx, Apache, GitHub Actions, Vercel, systemd |
| **Security** | AES-256-GCM, JWT rotation, bcrypt, RBAC, RLS, rate limiting, govulncheck |
| **Testing** | testify, uber mock, Vitest, PHPUnit, Playwright, Postman |
| **Browser** | Chromium extensions, content scripts, MutationObserver |
| **AI tools** | Claude, Cursor, Codex, ChatGPT, OpenCode |

</details>

---

## 📊 Stats

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&theme=tokyonight&bg_color=0d1117&title_color=4ade80&icon_color=16a34a" />
  <img width="49%" alt="stats" src="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&bg_color=f8fafc&title_color=15803d&text_color=475569&icon_color=16a34a" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&theme=tokyonight&bg_color=0d1117&title_color=4ade80" />
  <img width="38%" alt="top languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&bg_color=f8fafc&title_color=15803d&text_color=475569" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&theme=tokyonight&background=0d1117&ring=4ade80&fire=16a34a&currStreakLabel=4ade80" />
  <img width="60%" alt="streak" src="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&background=f8fafc&ring=16a34a&fire=15803d&currStreakLabel=15803d" />
</picture>

</div>

<details>
<summary><b>Contribution graph</b></summary>

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=0d1117&color=4ade80&line=16a34a&point=ffffff&area=true&area_color=16a34a&hide_border=true" />
  <img width="100%" alt="activity graph" src="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=f8fafc&color=15803d&line=16a34a&point=0f172a&area=true&area_color=16a34a&hide_border=true" />
</picture>

</details>

---

## 🧪 Learning next

<img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
<img alt="Terraform" src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" />
<img alt="Prometheus" src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" />
<img alt="Grafana" src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" />
<img alt="RabbitMQ" src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" />
<img alt="Trivy" src="https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aqua&logoColor=white" />
<img alt="OWASP" src="https://img.shields.io/badge/OWASP-000?style=flat-square&logo=owasp&logoColor=white" />
<img alt="MCP" src="https://img.shields.io/badge/MCP-16a34a?style=flat-square" />
<img alt="RAG" src="https://img.shields.io/badge/RAG-16a34a?style=flat-square" />
<img alt="Distributed systems" src="https://img.shields.io/badge/Distributed_systems-0f172a?style=flat-square" />

```mermaid
flowchart LR
    A([Full stack]) --> B[Go + TypeScript] --> C[DevOps + Security] --> D[Cloud] --> E[AI automation] --> F([Distributed systems])
    style A fill:#16a34a,color:#fff,stroke:none
    style F fill:#15803d,color:#fff,stroke:none
```

<div align="center">

<img width="100%" alt="footer" src="https://capsule-render.vercel.app/api?type=waving&section=footer&height=110&color=0:14532d,50:16a34a,100:052e16" />

</div>
