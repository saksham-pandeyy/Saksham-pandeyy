<div align="center">

# Hi, I'm Saksham

**Product Engineer — I build things that keep working when the network doesn't.**

[![Portfolio](https://img.shields.io/badge/Portfolio-sakshampandey.is-a.dev-2563EB?style=flat-square&logo=vercel)](https://sakshampandey.is-a.dev/)

React Native · Expo · TypeScript · Next.js · Offline-first architecture

</div>

---

## What I work on

Most of my interest sits at the intersection of **mobile engineering** and **systems that have to survive bad conditions** — poor connectivity, unreliable networks, users who are far from any server.

That's the core problem behind everything below.

---

## Current work

### Korvia — offline-first field data collection

A React Native + Expo app for field officers collecting structured survey data in places with no reliable signal.

**The interesting part isn't the UI — it's what happens when the request fails.**

- Submission is committed to SQLite in the **same transaction** that enqueues it for upload, so a crash mid-submit doesn't lose the work
- A durable **outbox** is drained by a single-writer runner with exponential-backoff retries
- Errors are **classified** (network / healable / retryable / fatal) instead of retried blindly
- Mandatory high-accuracy **GPS stamping** with Kalman-filtered smoothing for audit trails
- Multi-org partitioning so one organisation's rows can never surface in another's

**Stack:** React Native 0.81 · Expo SDK 54 · WatermelonDB (SQLite) · Zustand · TanStack Query

**Engineering:** 119 Jest suites, ~1,600 tests · ESLint clean · 6 GitHub Actions workflows that inspect only changed files

[Architecture case study →](https://github.com/saksham-pandeyy/field-collect-architecture)

---

## Selected work

| Project | What it is | Stack |
| --- | --- | --- |
| **[HandWritting](https://github.com/saksham-pandeyy/HandWritting)** | Text-to-handwriting converter. My most-starred project — 16 stars. | React, JavaScript |
| **[field-collect-architecture](https://github.com/saksham-pandeyy/field-collect-architecture)** | Written case study of an offline-first sync engine: outbox pattern, conflict reconciliation, retry semantics. | PWA, Dexie, outbox |
| **[portfolio](https://github.com/saksham-pandeyy/portfolio)** | Personal site with an emphasis on performance and accessibility. | Next.js, TypeScript, Tailwind, Framer Motion |
| **[DigiCurr](https://github.com/saksham-pandeyy/DigiCurr)** | Crypto screener with live market data and filtering. | React, Context API, CoinGecko API |
| **[mock-interview-ai](https://github.com/saksham-pandeyy/mock-interview-ai)** | AI-assisted interview practice. | JavaScript |

---

## How I like to build

A few opinions I've actually held to, rather than ones I switched off:

**Offline-first is a data-integrity decision, not a feature.** If the write path can fail silently, the product is broken — the network is just the most common reason it fails.

**If it isn't tested, it isn't finished.** Korvia's sync engine has more tests than features, because that layer has the least room for error and the fewest people watching it.

**Only look at what changed.** The CI workflows lint changed files and run only the test suites that import them. Running everything on every commit trains people to ignore the result.

**Write it down.** Most of my repos include an architecture document. The reason I understand a system is because I explained it.

---

## Currently

- Building Korvia
- Open to freelance mobile engineering work
- Occasionally writing about offline-first architecture

**Reach me:** [sakshampandey.is-a.dev](https://sakshampandey.is-a.dev/)