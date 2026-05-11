# Security Policy

Humonics is trust infrastructure. Security is the product. We take all vulnerability reports seriously and respond quickly.

---

## Reporting a vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Report via GitHub's private security advisory system:

**→ [Submit a private advisory](https://github.com/humonicsprotocol/.github/security/advisories/new)**

Include as much detail as you can:
- Which repo and component is affected
- A clear description of the vulnerability
- Steps to reproduce or a proof-of-concept
- Your assessment of the impact
- Any suggested mitigations (optional)

---

## What to expect

| Timeline | Action |
|---|---|
| **24 hours** | Acknowledgement of your report |
| **72 hours** | Initial severity assessment and response |
| **7 days** | Fix in progress or decision on non-fix with explanation |
| **30 days** | Target for fix release (critical issues may be faster) |
| **After fix** | Coordinated disclosure — we credit you unless you prefer anonymity |

---

## Scope

### In scope — please report

- Authentication bypasses in the oracle service
- zkProof forgery or circuit vulnerabilities that allow false attestation
- Smart contract vulnerabilities (reentrancy, unauthorized access, replay attacks)
- PII leakage from the oracle service
- SDK or API vulnerabilities that allow certificate forgery or spoofing
- Nonce reuse vulnerabilities in the zk pipeline
- Dependency vulnerabilities with a clear exploit path

### Out of scope

- Issues in third-party dependencies without a direct exploit path in Humonics code
- Social engineering attacks
- Physical attacks
- Denial-of-service without a clear exploit
- Issues already reported by someone else
- Vulnerabilities in testnet deployments with no mainnet impact

---

## Severity levels

We use the [CVSS v3](https://www.first.org/cvss/) scoring system:

| Severity | Score | Examples |
|---|---|---|
| **Critical** | 9.0–10.0 | Forge a certificate without human verification; steal oracle private key |
| **High** | 7.0–8.9 | Bypass zkProof verification; leak identity data from oracle service |
| **Medium** | 4.0–6.9 | Replay attack on attestation; unauthorized certificate revocation |
| **Low** | 0.1–3.9 | Information disclosure with low impact |

---

## Bug bounty

A formal bug bounty program will launch alongside mainnet. Critical and high severity findings reported during testnet will be recognized in the program retroactively.

---

## Supported versions

| Repo | Supported versions |
|---|---|
| `soroban-contracts` | Latest deployed version only |
| `zk-circuits` | Latest artifact release only |
| `oracle-service` | Latest release only |
| `sdk` | Latest major version |
| `api` | Latest major version |

We do not backport security fixes to older versions.

---

## Disclosure policy

We follow coordinated disclosure:

1. Reporter submits privately
2. We confirm, assess, and fix
3. We release the fix
4. We publish a security advisory crediting the reporter (unless anonymity is requested)
5. Reporter may publish their own writeup after the advisory is public

We ask for a minimum 30-day embargo from report to public disclosure. For critical issues we may request more time.

---

## Contact

Security team: **security@humonics.io**

For non-security issues, open a public GitHub issue in the relevant repository.
