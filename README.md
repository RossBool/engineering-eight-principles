# Parallel Front Protocol (三八线协议)

> A software engineering lifecycle methodology distilled from large-scale systems engineering experience.
>
> **Core idea: Multi-front parallel execution, clear boundaries, deliver to build consensus, stabilize delivery through consensus.**

[![Version](https://img.shields.io/badge/version-1.2.0-blue)](https://github.com)
[![QoderWork Skill](https://img.shields.io/badge/QoderWork-Skill-d3192a)](https://docs.qoder.com/qoderwork/introduction)
[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)

---

## Overview

The Parallel Front Protocol is a structured methodology for managing software projects from inception to launch. It provides eight guiding principles and a six-phase lifecycle, each with explicit entry conditions, core actions, and exit gates.

The methodology is designed for teams of 3+ people working on projects spanning 2+ months, but includes simplified paths for smaller teams and shorter timelines.

### Who is this for?

Engineering leads, technical project managers, and AI coding assistants (via QoderWork) who need a disciplined framework for project planning, diagnostic assessment, iteration management, and launch readiness.

---

## Eight Principles

| # | Codename | Engineering Meaning | One-liner |
|---|----------|---------------------|----------|
| 1 | **Parallel Front** | Services must have clear interface contracts and isolation boundaries | Draw the "demarcation line" between services — clear contracts, independent evolution |
| 2 | **Flank Landing** | Find the leverage point that shifts the entire project trajectory | Identify the one technical decision that flips the game, then commit fully |
| 3 | **Chosin Reservoir** | Under extreme constraints, concentrate resources on the critical module | After picking your entry point, focus all resources on the key breakthrough |
| 4 | **Anti-Strangulation** | Critical paths need multi-route redundancy: circuit breakers, fallbacks, auto-recovery | Core pipelines must have backup routes — circuit break, degrade, auto-recover |
| 5 | **Triangle Hill** | Quality baselines are non-negotiable — SLA, performance, security | SLA, performance baselines, security standards — lose these and you lose everything |
| 6 | **Fight & Negotiate** | Maintain iteration cadence; let delivered results drive requirement convergence | Don't wait for perfect requirements — iterative delivery IS the best negotiation |
| 7 | **Jincheng** | Pre-launch stress testing and contingency plans — the final push decides success | Pre-launch end-to-end testing and contingency plans deserve 50% of your effort |
| 8 | **Cost Awareness** | Every technical decision has hidden costs — make them visible | Cut features, sidelined team members, sacrificed explorations — see them all |

---

## Six-Phase Lifecycle

```
Phase 0          Phase 1          Phase 2          Phase 3          Phase 4          Phase 5
立项研判    →    迭代冲刺    →    韧性加固    →    质量收敛    →    持续交付    →    上线收尾
(Inception)      (Sprint)         (Resilience)     (Quality)        (Delivery)       (Launch)
```

Each phase has strict **entry conditions**, **core actions**, and **exit gates**. Phases cannot be skipped but can be merged (for small teams) or revisited (when conditions change). Detailed phase operations are documented in [`phases.md`](./phases.md).

### Simplified Paths by Team Size

| Team Size | Recommended Path |
|-----------|------------------|
| 5+ members | Full six-phase lifecycle |
| 3–5 members | Merge Phase 2+3, merge Phase 4+5 |
| 2–3 members | Use only Principles 1+5+6, skip formal phases |
| Solo / <2 weeks | Methodology overhead exceeds project cost — not recommended |

---

## File Structure

```
parallel-front/
├── SKILL.md                        # Main skill definition (v1.2.0)
├── phases.md                       # Six-phase operations manual
├── assessment-template.md          # Project diagnostic report template
├── campaign-template.md            # Phase execution plan template
├── dashboard-template.html         # HTML audit report dashboard
├── example-payment-platform.md     # Example: Payment platform v2.0 migration
├── example-diagnostic-report.md    # Example: Backend refactor diagnostic report
├── README.md                       # This file
└── LICENSE
```

### What each file does

**SKILL.md** is the core methodology document. It defines the eight principles, six phases, four usage modes, decision frameworks, and anti-pattern list. If you're installing this as a QoderWork skill, this is the file the agent reads.

**phases.md** is the detailed operations manual for each lifecycle phase. It includes entry conditions, step-by-step core actions, exit gates, and phase transition rules.

**assessment-template.md** is a structured template for project diagnostic reports. It covers six sections: overall diagnosis, eight-principle scan, phase assessment, risk matrix, action recommendations, and next assessment plan.

**campaign-template.md** is a template for phase execution plans. It structures project status, leverage points, phase-by-phase plans, risk contingency, and milestone overview.

**dashboard-template.html** is a self-contained HTML audit report dashboard. It renders a radar chart (Canvas), phase progress bar, principle health cards, risk findings, and action items. Data is injected via `window.__EIGHT_PRINCIPLES_DATA__`. Features oklch color system with rgba fallback, XSS-safe rendering, and full accessibility support.

**example-payment-platform.md** demonstrates a complete phase execution plan for a payment platform v2.0 migration (5-person team, 4-month timeline).

**example-diagnostic-report.md** demonstrates a complete diagnostic report for a game configuration backend refactor, including eight-principle scan and risk matrix.

---

## Usage Modes

The methodology supports four interaction modes depending on what the user needs:

| Mode | Trigger | Output |
|------|---------|--------|
| **Diagnostic** | "Assess this project" / "Project health check" | Markdown diagnostic report |
| **Planning** | "Plan this project" / "Execution plan" | Markdown execution plan |
| **Dashboard** | "Show me a global view" / "Project status" | HTML audit report |
| **Navigation** | "What should I do next?" / "Next phase" | Phase assessment + action items |

### Quick Start

When applying the methodology for the first time, answer three questions:

1. **Is this a new project or in-progress?** — New projects start from Phase 0; in-progress projects begin with a diagnostic.
2. **What do you need?** — Diagnose, plan, visualize, or navigate.
3. **What's the biggest pain point?** — This prioritizes which principles to scan first.

---

## Installation

### For QoderWork

Copy the entire directory to your QoderWork skills folder:

```bash
cp -R parallel-front/ ~/.qoderwork/skills/parallel-front/
```

Once installed, the skill is automatically available when working with QoderWork. Trigger it by mentioning "三八线协议", "parallel-front", "项目诊断", "执行方案", or any of the related keywords.

### For Manual Use

All files are plain Markdown (plus one HTML template). You can read them directly, copy templates into your own project documentation, or integrate them into other AI assistant workflows.

---

## Data Contract (Dashboard Template)

The HTML dashboard template accepts data via a global JavaScript variable:

```javascript
window.__EIGHT_PRINCIPLES_DATA__ = {
  projectName: "My Project",
  overallScore: 72,           // 0-100
  overallStatus: "warn",      // ok | warn | alert
  currentPhase: 2,            // 0-indexed (displays as Phase 3)
  phases: [
    { name: "立项研判", status: "completed" },
    { name: "迭代冲刺", status: "completed" },
    { name: "韧性加固", status: "current" },
    { name: "质量收敛", status: "pending" },
    { name: "持续交付", status: "pending" },
    { name: "上线收尾", status: "pending" }
  ],
  principles: [
    { name: "架构边界", score: 85, status: "ok" },
    { name: "杠杆点",   score: 70, status: "warn" },
    // ... all 8 principles
  ],
  metrics: [
    { label: "Sprint Velocity", value: "85%", trend: "up" },
    // ...
  ],
  risks: [
    { severity: "critical", title: "...", description: "...", mitigation: "..." },
    // ...
  ],
  actions: [
    { priority: "high", owner: "...", deadline: "...", task: "..." },
    // ...
  ]
};
```

**Score boundaries:** `score >= 75` → ok (green), `55–74` → warn (amber), `< 55` → alert (red).

Any missing keys fall back to built-in defaults — the template never renders `undefined` values.

---

## Key Decision Frameworks

The methodology includes three reusable decision frameworks:

**Boundary Delineation** (for architecture decisions): Identify stakeholders → draw the line → establish interface contracts → evolve independently.

**Leverage Point Identification** (when stuck): What's the cost of the current approach? → Is there an overlooked alternative? → Once chosen, commit fully.

**Requirement Negotiation Protocol** (when requirements keep changing): Keep delivering every 2 weeks → use delivered work as negotiation leverage → classify requirements into frozen / negotiable / flexible.

---

## Anti-Patterns

| Anti-Pattern | Consequence |
|-------------|-------------|
| Scope creep | Requirements expand endlessly, core objectives lose focus |
| Resource stacking trap | More people doesn't solve the underlying problem |
| Single-point-of-failure cascade | No redundancy on critical paths → full pipeline collapse |
| Pre-launch requirement ambush | Massive changes inserted right before delivery |
| Missing retrospective | Experience is lost; next project repeats the same mistakes |

---

## Examples

Two complete examples are included in this repository:

**Payment Platform v2.0 Migration** ([`example-payment-platform.md`](./example-payment-platform.md)) — A 5-person team migrating a payment middleware over 4 months. Demonstrates the full six-phase execution plan with risk contingency.

**Backend Refactor Diagnostic** ([`example-diagnostic-report.md`](./example-diagnostic-report.md)) — A diagnostic report for a game configuration backend refactor at Phase 3 (Quality Convergence). Demonstrates the eight-principle scan, risk matrix, and action recommendations.

---

## Design Principles

The methodology and its templates follow these design constraints:

- **Pure engineering terminology** — no military jargon in deliverables; codenames are internal references only.
- **Editorial-grade output** — audit reports use serif display + sans-serif body + monospace data, inspired by professional engineering reviews.
- **Accessibility** — HTML templates include ARIA roles, labels, and `prefers-reduced-motion` support.
- **oklch color system** — with automatic rgba fallback for environments that don't support oklch.
- **XSS-safe** — all user-provided strings are escaped before DOM insertion.

---

## Contributing

Contributions are welcome. If you've used this methodology on a real project and have feedback, improvements, or new examples, please open an issue or pull request.

---

## License

MIT
