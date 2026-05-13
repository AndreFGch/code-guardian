# Code Guardian Usage Guide

## Local personal storage

Clone or download this repository wherever you keep your tools or Claude Code skills.

Example:

```bash
git clone https://github.com/AndreFGch/code-guardian.git
```

## Project installation

Claude Code project skills should be placed under:

```text
YOUR_PROJECT/.claude/skills/code-guardian/SKILL.md
```

To install Code Guardian in a project, copy this folder:

```text
code-guardian/skills/code-guardian
```

into:

```text
YOUR_PROJECT/.claude/skills/code-guardian
```

## Windows example

```powershell
mkdir "YOUR_PROJECT\.claude\skills"

xcopy "code-guardian\skills\code-guardian" "YOUR_PROJECT\.claude\skills\code-guardian" /E /I
```

Replace `YOUR_PROJECT` with the path to your project.

## macOS / Linux example

```bash
mkdir -p YOUR_PROJECT/.claude/skills

cp -R code-guardian/skills/code-guardian YOUR_PROJECT/.claude/skills/code-guardian
```

Replace `YOUR_PROJECT` with the path to your project.

## Suggested workflow

1. Open the project folder in your IDE.
2. Open a terminal in the project root.
3. Start Claude Code.
4. Ask Claude to use Code Guardian before modifying files.
5. Review the report.
6. Approve only one small task at a time.

## Recommended prompt

```text
Use the code-guardian skill to inspect this repository.
Do not modify files.
Return a report with findings by severity and recommended next steps.
```

## Recommended pre-change prompt

```text
Use code-guardian before making this change.
Tell me what files you would touch, why, and whether the task should be split.
Do not modify files yet.
```

## Recommended security prompt

```text
Use code-guardian to check for secrets, unsafe scripts, risky dependencies and files that should not be committed.
Do not print secret values.
Do not modify files.
```
