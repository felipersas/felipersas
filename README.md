<p align="center">
  <img src="./mountain-clouds-header.webp" alt="Mountains above the clouds" width="100%" />
</p>

<h1 align="center">Hi, I'm Felipe Marques 👋</h1>

<h3 align="center">Full-Stack Developer · TypeScript · Go · Python · Distributed Systems · AI</h3>

<p align="center">
  <a href="https://felipersas-dev.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
  <a href="https://www.linkedin.com/in/felipe-marques-a748b9299/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge" alt="LinkedIn" /></a>
  <a href="https://github.com/felipersas?tab=followers"><img src="https://img.shields.io/github/followers/felipersas?style=for-the-badge&logo=github&label=Followers&color=181717" alt="GitHub followers" /></a>
</p>

---

## 🧭 About me

- 🔭 Mid-level Full-Stack Developer at **Keeper**, a fintech for graduation class fundraising and financial management.
- 🧱 Most of my side projects are backend: services that talk over RabbitMQ, sagas, ledgers, and the tracing and metrics needed to debug them.
- 🤖 I trained a small GPT from scratch in PyTorch to learn how language models work, and I build LLM agents with Mastra and the Vercel AI SDK.
- 🛠️ Lately I've been writing CLIs and TUIs in Go and Rust.
- 🌎 More at **[felipersas-dev.vercel.app](https://felipersas-dev.vercel.app/)**.

## 💼 Experience

**Mid-level Full-Stack Developer · Keeper** · Jun 2026 – present · São Paulo, Brazil (hybrid)

At Keeper, the money a graduation class raises has to reconcile from the first payment to the last payout. Most of this work shipped into code already running in production, with several classes paying at the same time.

- Built batch ticket issuing for the support team: they pick the event and the quantity per person, and the system issues the rest. Tickets used to be issued by hand through the API; about 700 a month now go through this screen.
- Reused AWS and HTTP clients, tuned the Granian server and the Docker image, and added lazy loading and concurrency where they paid off. Average CPU and memory usage of the ECS containers dropped by 25%.
- The React Native app stored the user's email and password in AsyncStorage. It now keeps only the token, and I tightened route protection.
- Added Google and Apple sign-in to the app on my own initiative.
- Wrote project skills and rules for Claude Code and Codex that draft PR descriptions and run a first review pass, so tasks come out in the same format with less rework.

<sub>`Angular` `TypeScript` `Python` `Flask` `PostgreSQL` `React Native` `AWS`</sub>

<sub>Previously: Full-Stack Developer at MindGroup Consulting e Marketing.</sub>

## 🧰 Tech stack

<table>
  <tr>
    <td><b>Languages</b></td>
    <td><img src="https://skillicons.dev/icons?i=ts,js,go,rust,py,java,bash" alt="TypeScript, JavaScript, Go, Rust, Python, Java, Bash" /></td>
  </tr>
  <tr>
    <td><b>Backend</b></td>
    <td><img src="https://skillicons.dev/icons?i=nodejs,nestjs,bun,flask,fastapi,spring" alt="Node.js, NestJS, Bun, Flask, FastAPI, Spring" /></td>
  </tr>
  <tr>
    <td><b>Frontend & Mobile</b></td>
    <td><img src="https://skillicons.dev/icons?i=react,nextjs,angular,vite,tailwind" alt="React, Next.js, Angular, Vite, Tailwind CSS" /></td>
  </tr>
  <tr>
    <td><b>Data & Messaging</b></td>
    <td><img src="https://skillicons.dev/icons?i=postgres,mysql,redis,dynamodb,elasticsearch,rabbitmq,prisma" alt="PostgreSQL, MySQL, Redis, DynamoDB, Elasticsearch, RabbitMQ, Prisma" /></td>
  </tr>
  <tr>
    <td><b>Cloud & DevOps</b></td>
    <td><img src="https://skillicons.dev/icons?i=aws,docker,githubactions,vercel,nginx,linux,grafana,prometheus" alt="AWS, Docker, GitHub Actions, Vercel, Nginx, Linux, Grafana, Prometheus" /></td>
  </tr>
  <tr>
    <td><b>AI & ML</b></td>
    <td><img src="https://skillicons.dev/icons?i=pytorch,sklearn" alt="PyTorch, scikit-learn" /></td>
  </tr>
  <tr>
    <td><b>Testing & Tools</b></td>
    <td><img src="https://skillicons.dev/icons?i=jest,vitest,git,github,neovim" alt="Jest, Vitest, Git, GitHub, Neovim" /></td>
  </tr>
</table>

<details>
<summary><b>More libraries & tools</b></summary>

<br/>

- **Architecture:** DDD · Clean Architecture · microservices · event-driven architecture · sagas · CQRS · outbox pattern
- **Languages:** SQL
- **Backend:** tRPC · Socket.IO · TypeORM · Drizzle · Zod · BullMQ · REST / OpenAPI · JWT
- **Frontend & Mobile:** React Native · Expo · TanStack Query · shadcn/ui · Zustand · React Hook Form
- **Data & Messaging:** Amazon S3 · pgvector
- **Cloud & DevOps:** ECS · Lambda · API Gateway · SNS · Cognito · Kong · Keycloak · Traefik · OpenTelemetry · Jaeger · Turborepo
- **AI & ML:** OpenAI · Gemini · Vercel AI SDK · LLM agents · RAG · pandas · NumPy · Claude Code · Codex
- **Testing & Tools:** Playwright · Testcontainers · Testing Library · pytest · JUnit

</details>

## 🚀 Featured projects

<table>
<tr>
<td>

### 🎰 [Crash Game](https://github.com/felipersas/crash-game)

Real-time multiplayer crash game. A multiplier climbs from 1.00× and crashes at a point fixed before the round; players who cash out in time win `bet × multiplier`.

- The Games and Wallets services coordinate each bet through a saga over RabbitMQ, with a transactional outbox and an idempotent inbox, so a redelivered message never debits or pays twice.
- Balances live in a double-entry ledger (integer cents, SHA-256 chained entries), and crash points are provably fair: each round's hash is committed before it starts.
- The multiplier is pushed every 100 ms over WebSockets. Kong and Keycloak (OIDC + PKCE) sit at the edge, and CI runs 700+ unit tests plus Testcontainers E2E tests.

`Bun` `NestJS` `Next.js` `PostgreSQL` `Redis` `RabbitMQ` `Kong` `Keycloak` `Prometheus` `Grafana`

</td>
</tr>
</table>

<table>
<tr>
<td width="50%" valign="top">

### 💸 [PayFlow](https://github.com/felipersas/payflow)

Transfers between accounts across three Go services that only talk through RabbitMQ. A saga handles debit, credit and compensation; traces go to Jaeger and metrics to Prometheus.

`Go` `PostgreSQL` `RabbitMQ` `OpenTelemetry` `Grafana`

</td>
<td width="50%" valign="top">

### 🧠 [Mini-GPT](https://github.com/felipersas/mini-gpt)

Decoder-only GPT written from scratch in PyTorch, without `nn.Transformer`, trained on Machado de Assis novels and Portuguese Wikipedia. Each component has its own doc with the math.

`Python` `PyTorch` `CUDA`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎬 [Democraft](https://github.com/felipersas/democraft)

Product demos as code: write the demo in TypeScript, Playwright runs it in a real browser and Remotion renders the video. Coding agents can write and maintain the same demos through the CLI's JSON output.

`TypeScript` `Playwright` `Remotion` `Next.js`

</td>
<td width="50%" valign="top">

### ⚡ [Fasty-ORM](https://github.com/felipersas/fasty-orm)

TypeScript ORM with a Rust core: Drizzle-style query builder, per-query cache with table-level invalidation, and a migration CLI.

`Rust` `TypeScript` `napi-rs` `SQLx`

</td>
</tr>
</table>

## 🐍 Contributions

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/felipersas/felipersas/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/felipersas/felipersas/output/github-contribution-grid-snake.svg" />
    <img alt="Snake eating my GitHub contribution grid" src="https://raw.githubusercontent.com/felipersas/felipersas/output/github-contribution-grid-snake.svg" />
  </picture>
</p>

---

<p align="center">
  <i>🥑 Eat · 💻 Code · ♻️ Repeat</i><br/>
  Feel free to reach out 💬
</p>
