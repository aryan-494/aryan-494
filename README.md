  # Aryan Mishra
  **Backend engineer. Distributed systems. Data synchronization. Offline-first architecture.**

  ---

  I build backend systems designed to stay correct under pressure — unreliable networks, concurrent writes, and partial failures.

  My focus: **data consistency and real-time collaboration**. Specifically, how multiple clients stay in sync without sacrificing correctness, and how systems recover when things go wrong.

  I think about failure modes before features.

  ---

  ## Currently Exploring

  - Distributed systems: **CRDTs, vector clocks, causal consistency**
  - Database internals: **WAL, MVCC, storage engine design**
  - Systems programming with **Rust**

  ---

  ## Projects

  ### [NexusSync](https://github.com/aryan-494/NexusSync) · [Live](https://nexussync-client.vercel.app/)
  *Offline-first collaborative task system designed for unreliable networks.*

  The problem: keep multiple clients consistent when they disconnect mid-session, retry writes, and reconnect in arbitrary order.

  - **Operation log (opLog):** every mutation is a discrete, idempotent unit with a unique ID. The server deduplicates by ID on every push — retries are always safe, double-writes are structurally impossible.
  - **Push/pull replication:** WebSocket events (from MongoDB Change Streams) act as invalidation signals only. Clients pull diffs on notification — separating notification from data delivery eliminates write-then-read race conditions.
  - **Sync hardening:** exponential backoff on failed pushes; debounced pull sync coalesces Change Stream bursts client-side — no request storms after reconnect.
  - **Tenant isolation enforced at the transport layer:** per-workspace Socket.IO rooms backed by Redis. Cross-tenant event leakage is architecturally prevented.

  `Node.js · Express · MongoDB · TypeScript · React · Socket.IO · Redis · IndexedDB · Docker`

  ---

  ### [StudyNotion](https://github.com/aryan-494/Edtech-platform)
  *Multi-role EdTech platform with course management and payment flows.*

  - **Authorization at the route layer:** access decisions are made before business logic runs. Privilege escalation is structurally prevented, not just guarded.
  - **Index-first API design:** paginated REST APIs built around compound MongoDB indexes on nested documents. N+1 patterns eliminated by design.
  - **Atomic payment enrollment:** Razorpay webhook signature verification + transactional writes. Payment and access grant commit together or both roll back — no partial-state failures.

  `Node.js · Express · MongoDB · React · Redux Toolkit · Razorpay · Cloudinary`

  ---

  ### [TrueDetective](https://github.com/aryan-494)
  *AI-backed fact verification pipeline with typed, schema-safe output.*

  - **Zod validation at every IO boundary** — input, API response, and output. Model deviations are caught before they surface as untyped runtime errors.
  - **Contract-first pipeline:** each stage carries a defined input/output schema enforced at compile time. Schema violations in model output were the primary failure mode during development — and are now fully hardened.

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

  - Model failure modes and edge cases first — then write the happy path
  - Idempotency and retry safety are API contract decisions, not implementation patches
  - Auth and access control belong at the structural layer, not scattered through business logic
  - Notification, data delivery, and state are separate concerns — conflating them creates race conditions
  - Explicit typed contracts at IO boundaries over defensive runtime checks

  ---

  ## GitHub Stats

  <p align="left">
    <img src="https://github-readme-stats.vercel.app/api?username=aryan-494&show_icons=true&theme=default&hide_border=true&include_all_commits=true&count_private=true&hide=stars&rank_icon=github" height="150"/>
    &nbsp;&nbsp;
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=aryan-494&layout=compact&theme=default&hide_border=true&langs_count=6" height="150"/>
  </p>

  ---

  [aryanmishra49712@gmail.com](mailto:aryanmishra49712@gmail.com) &nbsp;·&nbsp; [LinkedIn](https://linkedin.com/in/aryanmishra494) &nbsp;·&nbsp; [GitHub](https://github.com/aryan-494)
