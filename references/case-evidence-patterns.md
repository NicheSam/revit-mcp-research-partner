# Case Evidence Patterns

Read this reference when a real workflow needs a practical recommendation, especially when the evidence includes an existing plugin, an Issue or Pull Request, a failed preview, or a claim that a feature is already complete. These patterns are distilled from selected public interactions in `REVIT_MCP_study`; they are not claims that the linked changes are merged, deployed, or professionally approved.

## Evidence Basis and Limit

| Pattern | Public evidence | What this source supports | What it does not support |
| --- | --- | --- | --- |
| Review candidates before automation | [Issue #99](https://github.com/shuotao/REVIT_MCP_study/issues/99), [Issue #112](https://github.com/shuotao/REVIT_MCP_study/issues/112), [PR #124](https://github.com/shuotao/REVIT_MCP_study/pull/124) | A read-only, review-first first version; stable identity and explicit review states | That PR #124 is merged, deployed, or valid in every model |
| Stop writing when preview is not trustworthy | [Issue #100](https://github.com/shuotao/REVIT_MCP_study/issues/100), [Issue #113](https://github.com/shuotao/REVIT_MCP_study/issues/113), [PR #115](https://github.com/shuotao/REVIT_MCP_study/pull/115) | Separating discovery, preview, authorized write, and later check; preserving unresolved transform uncertainty | That all failure paths have been tested in the real host |
| Preserve a rejected route as a useful decision | [Issue #110](https://github.com/shuotao/REVIT_MCP_study/issues/110) | Rejecting one fragile mechanism while recording an alternative and a re-entry condition | That the original user need no longer exists |
| Check the whole path, not only the visible command | [Issue #111](https://github.com/shuotao/REVIT_MCP_study/issues/111) | Separating discoverability, connection, build, host execution, independent check, and matching-case coverage | That a successful build or response proves real-case correctness |

## Pattern 1: Make a Reviewable Candidate Before Taking Action

Use when the user says something like “this group looks wrong,” “can we automate this,” or “can MCP fix it?” but the case has not yet been bounded.

1. Locate the existing rule or manual method. Do not recreate a second method merely because it is easier to explain.
2. Return a read-only candidate list with stable identity, source, suggested action, warning, and one of `candidate`, `review_required`, or `blocked`.
3. State what the first version deliberately will not do.
4. Ask the responsible person to review only the cases that need a judgement.

**Minimum deliverable:** candidate table plus a small workflow map.

**Stop when:** a candidate cannot be traced to its source, the first version has no non-goals, or review cannot distinguish safe cases from uncertain cases.

## Pattern 2: A Preview Is a Gate, Not a Cosmetic Step

Use when the intended result depends on positions, transformations, host relationships, types, or another state that can become stale before execution.

1. Discover items and return names that people can recognize plus identities that the system can find again.
2. Preview the exact proposed result and the assumptions used to produce it.
3. If preview is inconsistent, uncertain, or no longer matches the current state, stop before write. Do not imitate a human's visual correction by guessing.
4. If approved, repeat the critical lookup at execution time and reject stale or changed candidates.
5. Independently read back the result using the same identities.

**Minimum deliverable:** preview contract, approval question, and readback checklist.

**Stop when:** the coordinate or identity basis is unknown, the preview differs from the intended result, rollback is undefined, or an approval is missing.

## Pattern 3: Reject the Mechanism, Keep the Underlying Need

Use when a requested route depends on a fragile integration, an unavailable host capability, unclear authority, or an interface that cannot be verified.

1. Say precisely which mechanism stops and why.
2. Keep the user's underlying goal visible.
3. Offer one smaller path that can be checked safely, such as extracting the needed logic, creating a read-only report, or recording a bounded Issue.
4. Record the condition that would justify reconsidering the original route.

**Minimum deliverable:** boundary note with alternative path and re-entry condition.

**Stop when:** the explanation only says “not supported,” hides the limitation in a default, or treats a rejected mechanism as proof the user need is invalid.

## Pattern 4: Report Progress as a Ladder, Not “Done”

Use when a user points to a commit, Issue, PR, screenshot, build, or successful command and asks whether the work is complete.

| Stage | Plain question | Required evidence | Do not conclude yet |
| --- | --- | --- | --- |
| Found | Can the action be located? | Current source, configuration, or visible list | It reaches the actual work |
| Connected | Does it reach the working part? | Bounded call path or matching source | The result is correct |
| Built | Did this revision pass its defined check? | Revision and named environment | It is installed or used |
| Run in the host | Did the intended application run it? | Host, input, model/document, batch, response | It is correct for representative cases |
| Checked separately | Was the outcome independently read back? | Separate inspection tied to the same run | It has professional acceptance |
| Covered by a matching case | Did the critical rule and failure path run on a representative case? | Coverage note and known gaps | Future cases are all covered |

**Minimum deliverable:** one-row-per-claim evidence ladder with explicit gaps.

**Stop when:** two stages are being treated as one, or sources from different revisions, models, or runs are combined without a traceable join.

## Choose a Concrete Output

| User need | First useful output | Use the pattern |
| --- | --- | --- |
| “I do not know how to describe this problem.” | Symptom-to-workflow map and one read-only check | 1 |
| “Can it be fixed automatically?” | Preview/approval/readback plan | 2 |
| “Can we force this existing UI or external tool to do it?” | Boundary note and safe alternative | 3 |
| “The PR is open and tests pass. Is it ready?” | Evidence ladder and remaining gaps | 4 |

## Visual Evidence Assets

- Use [`assets/research-routing-map.svg`](../assets/research-routing-map.svg) when explaining how evidence becomes a review gate and routed outcome.
- Use [`assets/issue-pr-evidence-workflow.svg`](../assets/issue-pr-evidence-workflow.svg) when explaining how case evidence, SOP, implementation, and progress checks relate.

Adapt labels, evidence IDs, and owners to the current case. State under the diagram what it proves and what it does not prove.
