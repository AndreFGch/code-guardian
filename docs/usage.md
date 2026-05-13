# Code Guardian Usage Guide

## Local personal storage

Recommended personal storage path on Windows:

```text
D:\Aplicaciones\Skills\code-guardian
```

This keeps the skill separate from any specific project.

## Project installation

Claude Code project skills should be placed under:

```text
PROJECT_ROOT\.claude\skills\code-guardian\SKILL.md
```

Example:

```text
D:\Aplicaciones\Nebulosa\.claude\skills\code-guardian\SKILL.md
```

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
