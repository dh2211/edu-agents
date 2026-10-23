# Write a new skill

A skill is a folder with a `SKILL.md` file. This page explains how to add one that passes the validator and fits the kit.

## Decide whether it should be a skill

Add a skill when teachers need a distinct document or procedure the current skills don't produce. If the request is a variation of an existing skill ("a worksheet with a word search"), improve that skill instead. Fewer, better skills are easier for the agent to choose between.

## Create the folder

```bash
mkdir skills/edu-lab-safety-briefing
```

The folder name is the skill name. It must start with `edu-` and use only lowercase letters, digits, and single hyphens, at most 64 characters. The prefix keeps our skills from replacing a teacher's own skills with the same name when both sit in a shared folder. Agent file names in `agents/` start with `edu-` for the same reason.

## Write the frontmatter

`SKILL.md` must start on line 1 with YAML frontmatter:

```markdown
---
name: edu-lab-safety-briefing
description: Writes a pre-lab safety briefing and student safety contract for a specific science lab. Use when a teacher asks for lab safety rules, a safety quiz, or a pre-lab talk.
license: MIT
---
```

- `name` must match the folder name.
- Put `description` in double quotes. Descriptions often contain a colon, and an unquoted colon makes the YAML invalid, so agents load the skill without its description.
- `description` must be 50 to 1,024 characters. Say what the skill makes, then "Use when" with the words a teacher would type. The agent picks skills by this text alone.

Use only the fields from the [Agent Skills specification](https://agentskills.io/specification). Tool-specific fields work in one agent and are ignored or rejected in another.

## Write the body

Follow the shape of the existing skills:

1. A one-line purpose.
2. **Ask first.** The 3 or 4 inputs the skill needs. The agent asks only for missing ones.
3. The steps, as numbered commands. Name the teaching practice behind them (backward design, gradual release, UDL, DOK) and say what it means in one line.
4. **Output.** The exact sections and order of the result.
5. **Guardrails.** Copy the section from any existing skill, word for word. The validator fails without it.

Keep `SKILL.md` under 500 lines. Move long reference material into `references/` and link it with a relative path, like `edu-assessment-builder` does with [references/item-writing.md](../skills/edu-assessment-builder/references/item-writing.md). Keep links one level deep.

To point at another skill, write its name in backticks followed by "skill": "use the `edu-rubric-builder` skill". Don't link to another skill's file. Teachers can install one skill without the others, and a link would break. The validator checks that every name written this way exists.

## Write for teachers and for the agent

- Plain English, short sentences, no jargon a new teacher wouldn't know.
- Write instructions the agent can follow without guessing: "Write 1 to 3 objectives", not "write a few objectives".
- Don't claim research findings without a source. Name the framework or author if you rely on one.
- No em dashes. The validator rejects them.

## Add an example

Produce a real output by following your skill for one grade and subject, and add it to `examples/`. If you can't produce a good example by following the instructions, the instructions need work.

## Check it

```bash
npm run validate
npm test
```

Both run in CI on every pull request.
