# Instructions for AI agents

This repository is my **blog** using a Hugo

## Workflow (summary)

- Never commit to `master`. Never push to any remote. Never publish.
- For each user task, create a branch with conventional naming (`feat/…`, `fix/…`, `docs/…`, `chore/…`).
- Prefer small commits as you go.
- When the task is done, open an offline “pull request”: a **patch file in the repository root** with a description comment at the top. `*.patch` is gitignored; do not commit patch files.
- The user reviews by writing comments *inside that patch file*. After they say they are done, implement the requested changes, commit, and generate a **new** patch file.
- They squash-merge to `master` and assign the next task.

## Starting a new session

1. Read this file.
2. Check `git status` / current branch; do not assume you are already on a task branch.
3. Wait for (or continue) the user’s current task. Do not start unrelated work.
