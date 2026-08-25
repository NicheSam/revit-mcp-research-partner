# Revit and MCP Boundaries

Apply these boundaries when interpreting evidence or proposing actions. They are decision gates, not general BIM instruction.

## Engineering and Responsibility

- Treat geometry detection as observation, not permission. A clash, intersection, route, or candidate does not authorize an opening, structural change, code decision, or cross-discipline commitment.
- Keep engineering intent, model operation, and professional approval separate. The Agent may organize evidence and expose uncertainty; the responsible human defines acceptable risk and approves exceptions.
- Preserve `review_required` when ambiguity cannot be eliminated. Do not convert uncertainty into a default value merely to continue automation.

## Read Before Mutation

Before proposing or performing a persistent model change, verify the relevant active context: document, view, level, selection or target identity, coordinate space and link transform, units, family/type, host and offset, and expected transaction scope. Verify only the fields relevant to the case, but stop if an unresolved field could change the result.

A mutation may proceed only after all of these are available and accepted:

1. **Preview:** a reviewable representation tied to stable candidate identities and intended changes.
2. **Rollback:** a defined transaction rollback, cancellation, or Revit Undo boundary; preview should not leave persistent model debris.
3. **Readback:** an independent query or inspection that checks the created/modified elements and engineering invariants, not just the command response.
4. **Human approval:** explicit authorization for the stated model, scope, and batch.

If any gate is missing, remain read-only and deliver analysis, a preview specification, a proposal, or a review packet.

## Evidence Claims

Keep these claims distinct:

```text
idea
!= source implementation
!= automated test
!= built artifact
!= deployment
!= live execution
!= independent readback
!= professional approval
```

- An Issue comment or closed Issue proves discussion or tracking state, not implementation or deployment.
- A commit proves repository history, not that the matching artifact was built, installed, loaded, or exercised.
- A passing test proves only its named scope, revision, fixtures, and environment.
- A screenshot proves visible state at a moment; without model, revision, artifact, and batch correlation it is not runtime provenance.
- API or tool success proves the request completed at its interface boundary, not that spatial, system, or engineering results are correct.
- Readback should be independent of the write response and tied to explicit acceptance criteria.

Never merge evidence from different models, revisions, sessions, or batches without labeling the join and its limitations.

## Professional Software API Evidence

When the case requires evaluating or implementing API capability for Revit, Autodesk products, MCP hosts, BIM tools, CAD tools, or other professional software, do not rely on agent memory or plausible API guesses.

- First identify the exact product, host, SDK, add-in target, and version from local files, manifests, loaded artifacts, logs, or user-provided evidence when available.
- Use official API references, SDK documentation, release notes, deprecation notes, official samples, or vendor-maintained source as primary evidence. Unofficial posts, examples, forum replies, and AI summaries may help locate issues but cannot be the primary source for capability claims.
- Record what the official source proves: signature, version support, threading or transaction requirements, host-context limits, side effects, failure behavior, and deprecation status when relevant.
- If official evidence cannot be reached or does not answer the question, mark the claim `officially_unverified`. Stop before implementation, tool proposal, model mutation, or public claim unless the user explicitly accepts the uncertainty.
- A successful API call is only interface evidence. It does not prove engineering correctness, deployment, live-model safety, or professional approval without the matching validation layers.

## Performance and Capability Claims

Do not claim an Agent is faster or more effective than a skilled Revit user without a comparable benchmark using the same task, model, starting state, success criteria, and failure accounting. It is acceptable to claim narrower observed benefits such as broader search, traceable evidence collection, visualization, translation, or exception localization when the case supports them.

## Authorization and Data Scope

- Inspect only sources in scope and preserve confidentiality labels and repository boundaries.
- Do not edit SC REVIT, Revit MCP, BIM Agent, live models, issues, releases, deployments, or company-internal material unless the user explicitly authorizes that specific mutation.
- A research request authorizes read-only inspection and recommendations, not implementation, issue creation, model modification, publication, or deployment.
- When the required evidence is inaccessible, report the missing layer and propose the smallest safe way to obtain it; do not invent model state or professional intent.
