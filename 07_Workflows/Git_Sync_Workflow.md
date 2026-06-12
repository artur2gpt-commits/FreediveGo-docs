# FreediveGo Git Sync Workflow

## Purpose

Keep FreediveGo code and documentation repositories safe, clean and synchronized.

---

## Repositories

### Code Repository

Local path:

C:\Users\Артур\Documents\Projects\FreediveGo

GitHub:

artur2gpt-commits/FreediveGo

Purpose:

Application code.

---

### Documentation Repository

Local path:

C:\Users\Артур\Documents\FreediveGo-docs-numbered

GitHub:

artur2gpt-commits/FreediveGo-docs

Purpose:

Product documentation, roadmap, AI agents, workflows, backlog and launch criteria.

---

## Do Not Use

Do not use:

C:\Users\Артур\Documents\FreediveGo-docs

Reason:

This folder has a different history and old structure.

---

## Required Before Work

Before any work, Codex must run:

git status

git log --oneline -3

git remote -v

---

## Safe Status

Safe status:

main...origin/main

This means local repository and GitHub are synchronized.

---

## Local Ahead

If status says:

ahead of origin/main by 1 commit

Action:

git push origin main

---

## Local Behind

If status says:

behind origin/main

Action:

git pull origin main

---

## Diverged History

If status says histories diverged:

Stop.

Do not force push.

Ask Artur.

---

## Never Do Without Approval

Never run:

git push --force

Never overwrite GitHub history.

Never delete working branches without approval.

Never mix code repo and docs repo.

---

## Required After Work

After every Codex task, report:

* Repository path
* Changed files
* Commit hash
* Push status
* git status
* git log --oneline -3

---

## Main Rule

Code changes go to FreediveGo.

Documentation changes go to FreediveGo-docs-numbered.
