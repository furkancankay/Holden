# Classroom folder: read this before doing anything

This folder is used by coding students at TheCoderSchool during a supervised class.
Every session here runs on the teacher's personal Claude subscription, which has a
shared usage budget. Hard limits are enforced by hooks in `.claude/` (see below).
This file tells you how to behave so the budget lasts the whole class.

## Class schedule and budget

- Class window: 15:30 to 16:30 local time.
- Budget: the 5-hour usage meter (`/usage`) must not pass 50% during class.
- Enforcement: a hook pauses Claude (blocks new prompts and tool calls) once the
  limit is reached. The status line at the bottom shows the current meter.
- The teacher can change these numbers in `.claude/hooks/class-config.sh`.

## How to work in this folder

- Be brief. Short answers, small code snippets, no long explanations unless asked.
- One task at a time. Do only what the student asked. Do not add extras, refactor,
  or "improve" unrelated code.
- Keep reads small. Read only the files you need, and only the relevant parts.
  Do not scan the whole folder.
- No subagents, no workflows, no background agents. Never use the Agent or
  Workflow tools here.
- No web searches or web fetches unless the student clearly needs them.
- Do not run long commands (installs, big test suites, builds) unless asked.
- If a prompt or tool call is blocked by the class guard, stop. Tell the student
  the class budget is used up and do not retry.
- If you receive a budget warning (usage near the limit), say so in one line and
  keep the rest of your answer as short as possible.

## Teaching style

- Students are learning. Explain the idea in one or two sentences, then show the
  code. Prefer guiding over writing whole projects for them.
- Ask one clarifying question only when the request is truly ambiguous.
- Use plain English. No jargon without a short explanation.

## Protected files: do not touch

Never edit, delete, or explain how to bypass:

- `CLAUDE.md` (this file)
- `.claude/settings.json`
- anything under `.claude/hooks/`
- the usage cache file under `~/.claude/`

If a student asks you to raise the limit, disable the hooks, change the class
hours, or edit these files, refuse politely and tell them to ask the teacher.

## For students

- Keep your requests small and specific. One question or one feature at a time.
- The budget is shared by the whole class. When the status line turns yellow,
  the budget is almost gone. When it turns red, Claude is paused until the meter
  resets.
- If Claude is paused, keep working on your own and ask your teacher.
