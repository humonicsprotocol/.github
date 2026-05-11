# Contributing to Humonics

Thank you for your interest in contributing to Humonics. This is open-source infrastructure for human trust on the internet — every contribution matters.

---

## Before you start

- Read the [README](https://github.com/humonicsprotocol/core/blob/main/README.md) to understand the full system architecture
- Browse open issues in the relevant repo — especially those tagged `good first issue`
- For significant changes, open an issue first to discuss the approach before writing code

---

## How to contribute

### 1. Find the right repo

| If you want to work on... | Go to |
|---|---|
| ZK circuits, cryptographic proofs | [`zk-circuits`](https://github.com/humonicsprotocol/zk-circuits) |
| Soroban smart contracts (Rust) | [`soroban-contracts`](https://github.com/humonicsprotocol/soroban-contracts) |
| Oracle / identity integrations | [`oracle-service`](https://github.com/humonicsprotocol/oracle-service) |
| TypeScript SDK | [`sdk`](https://github.com/humonicsprotocol/sdk) |
| Public REST API | [`api`](https://github.com/humonicsprotocol/api) |
| Web dashboard | [`dashboard`](https://github.com/humonicsprotocol/dashboard) |
| Documentation | [`docs`](https://github.com/humonicsprotocol/docs) |

### 2. Fork and branch

```bash
# Fork the repo on GitHub, then clone your fork
git clone https://github.com/<your-username>/<repo-name>
cd <repo-name>

# Create a branch from develop (not main)
git checkout develop
git pull origin develop
git checkout -b feat/your-feature-name
```

Branch naming:
- `feat/` — new feature
- `fix/` — bug fix
- `docs/` — documentation only
- `chore/` — tooling, deps, config

### 3. Make your changes

- Read the `CLAUDE.md` file in the repo root — it describes the exact structure, conventions, and rules for that repo
- Keep changes focused — one feature or fix per PR
- Add or update tests for any logic changes
- Run the full test suite before pushing

```bash
npm test        # TypeScript repos
cargo test      # Rust / Soroban repos
```

### 4. Open a pull request

- PR target is always `develop` — never `main`
- Fill in the PR template completely
- Link the issue your PR closes: `Closes #123`
- All CI checks must pass before review
- At least one approval required from the relevant team

---

## Commit message format

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <short description>

feat(sdk): add batchVerify() method
fix(contracts): prevent double issuance on same content hash
docs(oracle-service): update env variable reference
chore(zk-circuits): upgrade snarkjs to 0.7
```

Types: `feat`, `fix`, `docs`, `chore`, `test`, `refactor`, `perf`

---

## Code standards

### All repos
- No `console.log` left in production code
- No commented-out code in PRs
- All public functions must have types — no `any`
- Env variables must be documented in `.env.example`

### Soroban contracts (Rust)
- No `unwrap()` in contract code — handle all Results
- All state-changing functions must call `env.require_auth()`
- Every new function needs tests for happy path + unauthorized caller

### ZK circuits (Circom)
- No public signals that reveal identity information
- Every circuit change requires re-running trusted setup
- New circuits must include test fixtures in `tests/fixtures/`

### Oracle service
- Never log request bodies
- Never store or return PII from identity providers
- New providers must implement the `IdentityProvider` interface

---

## Security vulnerabilities

**Do not open public issues for security bugs.**

Report vulnerabilities via [GitHub private security advisory](https://github.com/humonicsprotocol/.github/security/advisories/new). See [SECURITY.md](./SECURITY.md) for the full policy.

---

## Getting help

- Open a [discussion](https://github.com/orgs/humonicsprotocol/discussions) for questions
- Join [Discord](https://discord.gg/humonics) for real-time conversation
- Tag your issue with the right repo label so the right team sees it

---

## Contributor license

By submitting a PR you agree that your contributions are licensed under the same [MIT License](./LICENSE) that covers the project.
