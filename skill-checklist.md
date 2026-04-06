# Skill Quality Checklist

Use this checklist when reviewing a newly written skill.

## Trigger quality
- Does the `description` say both what the skill does and when to use it?
- Are trigger phrases realistic and specific?
- Is the skill narrow enough to avoid accidental triggering?
- Does the description include a boundary when the skill could otherwise be too broad?

## Instruction quality
- Does the main body describe a clear step-by-step workflow?
- Does it tell the agent what output to produce?
- Does it include validation before finishing?
- Does it avoid placeholder instructions and empty headings?

## Packaging quality
- Is `SKILL.md` concise enough to stay readable?
- Should detailed rules move into `references/`?
- Should any deterministic step move into `scripts/`?
- Are prerequisites or external dependencies stated clearly?

## Practicality
- Would another agent be able to execute this workflow without extra explanation?
- Does the skill reflect how users really phrase requests?
- Is the skill reusable across multiple similar tasks?
