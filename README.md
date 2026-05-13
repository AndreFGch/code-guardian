# Code Guardian

**Code Guardian** is a Claude Code skill focused on repository health, safety, architecture, and scope review before making changes.

Its goal is to help developers work with more control, security, and traceability, especially in projects where AI coding agents should not modify files without first explaining what they plan to touch and why.

---

## Purpose

Code Guardian reviews a repository and generates a clear diagnosis about:

- project structure;
- missing important files;
- security risks;
- possible exposed secrets;
- suspicious or unnecessary dependencies;
- missing documentation;
- ADR consistency;
- pending Git changes;
- risks before executing a task;
- recommended scope for the next changes.

---

## Main Principle

> Code Guardian does not modify files by default.

It analyzes first, reports findings, and only suggests small, controlled changes.

---

## What Code Guardian Checks

Code Guardian can help inspect:

- repository structure;
- README quality;
- `.gitignore` coverage;
- ADR or architecture documentation;
- Claude Code instructions such as `CLAUDE.md`;
- project skills under `.claude/skills`;
- dependency files;
- risky scripts;
- possible secrets or sensitive files;
- environment files;
- generated files committed by mistake;
- build and test scripts;
- Git status and uncommitted changes;
- whether a requested task should be split.

---

## Repository Structure

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
Installation

Clone this repository wherever you keep your tools or Claude Code skills.

git clone https://github.com/AndreFGch/code-guardian.git

Example:

git clone https://github.com/AndreFGch/code-guardian.git code-guardian
Use Inside a Claude Code Project

To use Code Guardian in a project, copy only this folder:

code-guardian/skills/code-guardian

into your project skills folder:

YOUR_PROJECT/.claude/skills/code-guardian

Final structure inside your project:

YOUR_PROJECT/
  .claude/
    skills/
      code-guardian/
        SKILL.md
Windows Example
mkdir "YOUR_PROJECT\.claude\skills"

xcopy "code-guardian\skills\code-guardian" "YOUR_PROJECT\.claude\skills\code-guardian" /E /I

Replace YOUR_PROJECT with the path to your project.

macOS / Linux Example
mkdir -p YOUR_PROJECT/.claude/skills

cp -R code-guardian/skills/code-guardian YOUR_PROJECT/.claude/skills/code-guardian

Replace YOUR_PROJECT with the path to your project.

Usage Examples

Inside Claude Code, from your project root:

Use the code-guardian skill to inspect this repository.
Do not modify files.
Return a repository health report grouped by severity.

Before making a change:

Use code-guardian before this change.
Tell me which files you would inspect, what risks exist, and whether this task should be split.
Do not edit files.

Before installing dependencies:

Use code-guardian to review security risks before installing any dependency.
Do not install anything.

Before a commit:

Use code-guardian to review the current repository state before commit.
Check Git status, risky files, documentation gaps, and scope.
Do not modify files.
Recommended Workflow
Ask Code Guardian to inspect the repository.
Review the report.
Select one small task.
Ask Claude Code to explain which files it plans to touch.
Approve the change.
Review the diff.
Commit only after verifying the change.
Output Format

Code Guardian reports should follow this structure:

# Code Guardian Report

## 1. Scope

What was reviewed and what was not reviewed.

## 2. Repository snapshot

- Current folder:
- Git branch:
- Git status:
- Main detected stack:
- Important files found:

## 3. Findings by severity

### Critical

Issues that may expose secrets, destroy data, deploy accidentally, or cause major security risk.

### High

Issues that may break builds, hide risky behavior, or create maintainability/security problems.

### Medium

Issues that should be improved but do not block immediate progress.

### Low

Cleanups, naming, documentation, consistency, or small improvements.

## 4. Evidence

List the files or observations that support the findings.

## 5. Recommended next steps

Small, ordered tasks. Each task should modify no more than 3 to 5 files.

## 6. Before-changing plan

If implementation is requested, list:

- files you would touch;
- why each file must be touched;
- expected risk;
- whether user approval is required.
Severity Levels
Critical

Used for:

exposed credentials;
destructive commands in scripts;
production secrets committed;
unsafe deployment defaults;
task requests that require modifying many files without approval;
unclear commands that could delete or overwrite data.
High

Used for:

missing .gitignore in an active project;
missing environment handling;
unsafe dependency installation requests;
unclear architecture in a repo with multiple apps;
no audit/logging around sensitive actions;
sensitive integrations without a permission model.
Medium

Used for:

missing README;
missing ADRs;
unclear folder naming;
missing basic scripts;
missing tests in important modules;
inconsistent project structure.
Low

Used for:

formatting suggestions;
naming suggestions;
minor documentation improvements;
optional organization improvements.
Safety Rules

Code Guardian should not run destructive commands.

It should avoid commands that delete, move, overwrite, publish, deploy, install, or send data unless the user explicitly approves them.

Avoid commands such as:

rm -rf
git reset --hard
git clean -fd
npm publish
npm install
pnpm install
yarn install

On Windows, avoid commands such as:

Remove-Item -Recurse -Force
del /s
rmdir /s

unless the user explicitly approves them and the risk is clearly explained.

Secret Handling

Code Guardian should flag possible secrets or sensitive files, but it should not print secret values.

Examples of risky files or indicators:

.env;
.env.local;
.env.production;
private keys;
certificates;
tokens;
passwords;
connection strings;
API keys;
database credentials;
service account files;
files containing names like secret, credential, token, key, or password.
Philosophy

Code Guardian prioritizes:

safety;
clarity;
small changes;
evidence;
traceability;
maintainability.
Limitations

Code Guardian is not a replacement for:

a full security audit;
dependency vulnerability scanners;
secret scanning tools;
automated tests;
code review by an experienced developer.

It is a Claude Code skill designed to improve repository inspection and change control before an AI coding agent modifies files.

Project Status

Initial experimental version.

Current version:

v0.1.0
License

This project is licensed under the MIT License.


Después de guardarlo, ejecutá:

```powershell
git add README.md
git rebase --continue
git status