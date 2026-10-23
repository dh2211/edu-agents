# Why the kit uses Agent Skills

This page explains why edu-agents ships as Agent Skills folders instead of prompts, a plugin for one tool, or an app.

## What a teacher needs from the format

A teacher should be able to read every instruction the agent follows, change it, and use it in whichever AI tool their school allows. A department should be able to keep its own copy in a shared folder. Nothing should need a server, an account, or code.

## Why Agent Skills fits

An Agent Skill is a folder with a `SKILL.md` file: YAML frontmatter with a `name` and a `description`, then Markdown instructions. The [specification](https://agentskills.io/specification) is short and open.

Claude Code, Codex, Cursor, Grok, and OpenCode all document loading this layout ([install.md](install.md) links each page). So one folder works in all five tools.

The agent sees only each skill's name and description until a request matches, then loads the full instructions. Eleven skills cost little context when they're idle, so a teacher can install all of them.

Markdown is the whole format. A teacher with no coding background can open `edu-rubric-builder/SKILL.md`, see why the rubric has four levels, and change it to five.

## What we gave up

- **Tool-specific features.** Claude Code can run a skill in a subagent or inject shell output. Cursor can scope a skill to file paths. We use only the fields in the specification, so every tool reads the same file the same way.
- **A guided app.** A web app could walk a teacher through forms. Skills rely on the agent to ask for missing details, and quality depends on the model behind it.
- **Shared reference files.** Each skill holds what it needs, including its own copy of the Guardrails section. That duplicates a few lines, but a teacher can install one skill alone and it still works.

## What an agent is here

An agent file in `agents/` is a short role description: a `name`, a `description`, the list of skills it uses, and the order to use them in. The teaching knowledge stays in the skills, so the agents never drift from them. The Markdown-with-frontmatter shape matches Claude Code's custom subagents, and other tools can take the body as a prompt.
