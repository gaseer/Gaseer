# Mohammed Gaseer

**AI Engineer · Flutter & Full-Stack Engineer** — Malappuram, Kerala, India

I build AI features that live inside systems real businesses depend on: RAG assistants embedded in production mobile apps, LLM agents that query business data through tool calling, and WhatsApp automation pipelines that have to be correct under concurrency, not just impressive in a demo.

Currently building HRMS & ERP products at **Zeta Software**. Everything below is something I've shipped and can whiteboard.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/gaseer)
[![Portfolio](https://img.shields.io/badge/gaseer.in-000000?style=flat-square&logo=vercel&logoColor=white)](https://gaseer.in)
[![Email](https://img.shields.io/badge/gaseer007@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:gaseer007@gmail.com)

---

## What I actually build

**Production RAG, end to end.** Document ingestion → chunking strategy → embeddings → `pgvector` retrieval with re-ranking → grounded generation with source citations. The interesting problems aren't the API calls; they're chunk boundaries that don't split a policy mid-clause, retrieval that stays useful when the corpus triples, and citations that let a user verify an answer about their own payroll.

**Deterministic automation over LLM routing.** My WhatsApp booking system originally routed conversation state through an LLM. It was unpredictable in exactly the way a booking flow can't afford to be. I rebuilt it as an explicit n8n state machine backed by Supabase RPCs:

- Postgres **advisory locks** inside the RPC, so two people tapping the same slot at the same second can't both get it
- **Idempotent webhook handling** keyed on the provider message ID — WhatsApp retries, and retries must not double-book
- **HMAC SHA-256 signature verification** on every inbound webhook
- The LLM does what it's good at (understanding intent); the database does what it's good at (being correct)

**Mobile that ships.** Flutter with Clean Architecture and Riverpod, offline-first local persistence, and Shorebird OTA so a fix reaches enterprise users the same day instead of after store review.

---

## Selected work

| Project | What it is | Notable engineering |
|---|---|---|
| **Zeta HRMS** <br> [Play Store](https://play.google.com/store/apps/details?id=com.zeta.zeta_ess) · [App Store](https://apps.apple.com/in/app/zeta-hrms/id1439102381) | Enterprise HR platform with an embedded AI assistant for leave, payroll and policy questions | RAG pipeline over HR documents; geo-fenced attendance; biometric auth; multilingual UI; Shorebird OTA |
| **Zeta ERP — agent layer** | Conversational querying of inventory, finance and operations data | Structured tool calling against SQL, schema-aware prompting, report generation |
| **MotorGlow** <br> `[repo link]` | WhatsApp-native booking system for a car-wash business, built solo | Deterministic n8n state machine, Supabase RPCs with advisory locks, idempotent webhooks, HMAC verification |
| **SpotFeed** <br> `[repo link]` | Hyperlocal group chats that auto-expire after 6 hours | PostGIS geofencing for proximity joins, Supabase Realtime, FCM |
| **Manjali Jewellery Orders** | Multi-role order management for customers, manufacturers and admins | Real-time chat with video/image/audio, order lifecycle tracking, Node.js + MySQL + Firestore |

---

## Stack

**AI & LLM** — RAG pipelines · pgvector · embeddings & semantic search · chunking and retrieval strategies · re-ranking · grounded generation with citations · agents & tool calling · prompt engineering · MCP

**Automation** — n8n (deterministic state machines, idempotency, retries) · WhatsApp Business Cloud API · webhooks · queue and cron orchestration

**Backend** — Python · FastAPI · .NET Core · C# · Node.js · Express

**Data** — PostgreSQL · Supabase (RPC, RLS, Realtime, PostGIS) · SQL Server · MySQL · SQLite · Firestore

**Mobile & Frontend** — Flutter · Dart · Clean Architecture · Riverpod · BLoC · go_router · Shorebird OTA · Next.js · React · Angular · TypeScript

**Cloud & Tooling** — AWS (EC2, S3, Lambda, IAM) · Docker · Vercel · Firebase · CI/CD · Git · Claude Code

---

## Things production taught me

- An LLM in the control path of a transactional flow is a liability. Use it for intent, not for state.
- Idempotency isn't optional the moment a third party can retry your webhook.
- Retrieval quality is a data problem long before it's a model problem. Most "the model is hallucinating" bugs were bad chunks.
- Shipping OTA changes how you think about risk — small, frequent, reversible beats big and rehearsed.

---

## Beyond code

I run **iMentor**, a mentorship program for early-career developers in Kerala — a five-season curriculum for BCA/BSc students, currently running two batches. Teaching fundamentals is the fastest way I've found to notice the gaps in my own.

---

## Currently going deeper on

Flutter testing (unit, widget, integration) · offline-first architecture · evaluation harnesses for RAG · Linux and DevOps fundamentals

---

**Open to AI engineering roles.** Best reached at [gaseer007@gmail.com](mailto:gaseer007@gmail.com) or on [LinkedIn](https://linkedin.com/in/gaseer).
