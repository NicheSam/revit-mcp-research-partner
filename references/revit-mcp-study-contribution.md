# REVIT_MCP_study Contribution Handoff

Read this reference only when research produces a result that may be reusable by [`shuotao/REVIT_MCP_study`](https://github.com/shuotao/REVIT_MCP_study). The parent-project route is important, but it must not distort a local workflow into a public contribution before the evidence is ready.

## Recheck the Official State

Before recommending a target, inspect the current versions of:

- repository README and [`CONTRIBUTING.md`](https://github.com/shuotao/REVIT_MCP_study/blob/main/CONTRIBUTING.md);
- repository-level instructions such as `CLAUDE.md`, `CODEOWNERS`, Issue forms, and Pull Request templates when present;
- related `domain/` documents and Skills;
- open and closed Issues, Pull Requests, and relevant Discussions;
- a maintainer's explicit instruction or exception for this exact contribution, if one exists.

Record the URL plus check date or commit revision. Do not rely on this Skill's remembered snapshot as the current rule. If the sources cannot be checked, label the route `recheck_required` and stop at a draft or maintainer question.

## Eligibility Test

Recommend upstream contribution only when all applicable conditions pass:

1. **Repository fit:** the problem concerns a workflow, capability, defect, knowledge pattern, or orchestration that the project can reasonably own.
2. **Reusable scope:** the result is useful beyond one private model or company habit, and its coverage is stated honestly.
3. **Evidence maturity:** the claim is traceable and the validation matches the claim; a proposal is labelled as a proposal.
4. **No avoidable duplicate:** related Domain content, Skills, Issues, Pull Requests, and Discussions were checked.
5. **Public safety:** no client, company, model, credential, personal, licensed, or otherwise restricted material is exposed.
6. **Maintainable boundary:** the suggested change is reviewable, has an owner and test or validation path, and does not combine unrelated work.

If any condition fails, keep the result as local SOP, research memo, private Issue, or human-review material and state what would permit reassessment.

## Choose the Upstream Route

The current route must come from the freshly checked guide. As a working decision pattern—not a permanent repository rule—consider:

- **Verified reusable workflow or knowledge:** prepare the knowledge or Domain contribution currently allowed by the guide.
- **Reusable Agent coordination:** prepare a Skill contribution only if it has its own trigger, output, stop conditions, scenario tests, and fits existing repository tools.
- **Missing interface, defect, or core-code suggestion:** prepare an Issue first unless the current guide or maintainer evidence explicitly authorizes a code Pull Request.
- **Question, showcase, or early exploration:** use the Discussion or other community route currently named by the repository.
- **Private, local-only, disputed, or weakly tested result:** do not upstream yet.

An explicit maintainer exception overrides the default route only within the stated scope. Preserve its link and wording as evidence; do not generalize it to later work.

## Handoff Record

Produce this table before drafting:

| Field | Required content |
| --- | --- |
| Upstream fit | Reusable problem, intended users, and why the parent project can own it |
| Official rules checked | URLs, date or revision, relevant requirement, unresolved conflict |
| Related work | Domain/Skill/Issue/PR/Discussion links and duplicate or extension judgment |
| Evidence and limits | Public-safe sources, validation level, tested coverage, unproven claims |
| Suggested route | Issue / knowledge contribution / Skill / Discussion / no upstream action |
| Proposed scope | Smallest reviewable files or repository change; explicit exclusions |
| Maintainer decision | The smallest question or approval needed from maintainers |
| Authorization boundary | Draft only / user-authorized submission / user-authorized follow-up |

## Submission Tutorial

Tailor the steps to the current official guide and the chosen route.

### Issue or Discussion through GitHub

1. Open the current repository's **Issues** or **Discussions** page and search both open and closed records for the same problem.
2. Select the current template or category; do not bypass requested fields.
3. Use the prepared title and body. Include the use case, traceable evidence, expected result, validation, limits, and the exact maintainer question.
4. Remove private paths, model names, client data, logs with credentials, and unsupported completion claims.
5. Preview links and formatting. Stop before the final submit button unless the user explicitly authorized posting.

### Knowledge or Skill contribution through a fork

1. Read the current contribution guide and identify which paths an external contributor may change.
2. Fork the repository, create a narrowly named branch, and change only the allowed, reviewable files.
3. Follow current formatting and frontmatter requirements; update existing content instead of duplicating it when appropriate.
4. Run the repository's required tests or validation and record the exact revision and environment.
5. Compare the diff against the permitted scope; scan for secrets and private project data.
6. Draft the Pull Request with problem, decision, evidence, validation, limits, related work, and maintainer questions.
7. Stop before push or Pull Request creation unless the user explicitly authorized those external actions.

Optional Git or `gh` commands may be provided after the repository, branch, remote, allowed paths, and user authorization are confirmed. Do not present generic commands that may target the wrong fork or branch.

## Stop Conditions

Stop at a local artifact or maintainer question when:

- official contribution rules or current templates cannot be verified;
- related work has not been searched;
- the result duplicates existing work without a clear extension;
- evidence is only a private case, proposal, screenshot, test, or write response but the claim is broader;
- the change would touch paths external contributors are not currently allowed to modify;
- the material cannot be made public safely;
- the requested action is posting, commenting, pushing, or opening a Pull Request without explicit authorization.

The deliverable is a contribution-ready decision and package. It is not proof of acceptance, merge, deployment, live-model correctness, or professional approval.
