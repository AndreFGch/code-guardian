# Code Guardian Checklist

## Repository basics

- [ ] README exists.
- [ ] `.gitignore` exists.
- [ ] License exists if the project may be public.
- [ ] Changelog exists if the project may be versioned.
- [ ] Project has clear folder structure.
- [ ] Project has clear setup instructions.

## Safety

- [ ] No secrets committed.
- [ ] No `.env` files committed unless intentionally templated.
- [ ] `.env.example` exists if environment variables are required.
- [ ] No private keys committed.
- [ ] No tokens committed.
- [ ] No production credentials committed.
- [ ] No destructive scripts exposed as default commands.

## Claude Code

- [ ] `CLAUDE.md` exists if the repo needs persistent instructions.
- [ ] `.claude/skills` exists if project skills are used.
- [ ] Skills are scoped and documented.
- [ ] Skills do not request unnecessary tools.
- [ ] Skills do not perform destructive actions by default.

## Architecture

- [ ] ADR folder exists for architectural decisions.
- [ ] Initial ADR exists for stack and approach.
- [ ] Project boundaries are understandable.
- [ ] Modules have clear responsibility.
- [ ] Sensitive actions require approval.

## Change control

- [ ] Git working tree is reviewed before changes.
- [ ] Tasks are limited to 3 to 5 files when possible.
- [ ] Large tasks are split.
- [ ] Diffs are reviewed before commit.
- [ ] Commits are small and meaningful.
