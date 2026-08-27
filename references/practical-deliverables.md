# Practical Research Deliverables

Use this reference when the user needs more than a research classification. Convert case evidence into a concrete artifact that another person, Skill, repository, or review gate can use immediately. Do not copy case-specific vocabulary into general principles.

## Plain-Language Output Rule

Write the recommendation in the user's working language first. Prefer “what we know”, “what to do next”, “who needs to decide”, and “how we will check” over labels such as schema, transaction, runtime, or interface. Use a technical term only when it names a concrete thing the next owner must locate or verify; give its practical meaning at first use. Keep the detailed fields inside the artifact instead of making the whole answer read like an implementation document.

## Choose the Deliverable by the Next Decision

| Next decision | Primary deliverable | Minimum useful content |
| --- | --- | --- |
| What should we do next? | Action register | Prioritized action, owner, prerequisite, expected result, verification, stop condition |
| How should people repeat this workflow? | Domain SOP draft | Preconditions, inputs, phases, decisions, exceptions, outputs, validation, escalation |
| Can this become a bounded machine interface? | Tool proposal | Use case, input/output schema, identity, side effects, errors, preview, rollback, readback |
| Is a repository change ready to track? | Issue draft | Reproduction or use case, current evidence, expected behavior, acceptance criteria, exclusions |
| What must a responsible person decide? | Review packet | Candidates, evidence, uncertainty, consequence, explicit question, approval scope |
| How do sources, decisions, gates, and destinations relate? | SVG context or workflow diagram | Traceable nodes, complete branches, human gates, stop states, output destinations |
| What uncertainty should be tested first? | Validation matrix | Claim, probe, expected observation, contrary observation, evidence level, next route |
| I have an improvement idea but do not know what can realize it | Capability conversion map | Current work, desired change, needed capabilities, existing coverage, gap, smallest trial |
| Is this ready to give back to REVIT_MCP_study? | Upstream contribution pack | Fit, current rules checked, duplicate search, public-safe evidence, target, draft, validation, limits, submission boundary |

When several deliverables are useful, choose one primary artifact and only the dependent artifacts needed to make it actionable. Do not generate a bundle of empty templates.

## Recommendation Standard

Recommendations must be operational rather than aspirational. For each recommendation, state:

- **Action:** the exact bounded action or artifact to create.
- **Reason:** the evidence and decision criterion supporting it.
- **Owner:** the person, Agent, plugin, repository, or unresolved authority responsible.
- **Prerequisite:** the information, interface, approval, or stable state required first.
- **Expected result:** the observable change or reduced uncertainty.
- **Verification:** how the result will be checked independently at the needed evidence level.
- **Stop condition:** what prevents continuation or returns the case to research or human review.

Prefer two or three ranked recommendations over a long unranked list. Separate immediate read-only work from later implementation, deployment, or model mutation.

## Domain SOP Draft Shape

A useful SOP draft should normally contain:

1. **Purpose and decision:** what repeated question the SOP resolves and what it does not authorize.
2. **Trigger and preconditions:** when it applies, required sources, active state, versions, permissions, and known exclusions.
3. **Inputs and source of truth:** required fields, identity keys, units, coordinate basis, revision or batch, and which source wins when they conflict.
4. **Phases:** reconnaissance, scope confirmation, candidate production, review, execution if authorized, readback, and preservation.
5. **Decision states:** use explicit states such as `candidate`, `review_required`, `blocked`, and `verified`, with the transition rule for each.
6. **Rules and judgments:** deterministic formulas or conditions separated from contextual or professional judgment.
7. **Failure and recovery:** partial failure behavior, human-readable reason, retry boundary, rollback, and emergency stop.
8. **Outputs:** schema, report, preview, diagram, Issue, or model result, including fields needed for later lookup and readback.
9. **Validation:** observable success criteria, counterexample checks, coverage limit, and proof level.
10. **Known gaps and next route:** unresolved assumptions, missing interfaces, non-goals, and destination for follow-up.

Use the shape selectively. A small SOP can be short, but it must not omit a decision branch, required input, or failure path that changes safety or correctness.

## SVG Context and Workflow Diagrams

Create an SVG when relationships or branching are materially clearer visually: multiple evidence sources feed a decision, several roles exchange responsibility, the workflow has three or more dependent stages, or the same gate routes to multiple destinations.

Use this default information architecture:

```text
evidence sources
-> interpretation and candidate formation
-> reviewable representation
-> decision gates and stop states
-> authorized action or handoff
-> independent readback
-> routed outcome
```

The diagram must distinguish:

- recorded evidence from Agent inference;
- deterministic rule from contextual judgment;
- proposed action from executed and independently verified result;
- automated path from human-owned decision;
- normal completion from stop, rollback, and unresolved routes.

### SVG delivery requirements

- Produce a standalone UTF-8 `.svg` with a `viewBox`; do not depend on external fonts, stylesheets, scripts, or network assets.
- Include `<title>` and `<desc>` elements and keep text selectable.
- Include a compact legend when color, line style, or shape carries meaning. Do not rely on color alone.
- Label branch conditions on arrows and show every material decision branch. Every loop needs a finite exit condition; every node must reach a completion, stop, or unresolved endpoint.
- Attach evidence IDs or short source labels to claims. Mark inferred or proposed nodes explicitly.
- State below or beside the diagram what it proves and what it does not prove.
- Render or inspect the SVG before delivery. Visual correctness is part of artifact QA, but it is not engineering verification.

If the user needs a repository-native editable diagram and SVG is not required, Mermaid may be more maintainable. If SVG is requested or the artifact will be reused outside Markdown, deliver SVG rather than only Mermaid source.

## Validation Matrix

Use a validation matrix when several assumptions could fail independently:

| Claim or assumption | Evidence now | Smallest probe | Expected observation | Contrary observation | Route after result |
| --- | --- | --- | --- | --- | --- |

Test one hypothesis layer at a time. Prefer a read-only local sample before broad automation. Do not promote a successful sample beyond its stated coverage.

## Upstream Contribution Pack

Use this only when local research suggests a reusable outcome for `REVIT_MCP_study`. Follow [revit-mcp-study-contribution.md](revit-mcp-study-contribution.md) and include:

1. **Why it fits:** the repeatable problem and who benefits; distinguish a local success from broader evidence.
2. **Current rules checked:** official repository sources, check date or revision, and any maintainer exception.
3. **Related-work search:** overlapping Domain documents, Skills, Issues, Pull Requests, and Discussions; explain extension versus duplication.
4. **Public-safe evidence:** sanitized sources and reproduction, with private model, company, client, and credential material removed.
5. **Recommended target:** Issue, knowledge/Domain contribution, Skill contribution, Discussion, or no upstream action.
6. **Draft package:** suggested title and body, proposed files or scope, acceptance criteria, validation already performed, limitations, and explicit maintainer questions.
7. **Submission tutorial:** exact GitHub UI steps and, only when useful, optional Git/`gh` steps based on the current contribution guide.
8. **Authorization stop:** show what is prepared and stop before posting, commenting, pushing, or opening a Pull Request unless the user separately authorizes that external action.

The pack should make contribution easier without pretending the maintainer will accept it. If the official rules are unavailable or contradictory, prepare a question for maintainers rather than guessing the route.

## Final Artifact QA

Before delivery, check that:

- each artifact supports a named decision and owner;
- every recommendation is traceable to evidence or marked as a hypothesis;
- required inputs and identity keys are explicit;
- all material branches, exceptions, and partial failures have a route;
- human authority and mutation approval are visible rather than hidden in defaults;
- verification matches the claim level;
- the output is usable without rereading the full conversation.
