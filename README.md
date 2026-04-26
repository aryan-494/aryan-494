# Aryan Mishra
**Backend engineer. Real-time systems. Data consistency. Offline-first architecture.**

---

I build backend systems that stay reliable under real-world conditions — unreliable networks, concurrent writes, and partial failures.

My focus is on **data consistency and real-time collaboration**, designing systems that remain correct even when clients disconnect, retry, and reconnect unpredictably.

---

## Currently Exploring

- Distributed systems patterns for real-time applications  
- Database performance and indexing strategies  
- System design for scalable backend services  

---

## Projects

### [NexusSync](https://github.com/aryan-494/NexusSync) · [Live](https://nexussync-client.vercel.app/)
*Offline-first collaborative system enabling real-time multi-user updates even under unstable network conditions.*

The problem: keep multiple clients consistent when they disconnect mid-session, retry writes, and reconnect in arbitrary order.

- **Operation log (opLog):** every mutation is a discrete, idempotent unit with a unique ID. The server deduplicates by ID on every push — retries are always safe, double-writes are structurally impossible.
- **Push/pull replication:** WebSocket events (from MongoDB Change Streams) act as invalidation signals only. Clients pull diffs on notification — separating notification from data delivery eliminates write-then-read race conditions.
- **Sync hardening:** exponential backoff on failed pushes; debounced pull sync coalesces Change Stream bursts client-side — no request storms after reconnect.
- **Tenant isolation enforced at the transport layer:** per-workspace Socket.IO rooms backed by Redis. Cross-tenant event leakage is architecturally prevented.

`Node.js · Express · MongoDB · TypeScript · React · Socket.IO · Redis · IndexedDB · Docker`

---

### [StudyNotion](https://github.com/aryan-494/Edtech-platform)
*Multi-role EdTech platform with course management and payment flows.*

- **Authorization at the route layer:** access decisions are made before business logic runs, preventing privilege escalation by design.
- **Index-first API design:** paginated REST APIs built around compound MongoDB indexes on nested documents, avoiding N+1 query patterns.
- **Atomic payment enrollment:** Razorpay webhook verification with transactional writes ensures payment and access updates succeed or fail together.
- Built responsive frontend dashboards and course pages to support smooth user experience across roles.

`Node.js · Express · MongoDB · React · Redux Toolkit · Razorpay · Cloudinary`

---

### [TrueDetective](https://github.com/aryan-494)
*AI-backed fact verification pipeline with typed, schema-safe output.*

- **Zod validation at every IO boundary** — input, API response, and output, preventing runtime inconsistencies.
- **Contract-first pipeline:** each stage enforces strict input/output schemas, ensuring reliability even with variable AI responses.

`Node.js · Express · TypeScript · React · Gemini API`

---

## Technical Skills

| | |
|---|---|
| **Backend** | Node.js, Express, REST APIs, Socket.IO, JWT, Zod |
| **Frontend** | React, Next.js, TypeScript, Zustand, Tailwind CSS |
| **Databases** | MongoDB (Change Streams, Indexes, Transactions), Redis, PostgreSQL |
| **Systems** | Offline-First, Idempotent APIs, Eventual Consistency, Multi-Tenant SaaS |
| **Languages** | TypeScript, JavaScript, C++, Python |
| **DevOps** | Docker, Git, GitHub Actions, Vercel, Railway, MongoDB Atlas |

---

## Engineering Approach

- Design systems with failure scenarios in mind (network issues, retries, concurrency)
- Build APIs that are safe under retries using idempotent operations
- Keep authentication and access control structured and consistent
- Separate notification, data delivery, and state to avoid race conditions
- Prefer clear architecture and typed contracts over ad-hoc fixes

---

## GitHub Stats

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=aryan-494&show_icons=true&theme=default&hide_border=true&include_all_commits=true&count_private=true&hide=stars&rank_icon=github" height="150"/>
  &nbsp;&nbsp;
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=aryan-494&layout=compact&theme=default&hide_border=true&langs_count=6" height="150"/>
</p>

---

[aryanmishra49712@gmail.com](mailto:aryanmishra49712@gmail.com) &nbsp;·&nbsp; [LinkedIn](https://linkedin.com/in/aryanmishra494) &nbsp;·&nbsp; [GitHub](https://github.com/aryan-494) &nbsp;·&nbsp; [X](https://x.com/Mishra_aryan_49)
