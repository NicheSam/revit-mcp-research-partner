# Research Navigation for an Unclear Request

Read this reference when the user has a real concern but does not know the right technical question. Its purpose is to turn a vague request into a small, evidence-backed research move, not to make the user learn the system's vocabulary first.

## Start With the User's Situation

Restate the concern in this four-part form before choosing a solution:

```text
Observed symptom:
Desired outcome:
Smallest place to inspect:
What is not authorized yet:
```

If the user cannot supply a detail, inspect the available files, repository, Issue, model evidence, or existing workflow first. Ask at most two questions only when their answers change safety, ownership, or the next check.

## Pick the Research Path

| What the user may say | First thing to find out | First useful output | Do not do yet |
| --- | --- | --- | --- |
| “Something in the model looks wrong.” | Which items differ, and can they be identified again? | Read-only candidate table plus a short map | Change the model or assume the normal pattern is correct |
| “I know this workflow could be better, but I do not know what AI or tool to use.” | What work happens now, what change the user wants, and which capability is missing? | Capability conversion map plus one smallest reversible trial | Teach a catalogue of products or jump to a new Tool |
| “Can this be automated?” | Is there already a manual method, plugin, SOP, or interface that covers part of it? | Existing-capability map and the remaining gap | Propose a new tool because the word “Agent” was used |
| “This looks finished; can I use it?” | Which proof level exists: code, build, host run, readback, or matching-case coverage? | Evidence ladder with missing checks | Treat a PR, screenshot, or successful response as completion |
| “The screen can do it; can an API do it?” | Exact product/version and official API contract | Official-source check and a bounded capability answer | Guess an API or translate a UI action into an API claim |
| “Can we connect another system?” | What remains the same, what must be translated, and what is unsupported? | Capability/identity/unit boundary matrix | Rename objects and claim portability |
| “I have a large idea or a large PR.” | What is the smallest independently reviewable outcome? | Work slices with order, owner, and proof for each | Ask one reviewer to accept an entangled bundle |
| “I made a spec, but no one has acted on it.” | Has every supplied source and attachment actually been read? | Source coverage table and corrected research question | Repeatedly ask for information already present |

## Choose the Lightest Safe Depth

Choose depth by uncertainty, possible impact, and the evidence needed for the decision. Do not make every request pay the cost of the full research loop.

| Depth | Choose when | First-round output | Escalate when |
| --- | --- | --- | --- |
| **Fast** | The question is bounded and read-only, identities and sources are reliable, and no professional decision is being delegated | One narrow check, a direct answer, its evidence limit, and one next action or stop condition | The result depends on an unobserved state, conflicting source, changing identity, or broader claim |
| **Standard** | An existing workflow, habit, plugin, SOP, or failure record must be converted; rules or exceptions are not yet stable | A workflow/conversion table, the main uncertainty, and at most two decision-changing questions | Mutation, shared state, version-dependent behavior, or professional authority becomes material |
| **Strict** | Persistent change, shared or changing state, cross-version capability, large batch, irreversible consequence, or authority boundary can affect the outcome | Evidence ledger, safety and ownership gates, validation plan, stop conditions, and a reviewable artifact | Remain stopped until missing evidence, enforceable protection, or human authority is available |

Start with the lowest depth that can support the requested decision. Escalation is one-way for the current decision: discovering higher risk invalidates the shorter route, but a strict path may return to a smaller bounded question after the risky scope is removed.

## The Research Loop

1. **Find what already exists.** Search the smallest relevant source range before designing a replacement.
2. **Name the uncertainty.** Classify it as identity/state, observability, rule/exception, capability/version, shared ownership, responsibility, or evidence level. One round should reduce one main uncertainty.
3. **Choose a reversible check.** Prefer reading, comparison, preview, a small prototype, or documentation verification before a persistent change.
4. **Make the result reviewable.** Use a table, short SOP draft, evidence ladder, Issue draft, or SVG. A person must be able to reject the interpretation.
5. **Route or stop.** State the next owner, proof required, and condition that returns the work to research or human review.

Do not skip from step 1 to a proposed Tool. The value of the Skill is often discovering that the best next result is a clarified scope, a missing source, an existing capability, or a preserved negative conclusion.

## Capability Translation for a User Without a Technical Plan

Translate the work before naming a product:

| Current work | Desired change | Needed capability | Existing coverage | Gap or human decision | Smallest trial |
| --- | --- | --- | --- | --- | --- |
| What the person, plugin, document, or model does now | What should become easier, clearer, safer, or repeatable | observe / compare / explain / propose / execute / verify | Existing plugin, SOP, Gateway read, repository method, or official API | Missing interface, missing evidence, exception, authority, or unsafe state | One read-only sample, comparison, preview, draft, or disposable prototype |

Use capability words as a temporary bridge, not a glossary the user must learn. If the need is “understand why cases differ,” first test observation and comparison; do not assume execution is required. If an existing method covers the stable operation, preserve it and add Agent help only around evidence, explanation, exceptions, or handoff.

After the trial, route the learning based on evidence:

```text
local evidence only -> keep as local research or SOP draft
reusable and verified -> assess REVIT_MCP_study upstream fit
clear missing repository capability -> prepare an Issue-first contribution pack
professional or private decision -> keep human-owned and do not upstream
```

## Default Reply Shape

For a fast case, reply in ordinary language with:

1. **Answer or current finding** — tied to the narrow source or read-only observation.
2. **Evidence limit** — what the check does not prove.
3. **Next action or stop condition** — only if one is needed.

For a small unclear standard case, reply with:

1. **What I can check now** — named sources or a read-only observation.
2. **What this will tell us** — the decision it can change.
3. **What I need from you, if anything** — no more than two decision-changing questions.
4. **What you will receive next** — one concrete artifact and its limit.

For a strict or substantial case, attach the artifact and finish with the owner, verification, and stop condition from the output contract.

## Visual Map

Use [`assets/research-navigation-map.svg`](../assets/research-navigation-map.svg) when explaining this progression to a user or handing the research to another owner. It is a map of the research process, not proof that any case is complete.
