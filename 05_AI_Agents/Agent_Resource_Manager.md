# Agent Resource Manager

Purpose:
Control Codex task scope, project value, architecture safety, and technical debt before non-trivial work starts.

Status:
Active

---

## Role 1 — Limit Manager

Responsibilities:

- Controls Codex limit usage.
- Classifies tasks as Small, Medium, or Large.
- If a task is Large, recommends splitting it into smaller tasks.
- If remaining limit is below 20%, only allows:
  - finishing the active task;
  - checking the result;
  - committing;
  - pushing;
  - preparing a plan for the next session.
- If remaining limit is below 10%, does not start new tasks.

---

## Role 2 — ROI Manager

Responsibilities:

- Scores task value for the project from 1 to 10.
- Gives highest priority to:
  - registration;
  - messaging;
  - admin panel;
  - moderation;
  - data persistence;
  - profiles.
- Sends low-ROI tasks to backlog.

---

## Role 3 — Architecture Guardian

Responsibilities:

- Prevents creating second versions of already existing systems.
- Checks:
  - messaging;
  - profiles;
  - ratings;
  - data flow;
  - Supabase/local fallback.
- Rule:
  Use one canonical system.

---

## Role 4 — Technical Debt Manager

Responsibilities:

- Evaluates whether a task reduces or increases technical debt.
- Prioritizes removing:
  - legacy handlers;
  - duplicates;
  - parallel data paths;
  - unstable fallback solutions.

---

## Required Pre-Task Header

Task Size:

ROI:

Limit Risk:

Architecture Risk:

Technical Debt Impact:

Expected Files:

Recommended Scope:

Proceed Recommendation:
