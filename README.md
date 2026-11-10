<div align="center">

<img width="100%" alt="Kevin Chansa — animated forest banner" src="assets/forest-banner.svg" />

<a href="https://github.com/yesterdaygrace">
  <img alt="typing" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=3200&pause=800&color=4ADE80&center=true&vCenter=true&width=720&height=50&lines=Building+things+that+work.;Learning+what+I+don%27t+know+yet.;Laravel+%E2%86%92+Go+%2B+TypeScript;Database+%E2%86%92+API+%E2%86%92+Infra+%E2%86%92+Security;Shipping+backends+that+survive+production." />
</a>

<br/>

<img alt="Profile views" src="https://komarev.com/ghpvc/?username=yesterdaygrace&style=for-the-badge&color=16a34a&label=PROFILE+VIEWS&labelColor=0f172a" />
<img alt="Followers" src="https://img.shields.io/github/followers/yesterdaygrace?style=for-the-badge&logo=github&color=22c55e&labelColor=0f172a" />
<img alt="Repos" src="https://img.shields.io/badge/Experience-1y%205m-22d3ee?style=for-the-badge&labelColor=0f172a" />
<img alt="Status" src="https://img.shields.io/badge/Status-Open%20to%20work-22c55e?style=for-the-badge&labelColor=0f172a" />

<br/><br/>

**[About](#-about) · [Projects](#-featured-projects) · [Experience](#-professional-experience) · [Stack](#-tech-stack) · [Stats](#-github-analytics) · [Roadmap](#-engineering-roadmap) · [Connect](#-connect)**

</div>

---

## 👨‍💻 About

I'm a **Full Stack Web Developer** focused on **backend engineering, databases, enterprise systems, and practical automation**. Graduate in Informatics Engineering from **Universitas Kristen Satya Wacana**, with **1 year 5 months** of hands-on experience shipping and maintaining real software.

My strongest experience is **DAPENSE**, a pension fund information system, where I covered requirements, database design, backend, testing, deployment, and post-launch maintenance.

Now: moving from a Laravel foundation into **TypeScript and Go**, and going deeper into **Docker, CI/CD, Linux, DevSecOps, and AI-assisted development**.

```ts
const kevin = {
  role:      "Full Stack Web Developer",
  strongIn:  ["Laravel", "PostgreSQL", "REST APIs", "RBAC"],
  leveling:  ["Go", "TypeScript", "Docker", "CI/CD", "DevSecOps"],
  exploring: ["RAG", "MCP", "Agentic workflows", "Distributed systems"],
  principle: "Architecture, database, security and deployment must actually matter.",
} as const;
```

<details>
<summary><b>⚡ Quick facts (click to expand)</b></summary>

<br/>

| | |
|---|---|
| 🎓 **Education** | Informatics Engineering — Universitas Kristen Satya Wacana |
| 💼 **Experience** | 1 yr 5 mo (Jul 2024 → Dec 2025) |
| 🐧 **Daily driver** | Fedora / Linux |
| 🧭 **Focus** | Backend · Database · Security · Infra · AI automation |
| 🎯 **Goal** | Understand a system end-to-end: database → backend → API → frontend → infra → security → automation |

</details>

---

## 🚀 Featured Projects

<table>
<tr>
<td width="50%" valign="top">

### 📦 Inventra
**Inventory Management Backend**

Production-style inventory system built to practice serious backend patterns.

<img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" />
<img alt="Gin" src="https://img.shields.io/badge/Gin-008ECF?style=flat-square&logo=gin&logoColor=white" />
<img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img alt="React" src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" />
<img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />

<a href="https://github.com/yesterdaygrace"><b>View Repository →</b></a>

</td>
<td width="50%" valign="top">

### 🔎 DevScout
**Developer & Opportunity Platform**

Full-stack app combining developer profiles, skills, projects, jobs, applications, and GitHub integration.

<img alt="Vue" src="https://img.shields.io/badge/Vue_3-42b883?style=flat-square&logo=vuedotjs&logoColor=white" />
<img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img alt="Hono" src="https://img.shields.io/badge/Hono-E36002?style=flat-square&logo=hono&logoColor=white" />
<img alt="Supabase" src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white" />
<img alt="Pinia" src="https://img.shields.io/badge/Pinia-FFD859?style=flat-square&logo=pinia&logoColor=black" />

<a href="https://github.com/yesterdaygrace"><b>View Repository →</b></a>

</td>
</tr>
</table>

<details>
<summary><b>📦 Inventra — highlights & architecture</b></summary>

<br/>

```mermaid
flowchart LR
    A([HTTP]) --> B[Handler]
    B --> C[Service]
    C --> D[[Repository Interface]]
    D --> E[GORM]
    E --> F[(PostgreSQL)]
    style A fill:#6366f1,color:#fff,stroke:none
    style F fill:#4169E1,color:#fff,stroke:none
```

- 🏬 Multi-warehouse inventory
- 📒 Stock ledger & reservations
- 🔢 Cycle counts & adjustments
- ⚛️ Atomic database transactions + row-level locking
- 🔁 Idempotent operations
- 🔐 JWT auth · RBAC · refresh-token rotation
- 🧾 Audit logging · CSV exports
- 📘 OpenAPI documentation
- 🐳 Docker & CI · ✅ automated testing

</details>

<details>
<summary><b>🔎 DevScout — highlights & architecture</b></summary>

<br/>

```mermaid
flowchart LR
    A([Vue 3 + Pinia]) --> B[Hono API]
    B --> C[Supabase]
    C --> D[(PostgreSQL + RLS)]
    style A fill:#42b883,color:#fff,stroke:none
    style D fill:#3ECF8E,color:#0f172a,stroke:none
```

- 👤 Developer profiles, skills & project management
- 📌 Job and application tracking
- 🐙 GitHub API integration through an API proxy layer
- 🔐 Authentication · PostgreSQL relational design · Row Level Security
- ⚡ API caching · rate limiting
- 📘 OpenAPI · ☁️ Supabase deployment

</details>

---

## 🏢 Professional Experience

### DAPENSE — Pension Fund Information System

**Full Stack Web Developer Intern** · Dana Pensiun Sekolah Kristen Salatiga · `Jul 2024 → Dec 2025`

Built and maintained a web-based pension fund information system that modernized legacy financial workflows.

```mermaid
flowchart LR
    R[Requirements] --> D[ERD & DB design] --> B[Backend & APIs] --> T[UAT & testing] --> P[Deploy] --> M[Maintain]
    style R fill:#6366f1,color:#fff,stroke:none
    style M fill:#a855f7,color:#fff,stroke:none
```

<details>
<summary><b>🧩 Core modules</b></summary>

<br/>

`General Ledger` · `Journal Processing` · `Cash & Bank Transactions` · `Financial Reporting` · `Balance Reconciliation`

</details>

<details>
<summary><b>🛠️ What I worked on</b></summary>

<br/>

- Translated accounting business processes into application requirements
- Designed ERDs and normalized relational database structures
- Developed financial transaction workflows and RESTful APIs
- Implemented authentication, RBAC, validation, and structured workflows
- Improved database relationships and query performance
- Coordinated UAT with accounting stakeholders; shipped feedback and production fixes
- Managed deployment, post-deployment maintenance, and infrastructure troubleshooting
- Maintained backups and data-access controls
- Wrote functional and technical documentation

</details>

<img alt="Laravel" src="https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white" />
<img alt="PHP" src="https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white" />
<img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
<img alt="MySQL" src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" />
<img alt="Nginx" src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white" />
<img alt="Ubuntu" src="https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white" />
<img alt="Git" src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" />

> **Selected project results:** approx. **30–40% improvement in operational efficiency** and **25–30% reduction in manual input errors**, based on project experience and the workflow/validation improvements implemented.

---

## 🧠 Engineering Focus

> I don't want my GitHub to become a museum of framework tutorials. I build systems where architecture, database, security, and deployment actually matter.

```mermaid
mindmap
  root((Engineering))
    Backend
      REST API design
      AuthN / AuthZ
      Business logic
      Service architecture
    Database
      PostgreSQL / MySQL
      Data modeling
      Indexing
      Query optimization
    Infrastructure
      Linux
      Docker
      Nginx
      CI/CD
    Security
      JWT / RBAC
      OWASP
      RLS
      DevSecOps
    AI
      AI-assisted dev
      Automation
      RAG
      MCP / agents
```

---

## 🛠️ Tech Stack

<div align="center">

**Languages & Frameworks**

<img alt="stack" src="https://skillicons.dev/icons?i=php,laravel,go,ts,js,react,vue,tailwind&perline=8" />

**Data**

<img alt="data" src="https://skillicons.dev/icons?i=postgres,mysql,supabase,redis&perline=8" />

**Infra & DevOps**

<img alt="infra" src="https://skillicons.dev/icons?i=linux,fedora,docker,nginx,githubactions,git&perline=8" />

</div>

<details>
<summary><b>🔎 Full breakdown</b></summary>

<br/>

| Layer | Tools |
|---|---|
| **Backend & APIs** | Laravel · PHP · Go (Gin) · Hono · REST · OpenAPI · JWT |
| **Frontend** | React · Vue 3 · Pinia · Tailwind CSS · TypeScript |
| **Databases** | PostgreSQL · MySQL · Supabase · Database Design · Normalization · ERD · Indexing · Query Optimization |
| **Architecture** | Clean Architecture · Layered Architecture · RBAC |
| **Infrastructure** | Linux · Docker · Nginx · CI/CD |
| **Security** | OWASP · JWT · RBAC · RLS · SAST · Trivy |
| **Testing & Debugging** | PHPUnit · Playwright · Postman · Laravel Debugbar · Chrome DevTools |
| **AI-assisted dev** | OpenCode · Cursor · ChatGPT · Codex · Claude |

</details>

---

## 📊 GitHub Analytics

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&theme=tokyonight&bg_color=0d1117&title_color=a78bfa&icon_color=6366f1" />
  <img width="49%" alt="stats" src="https://github-readme-stats.vercel.app/api?username=yesterdaygrace&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&bg_color=f8fafc&title_color=7C3AED&text_color=475569&icon_color=6366F1" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&theme=tokyonight&bg_color=0d1117&title_color=a78bfa" />
  <img width="38%" alt="top langs" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yesterdaygrace&layout=compact&hide_border=true&langs_count=8&bg_color=f8fafc&title_color=7C3AED&text_color=475569" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&theme=tokyonight&background=0d1117&ring=a78bfa&fire=a855f7&currStreakLabel=a78bfa" />
  <img width="60%" alt="streak" src="https://streak-stats.demolab.com?user=yesterdaygrace&hide_border=true&background=f8fafc&ring=6366F1&fire=7C3AED&currStreakLabel=7C3AED" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=0d1117&color=a78bfa&line=6366f1&point=ffffff&area=true&area_color=6366f1&hide_border=true" />
  <img width="100%" alt="activity graph" src="https://github-readme-activity-graph.vercel.app/graph?username=yesterdaygrace&bg_color=f8fafc&color=7C3AED&line=6366F1&point=0f172a&area=true&area_color=6366F1&hide_border=true" />
</picture>

</div>

---

## 🧪 Currently Learning

<table>
<tr>
<td width="25%" valign="top">

**☁️ Infrastructure**

<img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" /><br/>
<img alt="Terraform" src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" /><br/>
<img alt="Prometheus" src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" /><br/>
<img alt="Grafana" src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" /><br/>
<img alt="Redis" src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" /><br/>
<img alt="RabbitMQ" src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" />

</td>
<td width="25%" valign="top">

**🔐 Security**

<img alt="OWASP" src="https://img.shields.io/badge/OWASP-000000?style=flat-square&logo=owasp&logoColor=white" /><br/>
<img alt="SAST" src="https://img.shields.io/badge/SAST-6366f1?style=flat-square" /><br/>
<img alt="Trivy" src="https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aqua&logoColor=white" /><br/>
<img alt="DevSecOps" src="https://img.shields.io/badge/DevSecOps-a855f7?style=flat-square" /><br/>
<img alt="Secrets" src="https://img.shields.io/badge/Secrets_Mgmt-0f172a?style=flat-square" />

</td>
<td width="25%" valign="top">

**🤖 AI Engineering**

<img alt="RAG" src="https://img.shields.io/badge/RAG-a855f7?style=flat-square" /><br/>
<img alt="MCP" src="https://img.shields.io/badge/MCP-6366f1?style=flat-square" /><br/>
<img alt="Agents" src="https://img.shields.io/badge/Agentic_Workflows-0f172a?style=flat-square" /><br/>
<img alt="Automation" src="https://img.shields.io/badge/AI_Automation-22d3ee?style=flat-square&logoColor=black" />

</td>
<td width="25%" valign="top">

**⚙️ Systems**

<img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" /><br/>
<img alt="Distributed" src="https://img.shields.io/badge/Distributed_Systems-6366f1?style=flat-square" /><br/>
<img alt="Concurrency" src="https://img.shields.io/badge/Concurrency-a855f7?style=flat-square" /><br/>
<img alt="Performance" src="https://img.shields.io/badge/Performance-22c55e?style=flat-square" />

</td>
</tr>
</table>

---

## 🗺️ Engineering Roadmap

```mermaid
flowchart TD
    A([Full Stack Web Development<br/><b>CURRENT</b>]) --> B[Backend Engineering]
    A --> C[Database Engineering]
    B --> D[Go + TypeScript]
    C --> D
    D --> E[DevOps]
    D --> F[Security]
    E --> G[Cloud & DevSecOps]
    F --> G
    G --> H[AI Automation]
    H --> I([Distributed Systems])
    style A fill:#6366f1,color:#fff,stroke:none
    style I fill:#a855f7,color:#fff,stroke:none
```

The goal isn't collecting technologies. It's understanding how a system behaves from **database → backend → API → frontend → infrastructure → security → automation**.

---

## 📫 Connect

<div align="center">

<a href="https://github.com/yesterdaygrace"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-yesterdaygrace-181717?style=for-the-badge&logo=github&logoColor=white" /></a>

<br/><br/>

<img width="100%" alt="footer" src="https://capsule-render.vercel.app/api?type=waving&section=footer&height=120&color=0:14532d,50:16a34a,100:052e16" />

</div>
