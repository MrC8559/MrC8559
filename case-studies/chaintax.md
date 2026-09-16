# ChainTax engineering case study

[ChainTax](https://chaintax.co.uk) is a live UK crypto-tax product I built for exchange, wallet, DeFi, NFT, staking, liquidity-pool, and related activity.

The production repository is private. This case study focuses on the engineering and release discipline that can be discussed publicly without exposing customer data or proprietary implementation details.

## Product problem

Crypto-tax software has to do more than produce a number. Complex activity can involve incomplete history, ambiguous protocol behaviour, pooled cost basis, income treatment, same-day matching, cross-wallet movement, and transactions that need human review.

The product therefore treats explainability and uncertainty as part of the core system rather than as presentation details.

## Engineering approach

The application is built as production financial software, with emphasis on:

- deterministic classification and calculation paths;
- explicit uncertainty and review states;
- audit-friendly outputs and visible calculation evidence;
- regression coverage for previously discovered edge cases;
- authenticated end-to-end testing around customer journeys;
- release gates that include build, security, accessibility, and production verification;
- conservative handling of claims that require legal or professional review.

The stack includes TypeScript, Next.js, Prisma, PostgreSQL-backed application data, browser automation, GitHub Actions, and Vercel deployment infrastructure.

## September 2026 production release evidence

A launch-readiness release on 12 September 2026 passed the following gates on the exact release content:

- **5,906 automated tests across 435 files**;
- **43 regression fixtures**;
- TypeScript, lint, Prisma validation, and production build checks;
- authenticated end-to-end customer smoke covering signup, correction, synthetic purchase, reports/downloads, sharing, and revocation;
- admin operations smoke;
- dependency advisory checks, secret-history scanning, and static application security checks;
- six separate accessibility smoke tests;
- post-deployment production verification;
- 57 read-only HTTP/HTML production checks;
- mobile and desktop browser verification at 390×844 and 1440×900;
- a second clean full CI execution after merge on the exact production content.

The release record also preserved known boundaries rather than converting incomplete evidence into a pass. For example, it did not claim universal browser accessibility, real Stripe webhook performance, Supabase email delivery, or independent reconciliation of every exported report.

## What this demonstrates

The useful part of this project is not the raw test count. It is the engineering process around a high-trust domain:

1. find a real edge case or production risk;
2. make it reproducible;
3. fix the underlying behaviour;
4. encode the failure as regression evidence;
5. run system-level gates;
6. verify the deployed result;
7. preserve remaining uncertainty explicitly.

That same evidence-first approach now informs my work on AI-agent security and research systems.

## Current status

ChainTax is live in production. The current product challenge is commercial validation and distribution rather than proving that another feature can be built.

Product: [chaintax.co.uk](https://chaintax.co.uk)
