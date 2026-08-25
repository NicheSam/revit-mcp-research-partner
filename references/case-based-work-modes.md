# Case-Based Work Modes

Read this reference when an Issue, Pull Request, maintainer discussion, existing plugin workflow, or failure record is part of the evidence. Choose one mode for the current round. These are ways to make research useful, not separate Skills or automatic permission to change a repository or model.

## 1. Turn the Case Into a Clear Workflow

Use when a real example shows useful work, a confusing result, or a repeated manual process, but people have not yet agreed what a safe first version should do.

Produce:

- a short story: what happened, what was first assumed, what evidence changed the plan, and what was learned;
- a plain-language workflow: what to check first, what produces a candidate, what needs review, what stops, and what happens next;
- a small list of unanswered decisions for the responsible person;
- one reviewable artifact, normally a workflow draft, action table, or SVG diagram.

Do not move on when the first version has no clear non-goals, the result cannot be traced back to its source, or a person cannot tell which cases need review.

## 2. Prepare Work for the Next Owner

Use when the workflow is clear enough that a person, existing specialist Skill, or repository owner can take one bounded next task.

Produce a handoff that says:

- the one task to do next, in ordinary language;
- the sources already checked and what each actually shows;
- the exact input and result that must stay consistent from review to completion;
- what is deliberately outside this task;
- how the next owner will show that the task worked;
- what must stop the work and return it to research or human review.

Name files, versions, fields, API details, or test commands only when the next owner needs them. Do not turn a handoff into permission for deployment, public comments, or model changes.

## 3. Choose a Boundary and an Alternative Path

Use when the requested mechanism is unsafe, unavailable, too fragile, owned by another product, or needs authority that the workflow does not have.

Produce:

- the precise part that should not continue, rather than rejecting the whole underlying need;
- the evidence and practical reason for stopping;
- a smaller or safer alternative that still helps the user move forward;
- what remains a human decision;
- the condition under which the original idea could be reconsidered;
- the place where this boundary should be preserved for future work.

Do not hide a boundary inside a default value, unsupported claim, or vague “not supported” sentence. A closed or rejected Issue can still yield a reusable decision note.

## 4. Check Honestly How Far the Work Has Reached

Use when a feature is said to exist, an Issue is closed, a Pull Request is open, or tests have passed and someone needs to know what that actually means.

Use this plain-language progress table:

| Checkpoint | Question | Evidence needed | What passing does not prove |
| --- | --- | --- | --- |
| Listed | Can the user or Agent find the promised action? | Current list, page, or configuration | The action can really complete the work |
| Connected | Does the visible action reach the part that performs the work? | Matching source paths or a bounded call | The result is correct in a real case |
| Built | Does the relevant version build or pass its defined checks? | Named revision and environment | It is installed, loaded, or used successfully |
| Tried in the real host | Did the intended application run the action? | Host, model or document, batch, inputs, and response | The result is correct for all cases |
| Checked independently | Was the result read back against the intended condition? | Separate query or inspection tied to the same run | Professional approval or broad coverage |
| Checked in a matching case | Did a representative real case exercise the important rule and failure paths? | Coverage note and remaining gaps | Every future project is covered |

If a checkpoint is missing, say “not yet checked” rather than carrying forward a stronger claim from an earlier checkpoint.

## Choosing Among the Modes

| If the current question is mainly… | Use this mode |
| --- | --- |
| “What should this real example become?” | Turn the case into a clear workflow |
| “What can the next person do without rediscovering everything?” | Prepare work for the next owner |
| “Should we stop this route, and what can we do instead?” | Choose a boundary and an alternative path |
| “Is this really finished, or only partly proven?” | Check honestly how far the work has reached |

One case may use more than one mode over time, but choose the smallest one that changes the next decision now.
