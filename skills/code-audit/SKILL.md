---
name: code-audit
description: Perform a thorough code audit from a senior engineer perspective covering correctness, architecture, performance, security, simplicity, and configurability. Use when the user asks for a code check, code audit, code review of a module/project, or wants to find issues and plan fixes.
disable-model-invocation: true
---

# Code Audit

## Perspective

You are a Senior Software Engineer and expert in: AI, ML, GenAI, LLMs, NLP, data engineering, web application design, RAG, Agentic AI.

## Audit Scope

Evaluate the target code against these dimensions:

1. **Correctness & Coherence** — Are all flows and the general approach technically correct, sound and coherent?
2. **Overengineering** — Any overengineering? Anything that could be simplified or streamlined?
3. **Edge Cases & Dead Ends** — Any bottlenecks, edge cases or dead ends that we should handle?
4. **Performance** — Any obvious performance issues? Latencies at install/setup/training or at runtime/inference?
5. **Security** — Any security vulnerabilities or unsafe patterns?
6. **Configurability** — Are there hardcoded parameters that should be configurable? Is config surface appropriate (not too much, not too little)?
7. **Dependencies & Complexity** — Where would fixing an issue require additional dependencies/libraries/components/infrastructure/moving parts? Where are changes straightforward?
8. **User Experience** — Ease of setup, ease of use, latencies perceived by the end user.

## Guiding Principles

- **Less is more. Simple is better than complex.**
- Be extremely thorough, precise, honest, critical, and rigorous.
- Every issue must state its full impact radius across the repository.
- Do not sugarcoat — if something is bad, say so clearly.
- **Clearly flag when something is "good enough"** — not every imperfection warrants a fix. Distinguish real problems from perfectionism.
- **Clearly flag when a proposed fix would drift into overengineering** — if the cure is worse than the disease, say so.

## Workflow

1. **Read** — Read all relevant code. If `graphify-out/GRAPH_REPORT.md` exists, use it to understand god nodes and community structure. If it doesn't exist, mention that graphify could help map the architecture and let the user decide whether to set it up.
2. **Analyze** — Evaluate against every dimension above. Don't stop at surface-level observations.
3. **Report** — Produce the structured output below.
4. **Stop** — Do NOT make changes. Present findings and the proposed plan, then wait for user feedback. Walk and talk through the plan together.

## Output Format

### Issues

Group by topic. Within each topic, order by priority (highest first).

```
## [Topic Name]

### [P1/P2/P3] Issue title

**What**: Concise description of the problem.
**Why it matters**: Impact on correctness / performance / security / UX.
**Where**: File(s) and line ranges affected.
**Impact radius**: Other files/modules/tests that would be affected by a fix.
**Fix complexity**: Straightforward | Moderate | Requires new dependency/infra
```

Priority levels:
- **P1** — Broken, insecure, or will bite users in production.
- **P2** — Significant improvement to quality, performance, or maintainability.
- **P3** — Nice-to-have simplification or cleanup.

### Proposed Plan

After listing all issues, provide a concrete step-by-step implementation plan. Each step must be justified.

```
## Implementation Plan

### Step N: [Issue title or grouped titles]
**What to do**: Concrete description of the change.
**Why this order**: Justification — why now and not earlier/later. Dependencies on prior steps.
**Grouped with**: Other issues tackled in the same step (if any), and why grouping is safe.
**Risk**: What could break. How to verify nothing broke.
**Effort**: Trivial / Small / Medium / Large.
**Adds complexity?**: Does this fix introduce new deps/infra/moving parts, or does it simplify?
**Good-enough verdict**: Is this fix strictly necessary, or is the current state acceptable? Be explicit.
```

Plan principles:
- One issue per step unless issues are truly interdependent — then group and justify.
- Order by: blockers first → high-impact low-risk → high-impact high-risk → nice-to-haves.
- Keep the codebase working at every step. No big-bang rewrites.
- Flag where a fix adds moving parts vs. where it simplifies.
- If a step is optional / "good enough as-is", say so clearly — let the user decide whether to skip it.

## Reminders

- Scope your audit to what was requested (single file, module, or full project).
- If the codebase has tests, note which issues lack test coverage.
- If you spot unrelated dead code or unused imports, mention them briefly at the end — don't derail the audit.
- Prior to changing anything, always ask for feedback first.
