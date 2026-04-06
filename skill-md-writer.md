---
name: skill-md-writer
description: Designs and writes high-quality SKILL.md files for AI agent workflows. Use when the user asks to "create a skill", "write a SKILL.md", "make an agent skill", "build a Codex skill", "convert this workflow into a skill", "สร้าง skill", "เขียน SKILL.md", or "ทำสกิลให้หน่อย". Use for new skills or improving existing ones. Do not use for general coding tasks that are unrelated to agent skills.
---

# SKILL.md Writer

## Purpose
Create or improve a complete `SKILL.md` file that follows the Agent Skills pattern and is likely to trigger reliably.

Your goal is not just to write instructions. Your goal is to produce a skill that:
1. Has a precise activation description.
2. Encodes a reusable workflow.
3. Stays concise in the main file.
4. Pushes bulky detail into references or scripts when needed.

## Core principle
The most important part of a skill is the YAML frontmatter at the top.

The `description` must combine:
- what the skill does
- when it should be used
- concrete trigger phrases the user is likely to say
- clear boundaries for when it should not trigger

Use this pattern:

`[what the skill does] + [when to use it, with trigger phrases] + [optional boundary]`

## Output requirements
When writing a skill:
- The file must be named exactly `SKILL.md`.
- `name` must be lowercase kebab-case.
- Keep the main `SKILL.md` practical and easy to scan.
- Prefer instruction-first skills unless scripts are clearly necessary.
- If the workflow is large, move detailed criteria into `references/` and mention them from `SKILL.md`.
- If the workflow needs deterministic execution, propose helper scripts under `scripts/`.
- If the skill depends on an external MCP/tool integration, mention that clearly in prerequisites or metadata.

## Workflow

### Step 1: Understand the target workflow
Before writing, determine:
- What repeatable job this skill is for
- Who will use it
- What signals should activate it
- What inputs the skill expects
- What output or artifact it should produce
- Whether the workflow is instruction-only, script-backed, reference-heavy, or MCP-enhanced

If the user already gave enough detail, do not ask unnecessary follow-up questions. Infer the most likely workflow and proceed.

### Step 2: Define the skill type
Classify the skill into one of these patterns:

1. **Instruction-only**  
   Use for checklists, writing tasks, review procedures, or standard operating workflows.

2. **Reference-backed**  
   Use when detailed rubrics, style guides, compliance rules, or examples would bloat `SKILL.md`.

3. **Script-backed**  
   Use when a deterministic action is needed, such as validation, formatting, file generation, or automation.

4. **MCP-enhanced**  
   Use when the workflow depends on a connected external system such as GitHub, Linear, browser tools, design tools, or internal services.

### Step 3: Write strong frontmatter
Always draft the frontmatter first.

Use this template:

```yaml
---
name: skill-name
description: Briefly state what the skill does. Then state exactly when to use it with concrete trigger phrases. Add a boundary if needed so the skill does not activate too broadly.
---
```

Rules:
- Make the description specific, not generic.
- Include phrases users are likely to type verbatim.
- Cover both English and the user's working language when helpful.
- Avoid vague phrases like "helps with documents" or "improves code".
- Avoid overly broad descriptions that may cause false triggering.

### Step 4: Structure the body
Organize `SKILL.md` in this order when possible:

```md
# Skill Title

## Purpose
One short paragraph describing the outcome.

## When to use
Bullet points with concrete triggers.

## Inputs
What the skill expects.

## Workflow
Step-by-step instructions the agent should follow.

## Output
What the final deliverable should contain.

## Quality checks
Checklist for validating the result.

## Boundaries
What this skill should not do.
```

Adapt the headings when needed, but keep the flow practical and operational.

### Step 5: Write actionable instructions
Instructions should read like a runbook for another capable agent.

Use these principles:
- Start by gathering context from the repo, files, or user request.
- Prefer inspecting available evidence before asking questions.
- Tell the agent what to produce, not just what to think about.
- State ordering explicitly when sequence matters.
- Include validation steps before completion.
- Require the agent to avoid placeholders and empty sections.

### Step 6: Add supporting files only when justified
If the skill is becoming too large:
- move scoring rubrics, examples, long standards, or domain rules into `references/`
- move deterministic actions into `scripts/`
- keep the main file focused on orchestration and decision-making

When references are needed, mention them explicitly, for example:
- `Read references/review-checklist.md before finalizing feedback.`
- `Use references/style-guide.md when generating the final document.`

When scripts are needed, mention what they are for, for example:
- `Run scripts/validate.sh before writing the final answer.`
- `Use scripts/bootstrap.py to generate the initial scaffold.`

### Step 7: Include quality checks
Every skill should end with a compact validation checklist.

Use checks such as:
- [ ] The description clearly states what the skill does and when to use it.
- [ ] Trigger phrases are concrete and realistic.
- [ ] The workflow is step-by-step and executable.
- [ ] The output format is explicit.
- [ ] The skill is not broader than necessary.
- [ ] Large detail has been moved out of the main file when appropriate.

### Step 8: Provide the final deliverable cleanly
When the user asks for a skill, produce:
1. the final `SKILL.md` content
2. optional recommended folder structure if references/scripts are useful
3. a short note on how to install or place the skill only if relevant to the user's platform

Do not pad the result with theory unless the user asks for explanation.

## Skill-writing heuristics
Use these heuristics while drafting:
- Prefer a narrow skill over a broad one.
- One skill should correspond to one repeatable workflow.
- Good descriptions improve activation more than long instructions do.
- Put stable policy in the skill, but keep volatile project facts outside unless necessary.
- If the user gives examples of how they ask for tasks, convert those examples into trigger phrases.
- If the workflow produces files, say exactly which files should be created or updated.

## Boundaries
- Do not create vague frontmatter.
- Do not write a description that only says what the skill does without saying when to use it.
- Do not overload one skill with unrelated workflows.
- Do not add scripts unless they materially improve reliability.
- Do not assume a platform-specific folder path unless the user asked for a specific platform.

## Default final format
Unless the user requests something else, return the result in this order:
1. Skill name
2. Recommended folder tree
3. Final `SKILL.md`
4. Optional companion files
