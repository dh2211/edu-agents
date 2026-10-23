# edu-agents

Agent Skills that help K-12 teachers plan lessons and make teaching materials: objectives, unit and lesson plans, slide outlines, worksheets, quizzes with answer keys, rubrics, differentiation, feedback on student work, and messages to families.

Each skill is a folder with a `SKILL.md` file in the open [Agent Skills](https://agentskills.io/specification) format. Claude Code, Codex, Cursor, Grok, OpenCode, and other agents that read that format can load them. You install the skills once, then ask your agent in plain English: "Plan a 5-lesson Grade 8 unit on chemical reactions."

The skills are standards-agnostic. They work with Common Core, NGSS, a state or national curriculum, or your own goals, and they never invent standard codes.

## Quick start

1. Clone the repository:

   ```bash
   git clone https://github.com/EduAgentsKit/edu-agents.git
   ```

2. Copy or link the `skills/` folders into the skills folder your agent reads. For Claude Code on macOS or Linux:

   ```bash
   mkdir -p ~/.claude/skills
   cp -R edu-agents/skills/* ~/.claude/skills/
   ```

   [docs/install.md](docs/install.md) lists the folder for each agent, with links to each tool's documentation. You don't need Node.js or any other software to use the skills.

3. Start your agent and ask for what you need:

   > Write a 45-minute Grade 3 lesson on unit fractions, with an exit ticket. Standard: CCSS 3.NF.A.1.

   The agent picks the matching skills, asks for anything missing, and drafts the lesson.

## Skills

| Skill | What it makes |
| --- | --- |
| [edu-learning-objectives](skills/edu-learning-objectives/SKILL.md) | Measurable objectives and success criteria at a Bloom's or DOK level, aligned to the standards you give it |
| [edu-unit-planner](skills/edu-unit-planner/SKILL.md) | A backward-design (UbD) unit: understandings, essential questions, performance task, lesson sequence |
| [edu-lesson-planner](skills/edu-lesson-planner/SKILL.md) | One timed lesson with gradual release (I do, we do, you do) and checks for understanding |
| [edu-slide-outline](skills/edu-slide-outline/SKILL.md) | A slide-by-slide outline with on-slide text, visuals to find, and speaker notes |
| [edu-worksheet-builder](skills/edu-worksheet-builder/SKILL.md) | A worksheet or practice set, easier to harder, with a full answer key |
| [edu-assessment-builder](skills/edu-assessment-builder/SKILL.md) | A quiz or test with a blueprint, items across DOK levels, and a key with rationales |
| [edu-formative-checks](skills/edu-formative-checks/SKILL.md) | Exit tickets, hinge questions, and warm-ups, with what each wrong answer means |
| [edu-rubric-builder](skills/edu-rubric-builder/SKILL.md) | An analytic, single-point, or holistic rubric plus a student checklist |
| [edu-differentiation](skills/edu-differentiation/SKILL.md) | UDL changes, support and extension tiers, English learner supports, and an accommodations menu |
| [edu-student-work-feedback](skills/edu-student-work-feedback/SKILL.md) | Feedback on student work: a strength, a next step, a question, and an optional suggested score |
| [edu-family-message](skills/edu-family-message/SKILL.md) | Plain-language messages to parents and guardians |

## Agents

An agent here is a short role file that names the skills it uses and the order to use them in. It adds no new instructions about teaching. Those live in the skills.

| Agent | Role |
| --- | --- |
| [edu-lesson-planner-agent](agents/edu-lesson-planner-agent.md) | Plans from objectives to unit, lessons, materials, and assessment, pausing for your approval at each step |
| [edu-assessment-agent](agents/edu-assessment-agent.md) | Quizzes, tests, rubrics, quick checks, and feedback on student work |
| [edu-family-liaison-agent](agents/edu-family-liaison-agent.md) | Messages to families based on what the class is learning |

You don't need the agents. Every skill works on its own.

## Examples

[examples/](examples/) has complete outputs produced by following the skills:

- [Grade 3 math: unit fractions](examples/grade-3-math-fractions.md). Objectives, a lesson plan, a worksheet with key, and an exit ticket.
- [Grade 8 science: chemical reactions](examples/grade-8-science-chemical-reactions.md). A unit plan, a quiz with key, and a lab report rubric.
- [Grade 11 English: argument writing](examples/grade-11-english-argument.md). A lesson, a rubric, feedback on a sample paragraph, differentiation, and a family message.

## What the skills always do

Every skill ends with the same Guardrails section, and the validator fails if one is missing. The agent:

- uses only standard codes you supply and writes `[standard: ask teacher]` otherwise,
- works without student names or identifying details,
- fits content to the grade and flags safety and sensitive topics,
- works every answer key and marks unsure facts `[verify]`,
- drafts, and leaves grades, placements, and IEP decisions to you.

## Privacy

Don't paste student names, ID numbers, IEP documents, or other personal information into an AI tool. Describe needs in general terms instead ("two students read below grade level"). The skills tell the agent to remove names it sees, but the text has already reached the AI provider by then. Check your school's or district's rules before you use AI tools with student work.

## Why Agent Skills

[docs/format.md](docs/format.md) explains the choice. In short, a skill is plain Markdown in a folder, several major coding agents already load the same folder layout, and a teacher can read and edit every instruction.

## Documentation

- [Install for your agent](docs/install.md)
- [Use the skills](docs/usage.md)
- [Write a new skill](docs/authoring.md)
- [Why this format](docs/format.md)
- [Contributing](CONTRIBUTING.md)

## License

[MIT](LICENSE).
