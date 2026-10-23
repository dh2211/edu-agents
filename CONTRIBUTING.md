# Contributing

Teachers, coaches, and developers are all welcome. The most useful contributions are fixes from real classroom use: "the rubric skill writes levels that two of us scored differently" is worth more than a new skill.

## Report a problem

Open an issue with:

- the skill and the agent you used (for example, `edu-worksheet-builder` in Cursor),
- what you asked for, with student information removed,
- what you got and what you expected.

## Change a skill

1. Fork the repository and create a branch.
2. Edit the `SKILL.md`. Follow [docs/authoring.md](docs/authoring.md).
3. Try the skill in at least one agent. Say which one in the pull request.
4. Run the checks:

   ```bash
   npm run validate
   npm test
   ```

5. Open a pull request that says what changed and why.

## Add a skill

Open an issue first and describe the teacher's problem it solves. Then follow [docs/authoring.md](docs/authoring.md) and include a worked example in `examples/`.

## Rules for all content

- Plain English.
- No real student data in issues, examples, or tests. Use invented work and say that it is invented.
- No invented standard codes. Use codes from the official source or a placeholder.
- No copyrighted texts beyond short quotations.
- Keep the Guardrails section identical across skills.
- Start every skill and agent name with `edu-`.

By contributing, you agree that your contribution is licensed under the [MIT License](LICENSE).
