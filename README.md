# Revit MCP Research Partner

A Codex Skill for researching real Revit, MCP, and BIM workflow cases before deciding what should be built, documented, escalated, or reviewed by a person.

It is a research and routing layer. It does not automatically create MCP tools, replace professional judgement, or authorize changes to a model.

## What it helps with

- Turn a vague real-world case into a clear research question and small next step.
- Separate evidence, engineering rules, context-dependent judgement, model side effects, and professional responsibility.
- Produce practical outputs such as a workflow map, SOP outline, evidence table, handoff brief, validation plan, or stop condition.
- Route the result to the appropriate destination: plugin, Domain SOP, Skill or MCP workflow, MCP Tool proposal, GitHub Issue, research memo, or human review.
- Use official product documentation when evaluating or implementing professional-software API capabilities.

## Intended use

Use it when a Revit/MCP/BIM workflow is unclear, has failed before, or needs a defensible recommendation before implementation. It is deliberately not for general Revit questions, generic presentations, or automatically turning every request into a tool.

## Safety boundary

The Skill requires preview, rollback planning, readback, and human approval before model mutation. It keeps the following evidence levels separate: idea, source code, test, deployed artifact, real-host execution, readback, and professional sign-off.

## Structure

```text
SKILL.md                         Entry workflow and routing guidance
agents/openai.yaml               Codex Skill metadata
references/                      Output contract, boundaries, routing, deliverables, and case modes
```

## Installation

Copy this folder to your Codex skills directory, for example:

```text
%USERPROFILE%\\.codex\\skills\\revit-mcp-research-partner
```

Restart or refresh Codex if required by your local installation.

## Status

Baseline public source. The Skill instructions have structure and reference-link checks; live Revit/MCP model behavior remains case-specific and requires its own evidence.

## License

No license has been selected for this repository yet. Do not assume reuse rights beyond the repository owner's stated terms.
