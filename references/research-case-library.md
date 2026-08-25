# Research Case Library

Read this reference after selecting a research path in [research-navigation.md](research-navigation.md), when a historical pattern can prevent rediscovery of the same mistake. This is a curated decision library, not a feature catalog. The cases were selected from public `REVIT_MCP_study` Issues and Pull Requests on 2026-08-25; linked status, runtime behavior, and product capabilities may change after that date.

## How to Use the Library

For the closest case, take only these four things:

1. the misconception that slowed the work;
2. the evidence that corrected it;
3. the smallest useful output;
4. the condition that stopped overclaiming or overbuilding.

Do not copy a case's professional vocabulary, numeric rule, API conclusion, or repository state into a new case without fresh evidence.

## 1. A Candidate Is Not Permission

**Situation:** People wanted a manual locating process to become automation.

**Misconception:** Finding a likely item was treated as enough reason to create or change something.

**Correction:** The first version was read-only: stable identity, suggested result, `candidate` / `review_required` states, warnings, and explicit non-goals came before implementation.

**Use when:** the user says “can you fix these?” but the interpretation has not been reviewed.

**Give the user:** a candidate table and a human decision point.

**Evidence:** [Issue #99](https://github.com/shuotao/REVIT_MCP_study/issues/99), [Issue #112](https://github.com/shuotao/REVIT_MCP_study/issues/112), [PR #124](https://github.com/shuotao/REVIT_MCP_study/pull/124). PR #124 was open when selected; do not claim merge or deployment from this card.

## 2. A Preview That Does Not Match Must Stop the Write

**Situation:** A human could visually adjust a proposed placement after an offset or transformation problem.

**Misconception:** An Agent could imitate that visual correction without a reliable basis.

**Correction:** Work was separated into discovery, preview, authorized creation, and independent readback. If the preview or basis was unreliable, creation stopped.

**Use when:** a proposed change depends on position, orientation, type, host, or another state that may change between review and execution.

**Give the user:** preview contract, approval question, and readback checklist.

**Evidence:** [Issue #100](https://github.com/shuotao/REVIT_MCP_study/issues/100), [Issue #113](https://github.com/shuotao/REVIT_MCP_study/issues/113), [PR #115](https://github.com/shuotao/REVIT_MCP_study/pull/115). PR #115 was open when selected; its existence does not prove all negative paths passed.

## 3. A Rejected Mechanism Can Still Advance the Work

**Situation:** A requested automation depended on controlling another UI path.

**Misconception:** “Not suitable for the core” meant the underlying need should disappear.

**Correction:** The project recorded the exact mechanism that was rejected, why it was fragile, a safer alternative, and the condition for reconsidering it.

**Use when:** a route is blocked by an external product, unsupported behavior, fragile integration, or missing authority.

**Give the user:** boundary note, alternative path, and re-entry condition.

**Evidence:** [Issue #110](https://github.com/shuotao/REVIT_MCP_study/issues/110).

## 4. A Visible Tool Can Still Be Disconnected From the Work

**Situation:** Tool registration existed, but the host-side path that performed the work was absent.

**Misconception:** A visible command or successful build proved the feature was usable.

**Correction:** The work was checked from listing through connection, build, host execution, independent readback, and matching-case coverage.

**Use when:** someone cites a commit, PR, test, or screenshot as proof of readiness.

**Give the user:** evidence ladder with named gaps.

**Evidence:** [Issue #111](https://github.com/shuotao/REVIT_MCP_study/issues/111), [PR #101](https://github.com/shuotao/REVIT_MCP_study/pull/101). PR #101 explicitly separated build checks from pending host runtime checks.

## 5. A Knowledge File Is Not a Knowledge System Until It Is Reachable

**Situation:** A reference document existed but the relevant workflows did not reliably load it.

**Misconception:** Saving a file in a repository made it available to the right Skill.

**Correction:** The issue traced trigger paths, direct references, reverse references, freshness, and deliberately left broad update automation out of the first scope.

**Use when:** the user says “we have collected all this material; why is it not helping?”

**Give the user:** source coverage table: source, invoked by, decision it changes, freshness, and known gap.

**Evidence:** [Issue #41](https://github.com/shuotao/REVIT_MCP_study/issues/41), [PR #40](https://github.com/shuotao/REVIT_MCP_study/pull/40). The case also shows that an unrelated large PR can prevent an otherwise valid correction from being merged as a bundle.

## 6. Read the Supplied Artifact Before Asking for Its Answer

**Situation:** A proposal contained an attachment whose decisive details were not read; follow-up questions repeated information already supplied.

**Misconception:** A title or a short description represented the full proposal.

**Correction:** Reading the attachment changed the problem from a guessed technical feature to a distinct, practical audit workflow. Existing checks and the proposed workflow were complementary rather than duplicates.

**Use when:** a user has supplied a document, model extract, log, or prototype but the request still sounds underspecified.

**Give the user:** source coverage table and a corrected research question before asking a new question.

**Evidence:** [Issue #62](https://github.com/shuotao/REVIT_MCP_study/issues/62).

## 7. Split Work by Reviewable Outcome, Not by File Count

**Situation:** One contribution combined many unrelated behavior chains and had become difficult to review or reconcile.

**Misconception:** A single large change was more efficient because all work arrived together.

**Correction:** The work was divided into independently reviewable chains, each with a dependency order. Later recovery compared a preserved snapshot with current main, retained authorship, repaired a missing connection, and kept remaining runtime proof explicit.

**Use when:** a research result is turning into a large Issue, PR, or multi-step implementation plan.

**Give the user:** one row per work slice: outcome, dependency, owner, acceptance evidence, and what does not move with that slice.

**Evidence:** [Issue #56](https://github.com/shuotao/REVIT_MCP_study/issues/56), [PR #102](https://github.com/shuotao/REVIT_MCP_study/pull/102).

## 8. “The UI Can Do It” Is Not an API Contract

**Situation:** A manual UI configuration suggested that a precise automation should be possible.

**Misconception:** UI capability implied a public, supported API with the same granularity.

**Correction:** The case checked API availability by exact version and recorded the negative result, an inadequate broad alternative, and a specific re-check trigger for future versions.

**Use when:** the user asks whether a UI action can be automated through an API.

**Give the user:** official documentation/API evidence check, capability boundary, and reconsideration trigger. The current case's conclusion must not be reused without checking the current product version and official source.

**Evidence:** [Issue #72](https://github.com/shuotao/REVIT_MCP_study/issues/72).

## 9. Portability Requires a Fresh Contract, Not a Vocabulary Swap

**Situation:** A workflow was proposed for another BIM host while preserving the existing host as default.

**Misconception:** equivalent-looking names meant the workflow was portable.

**Correction:** The work classified what could be shared, what needed an adapter, and what remained host-specific. It preserved identity and unit boundaries, required runtime discovery, limited early pilots, and corrected conclusions when a wrapper version—not the host—caused an observed limitation.

**Use when:** connecting another application, version, backend, or server to an established workflow.

**Give the user:** portability matrix, one read-only pilot, version/runtime evidence record with expiry, and explicit unsupported steps.

**Evidence:** [Issue #98](https://github.com/shuotao/REVIT_MCP_study/issues/98), [PR #122](https://github.com/shuotao/REVIT_MCP_study/pull/122), [PR #123](https://github.com/shuotao/REVIT_MCP_study/pull/123). PRs #122 and #123 were open when selected; they are evidence records and proposals, not proof of complete host support.

## Case Selection Index

| If the current uncertainty is about… | Start with |
| --- | --- |
| candidate identity, review, or mutation | 1 or 2 |
| rejected integration or public API boundary | 3 or 8 |
| implementation/completion claim | 4 |
| unused research material or unread attachment | 5 or 6 |
| large handoff or contribution | 7 |
| another host, version, or backend | 9 |
