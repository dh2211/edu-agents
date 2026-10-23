# Use the skills

After you [install the skills](install.md), ask your agent for what you need in plain English. The agent matches your request to a skill's description and loads it. You can also name the skill: "Use the edu-rubric-builder skill to..."

## Give the agent what a colleague would need

The skills ask for missing details, but a complete first request saves a round trip. Include:

- grade and subject,
- topic or text,
- time: minutes per lesson, number of lessons,
- standards, with codes, if your school uses them,
- what the class needs, described without names: "6 of 28 students are newcomers who speak Arabic",
- the format you want: print, slides, digital.

## Requests that work well

- "Write objectives for a two-week Grade 5 unit on the water cycle. Use DOK levels. Standards: NGSS 5-ESS2-1."
- "Plan a 50-minute Grade 9 algebra lesson on slope as rate of change. Then make an exit ticket."
- "Make a 12-question quiz on the causes of World War I for Grade 10, with an answer key. Mostly multiple choice, two short answers."
- "Build a 4-level rubric for a Grade 7 persuasive speech."
- "Here is a student paragraph and my rubric. Draft feedback: one strength, one next step, one question."
- "Adapt this worksheet for three students reading two grades below level and one newcomer English learner."
- "Write a short email to families about our next unit on fractions, with one thing they can do at home."

## Plan a whole unit

Ask for the `edu-lesson-planner-agent` workflow, or say: "Plan a 6-lesson Grade 8 unit on chemical reactions, then write lesson 1 with slides and a worksheet, then a quiz and rubric." The agent writes objectives, then the unit, then the lesson and materials, and stops after each step for you to approve or change it.

## Review everything before you use it

The skills tell the agent to work every answer key and mark unsure facts with `[verify]`. Agents still make mistakes. Before you teach or hand out anything:

1. Work the answer key yourself, or spot-check it.
2. Search for `[verify]` and `[standard: ask teacher]` and fill them in.
3. Check names, examples, and images for anything wrong for your students or community.
4. Read every family message before you send it.

## Keep student data out

Describe needs in general terms. Don't paste names, ID numbers, IEP or 504 documents, health information, or photos of students. If you paste student work for feedback, remove the name first. The skills remove names they see, but by then the text has reached the AI provider.
