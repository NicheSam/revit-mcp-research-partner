# Routing Targets

Choose the destination by uncertainty, repeatability, evidence maturity, ownership, and available interface. Prefer the smallest target that can own the result safely. A case may have a primary target plus a later dependent target.

| Target | Choose when | Required minimum | Do not choose when |
| --- | --- | --- | --- |
| Deterministic plugin | Rules and inputs are stable, repeatable, bounded, and testable; Revit API transaction details and batch behavior matter | Explicit contract, edge cases, failure behavior, rollback, tests, deployment and readback plan | The workflow still depends on ambiguous interpretation or professional permission |
| Domain SOP | People can execute a stable rule consistently and automation is unnecessary, premature, or uneconomic | Trigger, inputs, decision rule, exceptions, owner, verification, escalation | The rule cannot be followed without unavailable machine observation or remains disputed |
| Skill or MCP workflow | The main value is gathering context, explaining evidence, locating exceptions, coordinating tools, or stopping for review | Sources to inspect, decision boundaries, output contract, stop conditions, human handoff | The task is a fully deterministic operation better owned by a plugin, or it requires professional approval |
| MCP Tool proposal | The engineering rule and machine operation are clear, but a bounded read or write interface is missing | Use case, inputs/outputs, identities, side effects, errors, preview/rollback/readback contract, authorization boundary | “MCP” is only a desired label, the domain rule is unresolved, or existing interfaces already suffice |
| GitHub Issue | A repository-owned defect, gap, contract change, or implementation task is reproducible and ready to track | Repository/version, evidence, reproduction or use case, expected behavior, acceptance criteria, dependencies | The finding is exploratory, confidential, not repo-specific, or lacks enough evidence for actionable scope |
| Research memo | Evidence is incomplete, conflicting, exploratory, or spans systems and must be preserved before commitment | Research question, sources, hypotheses, contradictions, open questions, proposed next probe | A stable owner and acceptance contract already make a more operational target appropriate |
| Human review | The decision carries structural, regulatory, contractual, safety, cross-discipline, or professional-signoff responsibility | Review packet with candidates, evidence, uncertainties, consequences, and explicit question | Never bypass this route by hiding judgment inside defaults or an automated tool |

The route is not the deliverable. After choosing a target, create the minimum artifact that lets that target act: an executable SOP draft for a Domain SOP, an interface contract for a Tool proposal, acceptance criteria for an Issue, or a bounded decision packet for human review. Use [practical-deliverables.md](practical-deliverables.md) for the artifact shape.

## Routing Test

Apply these questions in order:

1. Does the outcome require authority or professional judgment the system cannot own? Route to human review and stop automation at a reviewable boundary.
2. Are the rule, inputs, exceptions, and success criteria stable and testable? If yes, prefer a plugin for machine execution or a Domain SOP for human execution.
3. Is ambiguity itself the work: gathering context, explaining evidence, finding exceptions, or coordinating review? Prefer a Skill or MCP workflow.
4. Is a clear, bounded operation blocked only by a missing interface? Draft an MCP Tool proposal; use a GitHub Issue when a known repository owns implementation.
5. Are evidence or ownership still unresolved? Preserve a research memo and specify the next read-only probe.

## Avoid False Toolification

Do not propose a new MCP Tool merely because an Agent is involved. First check for an existing plugin command, API, MCP tool, SOP, or readback path. A Tool proposal is justified by a missing bounded interface, not by a broad desire for automation.

When a deterministic plugin and an Agent workflow both contribute, assign the plugin the stable operation and assign the Agent context gathering, explanation, exception handling, and handoff. Keep the human as owner of risk tolerance, exceptions, and professional approval.

## Conditional Route Back to REVIT_MCP_study

Assess this route only after the local research has a reviewable result. Re-read the current official repository instructions before every handoff; repository rules can change.

| Result found in the case | Candidate upstream route | Minimum before recommending | Keep local when |
| --- | --- | --- | --- |
| A reusable, verified human workflow | Domain SOP or other knowledge contribution allowed by the current guide | Public-safe evidence, duplicate search, trigger, steps, exceptions, validation, limits | It is still a local habit, conflicts with evidence, or exposes private project material |
| A reusable lesson across several cases | Lessons or knowledge route allowed by the current guide | Cross-case evidence and a claim scoped to tested coverage | It is a single anecdote or only a proposed principle |
| Agent orchestration that fits the repository's existing tools and current Skill rules | Skill contribution candidate | Independent trigger, output contract, stop conditions, tested scenarios, no hidden tool dependency | It duplicates an existing Skill or only adds terminology |
| A clear missing interface, defect, or core-code change | Issue-first proposal unless the current guide or a maintainer explicitly permits another path | Repository/version, use case or reproduction, evidence, expected behavior, acceptance criteria, exclusions | The capability or ownership is unresolved |
| A question, showcase, or early idea | Discussion or other route named by the current repository | Concise context, what was tried, and the decision requested | It contains confidential evidence or has an actionable defect better suited to an Issue |

Do not equate “useful to the community” with “ready to submit.” Use [revit-mcp-study-contribution.md](revit-mcp-study-contribution.md) to build the handoff and teach the user how to submit. A maintainer's explicit exception must be preserved as evidence and followed within its exact scope.

## Skill Suite Routing

Use one research entry plus specialist follow-ups when the work naturally changes mode. The research output should hand off only the bounded subtask, then bring the result back into the evidence ledger.

| Route | Choose when | Handoff must include | Return evidence |
| --- | --- | --- | --- |
| Stay in this skill | The main work is evidence gathering, workflow decomposition, principle extraction, or destination routing | Research question, in-scope sources, unresolved decisions | Research round using the output contract |
| Existing official-docs implementation skill | The case requires API capability, signatures, version behavior, or implementation patterns for a professional software host | Product/version evidence, API question, allowed sources, decision to verify | Official source URLs, confirmed/unconfirmed API contract, version limits, unsupported assumptions |
| Existing diagnosis skill | A reproducible failure needs root-cause isolation before deciding product, SOP, or issue routing | Symptom, reproduction, observed evidence, excluded causes, mutation boundary | Cause hypothesis, tested layers, remaining uncertainty, next verification |
| Existing TDD or code-review skill | The research has already produced a bounded implementation or verification task | Contract, acceptance evidence, risks, files or repository scope, no extra deployment authority | Test result, diff review, residual risk, evidence level |
| Existing prototype skill | A disposable experiment can reduce uncertainty without changing production assets or live models | Question, throwaway scope, success signal, disposal boundary | Prototype result, what it proves, what it cannot prove |
| Candidate new specialist skill | The same subworkflow repeatedly has its own trigger, completion condition, artifact, evidence sources, permission boundary, and context load | Split rationale, non-overlap with existing skills, shared principles to import | Independent behavior test showing lower confusion or lower context load |

Do not split a skill for a glossary, a case-specific example, or a single principle that belongs in this research contract. Shared principles should remain references until repeated use proves that a separate skill changes decisions better than routing through the entry skill.

## Handoff Contract

Every handoff to another skill or tool should state:

- Task: the single question or action being delegated.
- Scope: systems, files, model, version, or batch in scope; explicit exclusions.
- Evidence: sources already checked and the level each source proves.
- Boundary: read-only, prototype-only, implementation-only, or mutation-authorized; never imply deployment or model mutation from research approval.
- Stop condition: the exact uncertainty, missing authority, conflicting evidence, or failed check that must return to research or human review.
- Return shape: the evidence or artifact that must come back before routing continues.
