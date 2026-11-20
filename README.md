<div align="center">

<img width="100%" alt="Kevin Chansa, animated Y2K halftone banner" src="assets/y2k-dots-banner.svg" />

<a href="https://github.com/yesterdaygrace">
  <img alt="typing" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=800&color=71717A&center=true&vCenter=true&width=720&height=44&lines=Junior+Software+Engineer+%40+Sahabat+Unggul;Backend+%C2%B7+Databases+%C2%B7+DevOps;Laravel+%E2%86%92+Go+%2B+TypeScript;Database+%E2%86%92+API+%E2%86%92+Infra+%E2%86%92+Security" />
</a>

<a href="https://www.linkedin.com/in/kevin-van-diesel-chansa/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="https://yesterdaygrace.github.io/portfolio/"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-live-18181b?style=for-the-badge&logo=githubpages&logoColor=white" /></a>
<a href="https://dev-scout-lac.vercel.app"><img alt="DevScout demo" src="https://img.shields.io/badge/DevScout-demo-18181b?style=for-the-badge&logo=vercel&logoColor=white" /></a>
<a href="https://github.com/yesterdaygrace?tab=repositories"><img alt="Repositories" src="https://img.shields.io/badge/Repos-all-18181b?style=for-the-badge&logo=github&logoColor=white" /></a>
<img alt="Profile views" src="https://komarev.com/ghpvc/?username=yesterdaygrace&style=for-the-badge&color=3f3f46&label=VIEWS&labelColor=18181b" />

**[🚀 Projects](#-projects) · [💼 Experience](#-experience) · [🧰 Stack](#-stack) · [📊 Stats](#-stats) · [🧪 Learning](#-learning-next)**

</div>

<details open>
<summary><b>👋 Pick your path</b></summary>

<br/>

| If you are | Start here |
|---|---|
| 🎯 **Hiring** | [Experience](#-experience) · [LinkedIn](https://www.linkedin.com/in/kevin-van-diesel-chansa/) |
| 🔍 **Reviewing code** | [SijiSiyu](https://github.com/yesterdaygrace/SijiSiyu) · [Inventra](https://github.com/yesterdaygrace/Inventra) (each has a `docs/` folder) |
| ⚡ **Short on time** | [DevScout live demo](https://dev-scout-lac.vercel.app) · [Portfolio](https://yesterdaygrace.github.io/portfolio/) |

</details>

| | |
|---|---|
| 💼 **Now** | Junior Software Engineer at **PT Sahabat Unggul International**: factory web and desktop apps, MySQL/MariaDB, Linux, Docker, Apache |
| 🎓 **Education** | Informatics Engineering, Universitas Kristen Satya Wacana |
| 🛠️ **Experience** | 2+ years shipping and maintaining business software |
| 🧭 **Next** | Go and TypeScript beyond my Laravel base, then DevOps, security and AI automation |

---

## 🚀 Projects

<table>
<tr>
<td width="50%" valign="top">

**🧵 [SijiSiyu](https://github.com/yesterdaygrace/SijiSiyu)**<br/>
Local-first Threads library with a Chromium extension that scans and syncs your saved posts.<br/><br/>
<img alt="SijiSiyu stack" src="https://skillicons.dev/icons?i=nuxt,vue,ts,sqlite,tailwind,nodejs&theme=dark" /><br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/SijiSiyu?style=flat-square&color=3f3f46&labelColor=18181b" />

</td>
<td width="50%" valign="top">

**🔎 [DevScout](https://github.com/yesterdaygrace/DevScout)** · [live](https://dev-scout-lac.vercel.app)<br/>
Search, compare and score GitHub developers. Collections, notes, per-user RLS.<br/><br/>
<img alt="DevScout stack" src="https://skillicons.dev/icons?i=vue,ts,supabase,postgres,tailwind,vite,vercel&theme=dark" /><br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DevScout?style=flat-square&color=3f3f46&labelColor=18181b" />

</td>
</tr>
<tr>
<td width="50%" valign="top">

**📦 [Inventra](https://github.com/yesterdaygrace/Inventra)**<br/>
Multi-warehouse inventory: append-only ledger, reservations, idempotent stock operations.<br/><br/>
<img alt="Inventra stack" src="https://skillicons.dev/icons?i=go,postgres,react,ts,tailwind,docker,githubactions&theme=dark" /><br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/Inventra?style=flat-square&color=3f3f46&labelColor=18181b" />

</td>
<td width="50%" valign="top">

**🏦 [DAPENSE](https://github.com/yesterdaygrace/DAPENSE)**<br/>
Pension fund accounting: double-entry journals, period close, role-gated reports.<br/><br/>
<img alt="DAPENSE stack" src="https://skillicons.dev/icons?i=laravel,php,mysql,redis,docker,nginx,ubuntu&theme=dark" /><br/>
<img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DAPENSE?style=flat-square&color=3f3f46&labelColor=18181b" />

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
    style X fill:#3f3f46,color:#fff,stroke:none
    style U fill:#3f3f46,color:#fff,stroke:none
```

- 📥 Saving a post on `threads.net` streams it to the local app and shows a toast
- 🔄 `MutationObserver` captures new bookmarks as the `/saved` feed scrolls; a bulk scan walks the full history
- 📴 Offline queue in `chrome.storage.local` flushes when the backend returns
- 🧩 Why an extension: Meta's Threads API has no Saved or Unsave endpoint, so the project reads the logged-in site instead
- 🔐 Tokens are AES-256-GCM encrypted at rest; sessions store only a SHA-256 hash; OAuth state guards against login CSRF

</details>

<details>
<summary><b>🔎 DevScout: how it's built</b></summary>

<br/>

```mermaid
flowchart LR
    A([Vue 3]) --> B[Hono proxy] --> G[GitHub API]
    A --> C[(Supabase + RLS)]
    style A fill:#3f3f46,color:#fff,stroke:none
```

- 🔑 The GitHub token stays server-side behind a Zod-validated Hono proxy with rate limiting and a request queue
- 🧮 6-factor candidate score (0 to 100) and a language breakdown over up to 20 non-fork repos
- 🛡️ Row Level Security on all 7 tables; Vitest unit tests and Playwright E2E

</details>

<details>
<summary><b>📦 Inventra: how it protects stock</b></summary>

<br/>

```mermaid
flowchart LR
    A([React]) --> B[Gin] --> C[Service] --> D[GORM] --> E[(PostgreSQL)]
    style A fill:#3f3f46,color:#fff,stroke:none
```

- 📒 Append-only ledger: corrections add a row, balances are derived on read
- 🔒 `SELECT ... FOR UPDATE` row locks inside transactions; idempotency keys return `409` on a changed body
- 🪪 JWT with refresh rotation and reuse detection, DB-backed RBAC, failure-safe audit trail
- ✅ 17 tables, 13 migrations, CI coverage gate at 80% per package

</details>

<details>
<summary><b>🏦 DAPENSE: how it keeps books</b></summary>

<br/>

```mermaid
flowchart LR
    H[header_coas] --> C[coas] --> J[jurnalings] --> V[(views)]
    P[periodes] --> J
    style J fill:#3f3f46,color:#fff,stroke:none
```

- 🗄️ 3NF schema, 8 core tables, `NUMERIC(15,2)` money columns and a balanced-journal guard
- 📅 Open, closed, then trial-balance snapshot per period
- 🛡️ 4 roles enforced by Policies and Gates; encrypted backups with 30-day retention

</details>

**More repositories**

| Repo | What it is | Stack |
|---|---|---|
| 🎬 [CinemaSystem](https://github.com/yesterdaygrace/CinemaSystem) | Cinema ticketing backend assessment. PostgreSQL `btree_gist` blocks overlapping schedules. Its Redis seat lock is a design proposal only. | <img alt="stack" src="https://skillicons.dev/icons?i=go,postgres,docker&theme=dark" /> |
| 📝 [Nodex](https://github.com/yesterdaygrace/Nodex) | CRUD API with pagination and a test suite that locks the API contract | <img alt="stack" src="https://skillicons.dev/icons?i=go,postgres,vue,vite&theme=dark" /> |
| 🌐 [portfolio](https://github.com/yesterdaygrace/portfolio) | Case-study portfolio, CI audit, typecheck and build, deployed to GitHub Pages | <img alt="stack" src="https://skillicons.dev/icons?i=react,ts,vite,githubactions&theme=dark" /> |

---

## 💼 Experience

| When | Role |
|---|---|
| `Oct 2026 → now` | 🏭 **Junior Software Engineer**, PT Sahabat Unggul International (contract) |
| `Aug 2024 → Dec 2025` | 🏦 **Full Stack Web Developer (intern)**, Dana Pensiun Sekolah Kristen Salatiga |
| `Aug → Dec 2024` | 🎓 **Teaching Assistant**, Web Developer course, UKSW |

<details open>
<summary><b>🏭 Sahabat Unggul: factory systems</b></summary>

<br/>

- 🐞 Fix bugs and add features to SUI APPS V2.0 (web and desktop) from factory operations requirements
- 🗄️ Run MySQL/MariaDB: backups, query tuning, monitoring
- 🐧 Support Linux servers: Docker containers, Apache and MySQL services, log monitoring
- 🤝 Gather requirements with HR, Production, Finance and Warehouse; document code changes and procedures

<img alt="Sahabat Unggul stack" src="https://skillicons.dev/icons?i=php,js,mysql,mariadb,docker,apache,linux&theme=dark" />

</details>

<details>
<summary><b>🏦 Dana Pensiun: legacy VDOS to Laravel</b></summary>

<br/>

- 🔁 Migrated a legacy VDOS-based financial system to Laravel
- 📚 Built General Ledger, Journal Processing, Cash & Bank, Financial Reporting and Balance Reconciliation modules
- 🧾 Turned accounting workflows into features with finance stakeholders, in 1 to 2 week sprints
- ✅ Tested at unit, integration and UAT level before releases
- 📈 Self-reported results: about 30 to 40% better operational efficiency and 25 to 30% fewer manual input errors

<img alt="Dana Pensiun stack" src="https://skillicons.dev/icons?i=laravel,php,js,mysql,nginx,ubuntu,git&theme=dark" />

</details>

<details>
<summary><b>🎓 Teaching assistant</b></summary>

<br/>

4 classes, 100+ students, 400+ assignments reviewed. Taught HTML, CSS, PHP and MySQL, and standardized grading across classes.

<img alt="Teaching stack" src="https://skillicons.dev/icons?i=html,css,php,mysql&theme=dark" />

</details>

---

## 🧰 Stack

<div align="center">

<table>
<tr><td align="right"><b>Languages</b></td><td><img alt="Languages" src="https://skillicons.dev/icons?i=php,go,ts,js,html,css,bash&theme=dark" /></td></tr>
<tr><td align="right"><b>Frameworks</b></td><td><img alt="Frameworks" src="https://skillicons.dev/icons?i=laravel,react,vue,nuxt,nodejs,tailwind,vite&theme=dark" /></td></tr>
<tr><td align="right"><b>Data</b></td><td><img alt="Data" src="https://skillicons.dev/icons?i=postgres,mysql,mariadb,sqlite,supabase,redis&theme=dark" /></td></tr>
<tr><td align="right"><b>Infra</b></td><td><img alt="Infra" src="https://skillicons.dev/icons?i=linux,fedora,ubuntu,docker,nginx,apache,vercel&theme=dark" /></td></tr>
<tr><td align="right"><b>CI/CD</b></td><td><img alt="CI/CD" src="https://skillicons.dev/icons?i=git,github,githubactions&theme=dark" /> <img alt="CI/CD" src="https://img.shields.io/badge/CI%2FCD-18181b?style=for-the-badge&logo=githubactions&logoColor=white" /></td></tr>
<tr><td align="right"><b>Quality &amp; security</b></td><td><img alt="Semgrep" src="https://img.shields.io/badge/Semgrep-18181b?style=for-the-badge&logo=semgrep&logoColor=white" /> <img alt="SonarQube" src="https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqubeserver&logoColor=white" /> <img alt="OWASP" src="https://img.shields.io/badge/OWASP-000?style=for-the-badge&logo=owasp&logoColor=white" /></td></tr>
<tr><td align="right"><b>Tools</b></td><td><img alt="Tools" src="https://skillicons.dev/icons?i=vscode,postman,github&theme=dark" /> <img alt="Jira" src="https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=jira&logoColor=white" /> <img alt="Chrome DevTools" src="https://img.shields.io/badge/Chrome_DevTools-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white" /></td></tr>
</table>

</div>

<details>
<summary><b>🔎 Full breakdown</b></summary>

<br/>

| Layer | Tools |
|---|---|
| ⚙️ **Backend** | Laravel, Livewire, Go (Gin, GORM), Nuxt/Nitro, Hono, Zod, REST, OpenAPI, JWT, OAuth 2.0, SSE |
| 🎨 **Frontend** | React 19, Vue 3, Nuxt, Pinia, TanStack Query, Tailwind, Vite, TypeScript, Chart.js |
| 🗄️ **Data** | PostgreSQL, MySQL/MariaDB, SQLite (WAL), Redis, Supabase, ERD design, indexing, query tuning |
| 🐳 **Infra** | Linux, Docker, Docker Compose, Nginx, Apache, systemd, Vercel, Kubernetes (learning) |
| 🔁 **CI/CD** | GitHub Actions (build, test, lint, audit, deploy), Vercel, GitHub Pages |
| 🛡️ **Security & quality** | OWASP, Semgrep, SonarQube, govulncheck, AES-256-GCM, JWT rotation, bcrypt, RBAC, RLS, rate limiting |
| 🧪 **Testing & debugging** | testify, uber mock, Vitest, PHPUnit, Playwright, Postman, Chrome DevTools |
| 🧰 **Workflow** | Jira, Git, Docker-based local environments |
| 🌐 **Browser** | Chromium extensions, content scripts, MutationObserver |
| 🤖 **AI tools** | Claude, Cursor, Codex, ChatGPT, OpenCode |

</details>

---

## 📊 Stats

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&theme=dark&bg_color=0d1117&title_color=ffffff&icon_color=a1a1aa" />
  <img width="49%" alt="stats" src="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&bg_color=ffffff&title_color=18181b&text_color=3f3f46&icon_color=71717a" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&theme=dark&bg_color=0d1117&title_color=ffffff" />
  <img width="38%" alt="top languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&bg_color=ffffff&title_color=18181b&text_color=3f3f46" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&theme=dark&background=0d1117&ring=ffffff&fire=a1a1aa&currStreakLabel=ffffff" />
  <img width="60%" alt="streak" src="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&background=ffffff&ring=18181b&fire=71717a&currStreakLabel=18181b" />
</picture>

</div>

<details>
<summary><b>📈 Contribution graph</b></summary>

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=0d1117&color=ffffff&line=a1a1aa&point=ffffff&area=true&area_color=3f3f46&hide_border=true" />
  <img width="100%" alt="activity graph" src="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=ffffff&color=18181b&line=71717a&point=18181b&area=true&area_color=d4d4d8&hide_border=true" />
</picture>

</details>

---

## 🧪 Learning next

<div align="center">

<img alt="Learning" src="https://skillicons.dev/icons?i=kubernetes,terraform,prometheus,grafana,rabbitmq&theme=dark" /><br/><br/>
<img alt="Trivy" src="https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aqua&logoColor=white" />
<img alt="OWASP" src="https://img.shields.io/badge/OWASP-000?style=flat-square&logo=owasp&logoColor=white" />
<img alt="MCP" src="https://img.shields.io/badge/MCP-3f3f46?style=flat-square" />
<img alt="RAG" src="https://img.shields.io/badge/RAG-3f3f46?style=flat-square" />
<img alt="Distributed systems" src="https://img.shields.io/badge/Distributed_systems-18181b?style=flat-square" />

</div>

```mermaid
flowchart LR
    A([Full stack]) --> B[Go + TypeScript] --> C[DevOps + Security] --> D[Cloud] --> E[AI automation] --> F([Distributed systems])
    style A fill:#3f3f46,color:#fff,stroke:none
    style F fill:#18181b,color:#fff,stroke:none
```

<div align="center">

<img width="100%" alt="yesterdaygrace, animated Y2K footer" src="assets/y2k-dots-footer.svg" />

</div>
