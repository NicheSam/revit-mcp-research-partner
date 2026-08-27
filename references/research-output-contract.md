# Research Output Contract

Use this contract at the depth required by the research route. A fast round may compress the contract to a finding, evidence limit, and next action or stop condition. A standard round should expose the workflow conversion and main uncertainty. A strict or substantial round should use the full contract. Shorter output must not hide absent evidence, stale state, or approval gates.

## Choose Output Depth

| Depth | Minimum visible output |
| --- | --- |
| **Fast** | Narrow finding; source or read-only observation; what it does not prove; next action or stop condition if needed |
| **Standard** | Research question; existing-workflow or source map; rule/judgment split; main evidence gap; primary route; smallest useful artifact; at most two decision-changing questions |
| **Strict** | Full evidence ledger; ownership and safety gates; environment/version contract when relevant; artifact manifest; validation; stop conditions; next human decision |

If a fast or standard check reveals higher risk or insufficient observability, reclassify the current decision before continuing. Do not expand a short answer merely to reproduce headings.

## 1. Research Question and Scope

- State the decision being investigated, not merely the requested feature.
- Name the in-scope workflow, model/document/view or repository when known.
- State what is not authorized or not being claimed.

## 2. Known Evidence

Maintain a compact evidence ledger:

| Evidence | Source and batch/date | Level | What it proves | What it does not prove |
| --- | --- | --- | --- | --- |

Use one or more explicit levels rather than collapsing them into “done”:

- **Idea:** hypothesis, request, intended design, or untested explanation.
- **Recorded source:** document, drawing, issue, failure record, model observation, or other traceable raw input.
- **Source implementation:** code or configuration exists in an identified revision.
- **Automated test:** a named test passed against a stated revision and environment.
- **Built artifact:** a specific artifact was produced; this does not prove it was loaded.
- **Deployment:** a specific artifact was installed or published to a stated target.
- **Live execution:** the intended host/model ran the operation in an identified batch.
- **Independent readback:** the result was queried or inspected independently of the write response and checked against the engineering success criteria.
- **Professional approval:** the responsible person or discipline accepted the result within a stated scope.

Keep different revisions, models, sessions, screenshots, and batches separate. An item may support multiple levels only when the traceability is explicit.

Do not assume the organization already has a clean knowledge base. When inputs are fragmented or informal, preserve their status before extracting rules:

| Input statement | Source | Status | Conflict or gap | Next treatment |
| --- | --- | --- | --- | --- |
|  | raw record / observed practice / document / implementation / model observation | verified fact / unverified inference / disputed rule / decision needed |  | retain / verify / compare / ask owner |

An informal habit can be valid recorded evidence without being a validated rule. Retrieval or indexing may help at scale, but it is not a prerequisite for beginning the research.

When API capability or implementation behavior is part of the claim, add the official source check:

- Product/API/version identified:
- Official source consulted:
- Confirmed contract:
- Unsupported or `officially_unverified` claim:
- Effect on routing or stop condition:

## 3. Workflow Decomposition

Classify the decisive findings:

| Finding | Class | Evidence | Confidence or gap | Owner |
| --- | --- | --- | --- | --- |
|  | engineering rule / contextual judgment / deterministic operation / model side effect / cross-discipline responsibility |  |  | human / Agent / plugin / unresolved |

When a failure drove the learning, summarize it as:

```text
Problem:
Misjudgment:
Correction:
Learning:
```

When the user begins with an improvement idea rather than a technical plan, add a capability conversion map:

| Current work and pain | Desired change | Needed capability | Existing method or tool | Remaining gap or human decision | Smallest reversible trial |
| --- | --- | --- | --- | --- | --- |

Use `observe`, `compare`, `explain`, `propose`, `execute`, and `verify` only as decision aids. Do not fill the table with product names before the capability and evidence gap are understood. Separate “the Agent can explain a possible path” from “a tool or API can enforce or execute it.”

## 4. Principle Checks

Apply only the checks that change the decision. Do not turn these into a glossary or a domain-term inventory.

| Check | Decision question |
| --- | --- |
| Falsifiable representation | Can the responsible human inspect the Agent's interpretation and reject it before execution? |
| State and identity consistency | Are the candidate identity, reviewed plan, execution input, and readback target the same batch and state? |
| Hypothesis isolation | Has the research avoided one correction masking a different root cause? |
| Local versus global evidence | Is the claim limited to the tested sample, or is there coverage for wider automation? |
| Preview side effects | Does the review mechanism avoid persistent model pollution unless explicitly accepted? |
| Same-run provenance | Are response, raw detail, transaction result, and readback tied to the same run when used together? |
| Human authority | Is any decision still owned by a responsible person or discipline rather than the Agent, plugin, or issue tracker? |
| Observable-state sufficiency | Does the evidence expose the state that could overturn the conclusion, or is a property, log, or screenshot standing in for it? |
| Guarantee level | Is a process requirement being confused with a tool promise, runtime enforcement, or observed result? |
| Shared-state validity | Is the reviewed identity, ownership, and state still current, and are conflicts and recovery defined? |

## 5. Key Judgment and Routing

- Name the primary target: plugin, Domain SOP, Skill or MCP workflow, MCP Tool proposal, GitHub Issue, research memo, or human review.
- State the decision criteria that support it.
- Name any dependent follow-up target and why it is not the primary target.
- If no route is defensible, state the evidence needed to choose.
- If another skill is needed, use the handoff contract in [routing-targets.md](routing-targets.md) and bring the result back to this evidence ledger before making a final route claim.

If the result may be useful to `REVIT_MCP_study`, add an upstream-fit record using [revit-mcp-study-contribution.md](revit-mcp-study-contribution.md):

| Upstream suitability | Suggested route | Official rules checked | Related existing work | Public-safe evidence | Missing proof | Submission boundary |
| --- | --- | --- | --- | --- | --- | --- |

Record the official source URL and check date or revision. Mark the result `recheck_required` if the current contribution guide, repository instructions, templates, or related work were not inspected in this research round. A draft is not a submitted Issue or Pull Request.

## 6. Smallest Viable Outcome

Define the smallest artifact that reduces uncertainty without assuming permission for broader implementation. Examples include a scoped SOP rule, a read-only probe, a preview schema, a reproducible failure note, a Tool proposal with input/output contract, or a review packet.

Include:

- intended user or owner;
- inputs and outputs;
- assumptions and exclusions;
- acceptance evidence;
- rollback or recovery expectation if mutation is later proposed.

For substantial research, do not leave this as a prose suggestion. Produce at least one usable artifact following [practical-deliverables.md](practical-deliverables.md), and list it in a deliverable manifest:

| Artifact | User or owner | Decision it supports | Evidence IDs used | Status |
| --- | --- | --- | --- | --- |

Also maintain an action register. Recommendations without an owner, prerequisite, verification, or stopping condition are incomplete:

| Priority | Exact next action | Owner | Prerequisite | Expected result | Verification | Stop condition |
| --- | --- | --- | --- | --- | --- | --- |

When the case comes from Issue, PR, maintainer discussion, an existing plugin, or a failure record, state which plain-language mode from [case-based-work-modes.md](case-based-work-modes.md) was used and why. Keep the user-facing summary in ordinary language; put technical identifiers in the evidence ledger, handoff, or validation table where they are needed.

## 7. Validation Method

Specify checks at the levels actually required for the claim. Prefer observable invariants such as stable element identity, coordinate/unit agreement, candidate counts, no unintended persistent elements after preview, transaction outcome, connector/system state, and independent model readback.

Do not substitute wording checks, screenshots, API success, or a passing unit test for the engineering result they cannot prove.

Validate the artifact itself as well as the underlying claim. A workflow or context diagram must have complete decision branches, reachable stop and completion states, explicit human gates, and labels that distinguish evidence, inference, proposed action, and verified result. An SVG must render as a standalone file and remain readable at its intended size; successful rendering does not validate the workflow facts.

For skill behavior reviews, use scenario families rather than keyword checks:

- a general Revit question should not trigger this research workflow;
- a bounded read-only question with reliable evidence should take the fast path instead of producing the full contract;
- a broad workflow research question should stay in this skill until a bounded subtask appears;
- fragmented documents and oral practices should be preserved as raw records, facts, inferences, conflicts, and human decisions rather than rejected for lacking a knowledge base;
- a conclusion that depends on an unobserved state should request the smallest read-only probe rather than infer from adjacent properties;
- an API capability question should require official product/version documentation and stop when unavailable;
- a multi-version claim should compare the requested versions, while a single-version claim should not create an unnecessary compatibility catalog;
- a proposed model mutation without preview, rollback, readback, or human approval should stop before execution;
- a mutation in shared or changing state should stop when ownership, writability, conflict impact, or recovery is unresolved;
- a successful sample should remain sample-scoped until wider coverage is evidenced;
- an implementation request should not inherit research authorization for deployment, issue creation, or model mutation.
- a vague improvement idea should receive a capability conversion map and smallest trial, not a catalogue of AI products;
- a verified reusable workflow should trigger an upstream-fit check, while private, local-only, or unverified material should not be pushed upstream;
- an upstream recommendation should be based on freshly checked official contribution rules and related work, not a memorized route;
- preparing an upstream draft or tutorial should stop before external submission unless the user separately authorizes it.

## 8. Stop Conditions and Human Decision

List conditions that require refusal, pause, rollback, or handoff. End with the smallest decision the responsible human must make next. Typical stop conditions include:

- active document, view, level, selection, link transform, unit, host, or identity is unresolved;
- the state needed to support the conclusion cannot be observed with the available evidence;
- preview differs from the expected geometry or creates persistent artifacts;
- rollback or independent readback is unavailable;
- ownership, writability, concurrent change impact, or conflict recovery is unresolved;
- source evidence conflicts or belongs to different batches;
- official API evidence is unavailable for a capability or implementation claim;
- confidence is below the stated threshold;
- structural, regulatory, contractual, or professional approval is required;
- the requested action exceeds the user's explicit authorization.
