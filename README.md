<div align="center">
  <img src="assets/banner.gif" width="100%" alt="Animated CAD blueprint banner: an involute 3:2 gear mesh and reciprocating slider-crank piston compress context payload on the left while driving the SPEC → AGENTS → REVIEW → SHIP engineering pipeline on the right for Marvin K.">
  <p><strong>Software engineered the way a precision machine is built — spec-first, deterministic, auditable.</strong></p>

  <a href="https://github.com/777marvin/ext-broke/releases"><img src="https://img.shields.io/github/v/release/777marvin/ext-broke?color=38bdf8&labelColor=080d1a&label=ext-broke" alt="Release"></a>
  <a href="https://github.com/777marvin/ext-broke/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/777marvin/ext-broke/ci.yml?color=38bdf8&labelColor=080d1a&label=ci" alt="CI"></a>
  <a href="https://github.com/777marvin/ext-broke/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-fb923c?labelColor=080d1a" alt="MIT License"></a>
  <a href="https://www.linkedin.com/in/marvin-knabe/"><img src="https://img.shields.io/badge/linkedin-marvin--knabe-38bdf8?labelColor=080d1a&logo=linkedin&logoColor=38bdf8" alt="LinkedIn"></a>
  <a href="mailto:777marvin.dev@proton.me"><img src="https://img.shields.io/badge/mail-777marvin.dev@proton.me-fb923c?labelColor=080d1a&logo=protonmail&logoColor=fb923c" alt="Email"></a>
</div>

---

## 01 // ENGINEERING PHILOSOPHY

I come from **mechanical engineering**. In machine design, nobody walks up to a CNC mill and improvises a gearbox by trial and error — you start with tolerances, kinematic constraints, a technical drawing, and verification gates.

I build software the exact same way:
- **Specifications over vibe-coding:** Written architecture specs, explicit invariants, and deterministic test suites before an agent touches implementation.
- **Agents as precision actuators:** AI agents execute scoped tasks inside strict boundaries; I design the system, enforce quality gates, and verify every diff.
- **Intersection of two worlds:** Combining mechanical-engineering rigor with modern **TypeScript & AI-agent tooling**.

---

## 02 // FLAGSHIP SYSTEM: [`ext-broke`](https://github.com/777marvin/ext-broke)

**[ext-broke](https://github.com/777marvin/ext-broke)** is a local-first token budget & context-compression engine for [AiderDesk](https://github.com/hotovo/aider-desk).

Long agentic coding sessions resend the same growing conversation history on every turn. **broke** intercepts the outbound payload *before each model call* and compresses eligible older material across three progressive stages — while keeping your initial prompt, recent turns, and stored task history **100 % intact**.

```bash
npx @aiderdesk/extensions install -g https://github.com/777marvin/ext-broke
```

### Architecture & Key Capabilities (v1.4.0)

| Subsystem | Engineering Mechanism | Impact |
| :--- | :--- | :--- |
| **`structural` → `truncate` → `summarize`** | 3-stage progressive compression pipeline; optional deep stage offloads summarization **locally via Ollama** (`qwen2.5-coder:3b`) with zero extra cloud calls | **32.2 %** (`truncate`) up to **89.7 %** (`summarize`) char reduction in deterministic benchmark |
| **`broke-search` (Offline BM25)** | Local workspace keyword indexer with a strict `2000 ms` scan budget returning exact `path:line` snippets | Prevents full-file context flooding during agent exploration |
| **`ST-slicing` & Cache-Friendly Mode** | Extracts TypeScript/code interface views for large reads and preserves already-sent byte prefixes | Maximizes provider prompt-cache hit rates across turns |
| **Cryptographically Signed Releases** | In-app `/broke update` verifies **Ed25519-signed `SHA256SUMS`** manifests; secrets are redacted before summarization & non-loopback hosts are blocked by default | Tamper-proof updates & strict local-first privacy |

### Deterministic Reference Benchmark (`npm run bench`)
*67 messages · 351,403 characters · zero randomness · no LLM required for baseline:*

| Pipeline Stage | Characters Removed | Payload Remaining | Reduction |
| :--- | ---: | ---: | ---: |
| **`truncate`** *(shipped default)* | **113,070 chars** (~28.3k est. tokens) | 238,333 chars | **32.2 %** |
| **`summarize`** *(with local Ollama)* | **315,263 chars** (~78.8k est. tokens) | 36,140 chars | **89.7 %** |

> *Transparency note:* Token counts use the deterministic `chars / 4` heuristic and are always reported as estimates, never as guaranteed provider billing claims. Live per-session telemetry is available anytime via the status bar badge and `/broke measure`.

---

## 03 // WORKFLOW & TOOLING (`SPEC → AGENTS → REVIEW → SHIP`)

1. **`01 // SPEC` (BMAD Method):** Role-based specification, system boundaries, and task decomposition version-controlled directly in Git.
2. **`02 // AGENTS` (AiderDesk + Local & Frontier Models):** Scoped execution against explicit acceptance criteria.
3. **`03 // REVIEW` (Deterministic Gates):** Automated test suites, reproducible benchmarks, layout/lint verification, and human code review.
4. **`04 // SHIP` (Auditable Delivery):** Public planning artifacts and cryptographically signed releases (`Ed25519`). Both the process and the output are inspectable.

---

## 04 // OPEN SOURCE & CONTRIBUTIONS

- **[777marvin/ext-broke](https://github.com/777marvin/ext-broke)** — Creator & maintainer. 22+ releases shipped (`v0.3.0` → `v1.4.0`), MIT licensed, TypeScript.
- **[hotovo/aider-desk#981](https://github.com/hotovo/aider-desk/pull/981)** — Upstream contributor: authored and shipped the complete German (`de`) localization for AiderDesk (the 5th official language alongside English, Chinese, Russian, and Korean).

---

## 05 // NOW & NEXT

- Completing my qualification as **State-Certified Technician in Mechanical Engineering** (*Staatlich geprüfter Techniker — Maschinentechnik*, expected July 2027).
- Actively evolving `ext-broke` — explore the [Feature Deep-Dive](https://github.com/777marvin/ext-broke/blob/main/docs/features.md) and [Public Roadmap](https://github.com/777marvin/ext-broke/blob/main/docs/roadmap.md).

---

## 06 // CONTACT

- **Engineering Collaboration & Contract Work** (AI-agent tooling, TypeScript automation, industrial/technical software):  
  [777marvin.dev@proton.me](mailto:777marvin.dev@proton.me) · [LinkedIn — Marvin Knabe](https://www.linkedin.com/in/marvin-knabe/)
- **Feedback, Benchmarks & Issues:**  
  Open an issue or discussion in **[ext-broke/issues](https://github.com/777marvin/ext-broke/issues)** — attach `/broke stats` or `/broke measure` output (contains zero conversation text).
