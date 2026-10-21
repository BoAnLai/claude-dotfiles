---
name: skill-template
description: This skill do nothing and should never be used automatically by claude or any ai agents. The purpose of this skill is to record some notes for Mike to check when manage other skills. 
---

# skill-template

## Structure for a skill

| Type | Name | Path | Note |
|---|---|---|---|
| directory | skills | `skills/` | |
| directory | skill-template | `skills/skill-template/` | |
| file | SKILL.md | `skills/skill-template/SKILL.md` | required:instructions in Markdown with YAML frontmatter |
| directory | scripts | `skills/skill-template/scripts/` | optional:Executable code |
| directory | references | `skills/skill-template/references/` | optional:Documentation |
| directory | assets | `skills/skill-template/assets/` | optional:Templates, fonts, image... |

## Three level for Progrssive Disclosure

1. First level (YAML frontmatter): Always loaded in Claude's system prompt. Provides just enough information for Claude to know when each skill should be used without loading all of it into context.
2. Second level (SKILL.md body): Loaded when Claude thinks the skill is relevant to the current task. Contains the full instructions and guidance.
3. Third level (Linked files): Additional files bundled within the skill directory that Claude can choose to navigate and discover only as needed.

## Categories for skill use cases 

1. Document and asset creation
2. Workflow automation
3. MCP enhancement

## define success criteria

1. skill trigger on 90% relevent queries: run 10-20 test query that should trigger your skill.
2. compare task with and without skill: count tool call and token consumed.
3. needing correction?
4. complete as expected?
5. consistent result?

