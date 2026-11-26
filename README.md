<img src="assets/ui/header.svg" width="100%" alt="Kevin Chansa. Backend, databases, DevOps. Animated halftone banner in a desktop window.">

<p align="center">
  <a href="https://www.linkedin.com/in/kevin-van-diesel-chansa/">LinkedIn</a> ·
  <a href="https://yesterdaygrace.github.io/portfolio/">Portfolio</a> ·
  <a href="https://dev-scout-lac.vercel.app">DevScout demo</a> ·
  <a href="https://github.com/yesterdaygrace?tab=repositories">All repositories</a>
</p>

<p align="center"><b><a href="#projects">Projects</a> · <a href="#experience">Experience</a> · <a href="#stack">Stack</a> · <a href="#stats">Stats</a> · <a href="#learning">Learning</a></b></p>

<table>
  <tr>
    <td width="40%" valign="top">
      <img src="assets/ui/profile-card.svg" width="100%" alt="Kevin Van Diesel Chansa, @yesterdaygrace. Junior Software Engineer. Focus: backend and databases. Now: Sahabat Unggul International. Education: Informatics, UKSW.">
    </td>
    <td width="60%" valign="top">
      <h3>Hey, I'm Kevin.</h3>
      <p>Junior software engineer working across backend, frontend, databases and DevOps. Informatics Engineering graduate (UKSW) with 2+ years shipping and maintaining business software.</p>
      <p>At <b>PT Sahabat Unggul International</b> I maintain a factory's web and desktop apps and run its MySQL/MariaDB, Docker and Apache stack.</p>
      <p>Outside work I build Go and TypeScript projects to move beyond my Laravel base.</p>
      <table>
        <tr><th>If you are</th><th>Start here</th></tr>
        <tr><td>Hiring</td><td><a href="#experience">Experience</a> · <a href="https://www.linkedin.com/in/kevin-van-diesel-chansa/">LinkedIn</a></td></tr>
        <tr><td>Reviewing code</td><td><a href="https://github.com/yesterdaygrace/SijiSiyu">SijiSiyu</a> · <a href="https://github.com/yesterdaygrace/Inventra">Inventra</a> (each has a <code>docs/</code> folder)</td></tr>
        <tr><td>Short on time</td><td><a href="https://dev-scout-lac.vercel.app">DevScout demo</a> · <a href="https://yesterdaygrace.github.io/portfolio/">Portfolio</a></td></tr>
      </table>
    </td>
  </tr>
</table>

<img src="assets/ui/divider.svg" width="100%" alt="">

<a name="projects"></a>
<img src="assets/ui/sec-projects.svg" width="100%" alt="Projects. Selected work, 4 repositories.">

<p align="center">
  <a href="https://github.com/yesterdaygrace/SijiSiyu"><img src="assets/ui/f-sijisiyu.svg" width="210" alt="SijiSiyu: Threads saved-posts library. Open the repository."></a>
  <a href="https://github.com/yesterdaygrace/DevScout"><img src="assets/ui/f-devscout.svg" width="210" alt="DevScout: developer sourcing and scoring. Open the repository."></a>
  <a href="https://github.com/yesterdaygrace/Inventra"><img src="assets/ui/f-inventra.svg" width="210" alt="Inventra: multi-warehouse inventory. Open the repository."></a>
  <a href="https://github.com/yesterdaygrace/DAPENSE"><img src="assets/ui/f-dapense.svg" width="210" alt="DAPENSE: pension fund accounting. Open the repository."></a>
</p>

<details>
<summary><b>🧵 SijiSiyu: local-first Threads library with a saved-posts scanner</b></summary>

<br/>

`Nuxt` `Vue 3` `TypeScript` `SQLite (WAL)` `Tailwind` `Chromium extension` · [repo](https://github.com/yesterdaygrace/SijiSiyu) · <img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/SijiSiyu?style=flat-square&color=3f3f46&labelColor=18181b" />

```mermaid
flowchart LR
    X([Extension]) -->|sync| N[Nitro API] --> S[(SQLite WAL)]
    N <-->|OAuth| M[Threads API]
    N -- SSE --> U([Nuxt UI])
    style X fill:#3f3f46,color:#fff,stroke:none
    style U fill:#3f3f46,color:#fff,stroke:none
```

- Saving a post on `threads.net` streams it to the local app and shows a toast
- `MutationObserver` captures new bookmarks as the `/saved` feed scrolls; a bulk scan walks the full history
- Offline queue in `chrome.storage.local` flushes when the backend returns
- Why an extension: Meta's Threads API has no Saved or Unsave endpoint, so the project reads the logged-in site instead
- Tokens are AES-256-GCM encrypted at rest; sessions store only a SHA-256 hash; OAuth state guards against login CSRF

</details>

<details>
<summary><b>🔎 DevScout: search, compare and score GitHub developers</b></summary>

<br/>

`Vue 3` `TypeScript` `Hono` `Supabase` `Tailwind` `Vite` `Vercel` · [repo](https://github.com/yesterdaygrace/DevScout) · [live demo](https://dev-scout-lac.vercel.app) · <img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DevScout?style=flat-square&color=3f3f46&labelColor=18181b" />

```mermaid
flowchart LR
    A([Vue 3]) --> B[Hono proxy] --> G[GitHub API]
    A --> C[(Supabase + RLS)]
    style A fill:#3f3f46,color:#fff,stroke:none
```

- The GitHub token stays server-side behind a Zod-validated Hono proxy with rate limiting and a request queue
- 6-factor candidate score (0 to 100) and a language breakdown over up to 20 non-fork repos
- Row Level Security on all 7 tables; Vitest unit tests and Playwright E2E

</details>

<details>
<summary><b>📦 Inventra: multi-warehouse inventory that protects stock</b></summary>

<br/>

`Go` `PostgreSQL 17` `React 19` `TypeScript` `Docker` `GitHub Actions` · [repo](https://github.com/yesterdaygrace/Inventra) · <img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/Inventra?style=flat-square&color=3f3f46&labelColor=18181b" />

```mermaid
flowchart LR
    A([React]) --> B[Gin] --> C[Service] --> D[GORM] --> E[(PostgreSQL)]
    style A fill:#3f3f46,color:#fff,stroke:none
```

- Append-only ledger: corrections add a row, balances are derived on read
- `SELECT ... FOR UPDATE` row locks inside transactions; idempotency keys return `409` on a changed body
- JWT with refresh rotation and reuse detection, DB-backed RBAC, failure-safe audit trail
- 17 tables, 13 migrations, CI coverage gate at 80% per package

</details>

<details>
<summary><b>🏦 DAPENSE: pension fund accounting</b></summary>

<br/>

`Laravel` `PHP 8.3` `MySQL 8.4` `Redis` `Docker` `Nginx` · [repo](https://github.com/yesterdaygrace/DAPENSE) · <img alt="last commit" src="https://img.shields.io/github/last-commit/yesterdaygrace/DAPENSE?style=flat-square&color=3f3f46&labelColor=18181b" />

```mermaid
flowchart LR
    H[header_coas] --> C[coas] --> J[jurnalings] --> V[(views)]
    P[periodes] --> J
    style J fill:#3f3f46,color:#fff,stroke:none
```

- 3NF schema, 8 core tables, `NUMERIC(15,2)` money columns and a balanced-journal guard
- Open, closed, then trial-balance snapshot per period
- 4 roles enforced by Policies and Gates; encrypted backups with 30-day retention

</details>

**More repositories**

| Repo | What it is | Stack |
|---|---|---|
| 🎬 [CinemaSystem](https://github.com/yesterdaygrace/CinemaSystem) | Cinema ticketing backend assessment. PostgreSQL `btree_gist` blocks overlapping schedules. Its Redis seat lock is a design proposal only. | <img src="assets/ui/strip-cinema.svg" height="30" alt="Go, PostgreSQL, Docker"> |
| 📝 [Nodex](https://github.com/yesterdaygrace/Nodex) | CRUD API with pagination and a test suite that locks the API contract | <img src="assets/ui/strip-nodex.svg" height="30" alt="Go, PostgreSQL, Vue, Vite"> |
| 🌐 [portfolio](https://github.com/yesterdaygrace/portfolio) | Case-study portfolio; CI runs audit, typecheck and build, then deploys to GitHub Pages | <img src="assets/ui/strip-portfolio.svg" height="30" alt="React, TypeScript, Vite, GitHub Actions"> |

<img src="assets/ui/divider.svg" width="100%" alt="">

<a name="experience"></a>
<img src="assets/ui/sec-experience.svg" width="100%" alt="Experience. Where I have worked, 2024 to now.">

| When | Role |
|---|---|
| `Oct 2026 → now` | 🏭 **Junior Software Engineer**, PT Sahabat Unggul International (contract) |
| `Aug 2024 → Dec 2025` | 🏦 **Full Stack Web Developer (intern)**, Dana Pensiun Sekolah Kristen Salatiga |
| `Aug → Dec 2024` | 🎓 **Teaching Assistant**, Web Developer course, UKSW |

<details open>
<summary><b>🏭 Sahabat Unggul: factory systems</b></summary>

<br/>

- Fix bugs and add features to SUI APPS V2.0 (web and desktop) from factory operations requirements
- Run MySQL/MariaDB: backups, query tuning, monitoring
- Support Linux servers: Docker containers, Apache and MySQL services, log monitoring
- Gather requirements with HR, Production, Finance and Warehouse; document code changes and procedures

<img src="assets/ui/strip-sahabat.svg" height="40" alt="PHP, JavaScript, MySQL, MariaDB, Docker, Apache, Linux">

</details>

<details>
<summary><b>🏦 Dana Pensiun: legacy VDOS to Laravel</b></summary>

<br/>

- Migrated a legacy VDOS-based financial system to Laravel
- Built General Ledger, Journal Processing, Cash & Bank, Financial Reporting and Balance Reconciliation modules
- Turned accounting workflows into features with finance stakeholders, in 1 to 2 week sprints
- Tested at unit, integration and UAT level before releases
- Self-reported results: about 30 to 40% better operational efficiency and 25 to 30% fewer manual input errors

<img src="assets/ui/strip-dana.svg" height="40" alt="Laravel, PHP, JavaScript, MySQL, Nginx, Ubuntu, Git">

</details>

<details>
<summary><b>🎓 Teaching assistant</b></summary>

<br/>

4 classes, 100+ students, 400+ assignments reviewed. Taught HTML, CSS, PHP and MySQL, and standardized grading across classes.

<img src="assets/ui/strip-ta.svg" height="40" alt="HTML, CSS, PHP, MySQL">

</details>

<img src="assets/ui/divider.svg" width="100%" alt="">

<a name="stack"></a>
<img src="assets/ui/sec-stack.svg" width="100%" alt="Stack. What I build with.">
<img src="assets/ui/stack.svg" width="100%" alt="Tech stack icons. Languages: PHP, Go, TypeScript, JavaScript, HTML, CSS, Bash. Frameworks: Laravel, React, Vue, Nuxt, Node.js, Tailwind, Vite. Data: PostgreSQL, MySQL, MariaDB, SQLite, Supabase, Redis. Infra: Linux, Fedora, Ubuntu, Docker, Nginx, Apache, Vercel. CI/CD: Git, GitHub, GitHub Actions. Quality: Semgrep, SonarQube, OWASP. Tools: Postman, Jira, Chrome DevTools.">

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
| 🧰 **Workflow** | Jira, Git, VS Code, Docker-based local environments |
| 🌐 **Browser** | Chromium extensions, content scripts, MutationObserver |
| 🤖 **AI tools** | Claude, Cursor, Codex, ChatGPT, OpenCode |

</details>

<img src="assets/ui/divider.svg" width="100%" alt="">

<a name="stats"></a>
<img src="assets/ui/sec-stats.svg" width="100%" alt="Stats. Live from GitHub.">

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&theme=dark&bg_color=0d1117&title_color=ffffff&icon_color=86d3a6" />
  <img width="49%" alt="stats" src="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&bg_color=ffffff&title_color=18181b&text_color=3f3f46&icon_color=2f7a52" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&theme=dark&bg_color=0d1117&title_color=ffffff" />
  <img width="38%" alt="top languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&bg_color=ffffff&title_color=18181b&text_color=3f3f46" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&theme=dark&background=0d1117&ring=86d3a6&fire=86d3a6&currStreakLabel=ffffff" />
  <img width="60%" alt="streak" src="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&background=ffffff&ring=2f7a52&fire=2f7a52&currStreakLabel=18181b" />
</picture>

</div>

<details>
<summary><b>📈 Contribution graph</b></summary>

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=0d1117&color=ffffff&line=86d3a6&point=ffffff&area=true&area_color=3f3f46&hide_border=true" />
  <img width="100%" alt="activity graph" src="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=ffffff&color=18181b&line=2f7a52&point=18181b&area=true&area_color=d4d4d8&hide_border=true" />
</picture>

</details>

<img src="assets/ui/divider.svg" width="100%" alt="">

<a name="learning"></a>
<img src="assets/ui/sec-learning.svg" width="100%" alt="Learning next. What I am picking up.">
<img src="assets/ui/learning.svg" width="100%" alt="Currently learning. Infra: Kubernetes, Terraform, Prometheus, Grafana, RabbitMQ. Security: Trivy, OWASP. Topics: MCP, RAG, distributed systems.">

```mermaid
flowchart LR
    A([Full stack]) --> B[Go + TypeScript] --> C[DevOps + Security] --> D[Cloud] --> E[AI automation] --> F([Distributed systems])
    style A fill:#3f3f46,color:#fff,stroke:none
    style F fill:#18181b,color:#fff,stroke:none
```

<p align="center">
  <img src="assets/ui/contact-title.svg" width="520" alt="Find me"><br>
  <a href="https://github.com/yesterdaygrace"><img src="assets/ui/contact-1.svg" width="520" alt="GitHub"></a><br>
  <a href="https://www.linkedin.com/in/kevin-van-diesel-chansa/"><img src="assets/ui/contact-2.svg" width="520" alt="LinkedIn"></a><br>
  <a href="https://yesterdaygrace.github.io/portfolio/"><img src="assets/ui/contact-3.svg" width="520" alt="Portfolio"></a><br>
  <a href="https://dev-scout-lac.vercel.app"><img src="assets/ui/contact-4.svg" width="520" alt="DevScout live demo"></a>
</p>

<img src="assets/ui/footer.svg" width="100%" alt="End of profile. Kevin Van Diesel Chansa, yesterdaygrace.">
