<div align="center">

<img src="https://raw.githubusercontent.com/humonicsprotocol/.github/main/assets/humonics-banner.svg" alt="Humonics" width="100%" />

# Humonics Protocol

### The Certificate Authority for Human-Origin Digital Work

**Cryptographic proof that specific content was created by a verified human — not AI.**

[![Built on Stellar](https://img.shields.io/badge/Built%20on-Stellar-black?logo=stellar&logoColor=white)](https://stellar.org)
[![Powered by Soroban](https://img.shields.io/badge/Powered%20by-Soroban-7c3aed)](https://soroban.stellar.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-6d28d9.svg)](https://opensource.org/licenses/MIT)
[![Status: Building](https://img.shields.io/badge/Status-Building-f59e0b)](https://github.com/humonicsprotocol)

</div>

---

## The problem

The internet can no longer tell the difference between human and AI-generated content.

Publishers can't verify their writers. Hiring platforms can't verify portfolios. AI training datasets have no way to source human-origin work. Courts have no cryptographic chain of custody for digital evidence.

**Humonics fixes this at the infrastructure layer.**

---

## What we're building

A decentralized, zero-knowledge certificate authority that issues tamper-proof credentials for human-created work — without exposing who the human is.

```
Human creator  →  ZK identity proof  →  Soroban smart contract  →  On-chain certificate
                  (no PII on-chain)      (Stellar network)          (anyone can verify)
```

Any publisher, platform, or system can call:

```typescript
const result = await client.verify(contentHash);
// → { certified: true, issuedAt: 1715000000, contentType: "text" }
```

---

## What Humonics certifies

| Content type | Examples |
|---|---|
| **Text** | Articles, essays, reports, books |
| **Code** | Repositories, pull requests, scripts |
| **Art** | Images, illustrations, design files |
| **Audio** | Podcasts, music, voice recordings |
| **Video** | Films, tutorials, documentary footage |

---

## How it works

**1. Verify the human**
Three parallel attestation paths — biometric liveness, social web-of-trust, and trusted oracles (Gov ID / KYC) — feed into a zero-knowledge circuit. The circuit proves the human passed verification without revealing their identity.

**2. Fingerprint the work**
The content hash, creator DID, timestamp, and context are bound together in a cryptographic commitment. The raw content stays off-chain (IPFS / Arweave). Only the proof lives on Stellar.

**3. Issue the certificate**
A Soroban smart contract mints an on-chain certificate. It's permanent, tamper-proof, and queryable by anyone in milliseconds.

**4. Verify anywhere**
One SDK call. One API endpoint. Works in browsers, backends, and CI pipelines.

---

## Repositories

| Repo | What it does |
|---|---|
| [`zk-circuits`](https://github.com/humonicsprotocol/zk-circuits) | Zero-knowledge circuits for human attestation (Circom + SnarkJS) |
| [`soroban-contracts`](https://github.com/humonicsprotocol/soroban-contracts) | On-chain certificate registry, verification gateway, HUM token (Rust + Soroban) |
| [`oracle-service`](https://github.com/humonicsprotocol/oracle-service) | Trusted oracle integrations — Gov ID, biometric liveness, KYC |
| [`sdk`](https://github.com/humonicsprotocol/sdk) | TypeScript SDK — `npm install @humonics/sdk` |
| [`api`](https://github.com/humonicsprotocol/api) | Public REST API for non-SDK consumers |
| [`dashboard`](https://github.com/humonicsprotocol/dashboard) | Web app for creators and verifiers |
| [`docs`](https://github.com/humonicsprotocol/docs) | Developer documentation |

---

## Who uses Humonics

<table>
<tr>
<td align="center" width="25%">
<b>Publishers</b><br/>
<sub>Verify journalist and writer attribution before publication</sub>
</td>
<td align="center" width="25%">
<b>Hiring platforms</b><br/>
<sub>Confirm portfolios and code samples are human-authored</sub>
</td>
<td align="center" width="25%">
<b>AI labs</b><br/>
<sub>Source verified human-origin training data at scale</sub>
</td>
<td align="center" width="25%">
<b>Legal / courts</b><br/>
<sub>Cryptographic provenance chain for digital evidence</sub>
</td>
</tr>
</table>

---

## Roadmap

```
Q3 2025  ████████░░  ZK circuits + CertificateRegistry testnet
Q4 2025  ██████░░░░  Verification gateway + public API + SDK v1
Q1 2026  ████░░░░░░  HUM token mainnet + staking + DAO governance
Q2 2026  ██░░░░░░░░  Art / audio / video + enterprise API + legal provenance
```

---

## Get started

```bash
npm install @humonics/sdk
```

```typescript
import { HumonicsClient } from '@humonics/sdk';

const client = new HumonicsClient({ network: 'testnet' });
const result = await client.verify(contentHash);
```

→ [Full documentation](https://docs.humonics.io)
→ [API reference](https://docs.humonics.io/api)
→ [Quickstart guide](https://docs.humonics.io/quickstart)

---

## Contributing

Humonics is open-source. We welcome contributions across all repositories.

The best places to start:

- [`zk-circuits`](https://github.com/humonicsprotocol/zk-circuits) — if you know Circom or cryptographic protocols
- [`soroban-contracts`](https://github.com/humonicsprotocol/soroban-contracts) — if you know Rust and want to build on Stellar
- [`sdk`](https://github.com/humonicsprotocol/sdk) — if you want to improve the developer experience

Read the [Contributing Guide](https://github.com/humonicsprotocol/.github/blob/main/CONTRIBUTING.md) before opening a PR.

Security issues must be reported via [private advisory](https://github.com/humonicsprotocol/.github/security/advisories/new) — not public issues.

---

<div align="center">

**Built on [Stellar](https://stellar.org) · Secured by [Soroban](https://soroban.stellar.org) · Proven by zero-knowledge**

[Website](https://humonics.io) · [Docs](https://docs.humonics.io) · [Twitter](https://x.com/humonics) · [Discord](https://discord.gg/humonics)

</div>
