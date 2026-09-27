# 🛠️ Upkeep Console — Autonomous Codebase Maintenance Copilot

> **Built with IBM Bob 2.0 for the Lablab.ai IBM Bob 2.0 Hackathon**

Upkeep Console is an autonomous codebase maintenance platform that scans live repositories, triages accumulated technical debt across objective risk-effort matrices, and dispatches parallel Bob 2.0 subagents to resolve safe issues with strict zero-regression test verification.

---

## ⚡ The Core Problem

Technical debt accumulates silently across long-lived services:
- Outdated dependencies with critical CVEs
- Dead code branches and uncalled functions
- Missing test coverage on retry logic and failure paths
- Unhandled promise rejections and silent webhook failures

Manual repository audits take **~14 hours** per service, leading teams to defer fixes until an outage occurs. Upkeep Console transforms this into a scheduled, autonomous **9-minute workflow**.

---

## 🚀 Key Features

* **Repository Context Ingestion:** Ingests complete service context across AST call graphs rather than isolated git diffs.
* **Objective Triage & Scoring:** Evaluates every finding for risk vs. developer effort before touching files.
* **Parallel Subagent Dispatching:** Dispatches safe remediation tasks simultaneously across isolated branches.
* **5-Gate Quality Pipeline:** Moves every item through *Detected ➔ Triaged ➔ Bob Fixing ➔ Verified ➔ Shipped*.
* **Zero-Regression Invariant:** Every automated patch is re-run against the full test suite before PR packaging.
* **In-Browser Interactive Analyzer:** Real-time client-side AST inspection checking for exposed tokens, unhandled async calls, leftover debug logs, and unsafe execution.

---

## 📊 Benchmark Results (`checkout-service`)

| Metric | Before Upkeep | After Upkeep Session | Impact |
| :--- | :---: | :---: | :---: |
| **Test Coverage** | 61% | **88%** | +27% test assertions |
| **Known CVEs** | 1 (lodash) | **0** | Auto-patched safely |
| **Dead Branches** | 3 | **0** | Cleaned and purged |
| **Open Debt Items** | 9 | **2** | 7 auto-fixed, 2 held for human review |
| **Passing Tests** | 31 / 41 | **41 / 41** | 100% regression verification |
| **Audit & Fix Time** | ~14 hours | **~9 minutes** | **13.8 hrs developer time returned** |

---

## 🛠️ The 5-Gate Maintenance Pipeline

1. **Gate 01 · Detected:** Deep scan maps all stale dependencies, dead code, and untested execution paths.
2. **Gate 02 · Triaged:** Every issue receives an objective classification; nothing is edited prior to scoring.
3. **Gate 03 · Bob Fixing:** Safe tasks are dispatched to parallel Bob 2.0 subagents on dedicated branches.
4. **Gate 04 · Verified:** Fixes run against automated regression tests to guarantee zero regressions.
5. **Gate 05 · Shipped:** Clean changelog generated; architectural changes (e.g. major framework shifts) held for maintainer approval.

---

## 🤖 IBM Bob 2.0 Integration Details

* **Agent Mode Repository Indexing:** Bob analyzes call trees, locating dead functions (`legacyDiscount`) and unhandled exception paths.
* **Parallel Subagents:** Concurrent instances work in parallel on isolated branches (Subagent A on CVE bumps, Subagent B on dead code removal, Subagent C on retry tests).
* **Enterprise Guardrails:** Enforces `.bobignore` to ensure sensitive credentials and runtime environment files remain unindexed.

---

## 💻 Tech Stack

* **AI Engine:** IBM Bob 2.0 (Agent Mode & Parallel Subagents)
* **Frontend:** Tailwind CSS, HTML5, JavaScript (ES6+), Canvas Graphics
* **Deployment:** Vercel (Instant edge delivery)
* **Testing & Verification:** Pytest, AST Parsers, Git Branch Automation

---

## 🚀 Running Locally

1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)<YOUR_USERNAME>/upkeep-console.git
   cd upkeep-console
