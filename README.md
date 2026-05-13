# Code Guardian

**Code Guardian** is a Claude Code skill focused on repository health, safety, architecture, and scope review before making changes.

It helps developers work with more control, traceability, and security by inspecting a repository before an AI coding agent modifies files.

## Purpose

Code Guardian reviews a repository and generates a clear diagnosis about:

- project structure;
- missing important files;
- security risks;
- possible exposed secrets;
- suspicious or unnecessary dependencies;
- missing documentation;
- consistency with ADRs;
- pending Git changes;
- risks before executing a task;
- whether a requested change should be split into smaller steps.

## Main principle

> Code Guardian does not modify files by default.

It inspects first, reports findings, and suggests small, controlled next steps.

## What Code Guardian is for

Use Code Guardian when you want to:

- inspect a repository before asking Claude Code to make changes;
- detect security risks before installing dependencies;
- check if a project has a clean initial structure;
- validate that a requested change is small enough;
- detect files that should not be committed;
- review basic architecture and documentation;
- prepare a repository health report before a commit;
- check if a project is ready to be published.

## What Code Guardian is not for

Code Guardian is not intended to:

- replace a full security audit;
- automatically fix every issue;
- install dependencies without approval;
- run destructive commands;
- deploy applications;
- publish packages;
- modify many files without explaining the scope first.

## Repository structure

```text
code-guardian/
  README.md
  LICENSE
  CHANGELOG.md
  skills/
    code-guardian/
      SKILL.md
  docs/
    usage.md
    checklist.md
    publishing-notes.md
  examples/
    basic-report.md
    security-report.md
    pre-change-report.md
