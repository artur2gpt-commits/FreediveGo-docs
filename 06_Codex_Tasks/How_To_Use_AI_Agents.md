# How To Use FreediveGo AI Agents

## Goal

Use AI agents as a project management system before sending tasks to Codex.

---

## Required Workflow

Before any Codex task, check the task through:

1. Product Manager
2. Solution Architect
3. QA Engineer
4. UX Reviewer
5. Security Engineer, if the task affects users, permissions, files or data

---

## Product Manager Check

Question:

Should this task be done now?

Checks:

- Is it MVP?
- Does it help launch?
- Is it more important than current priorities?
- Can it wait?

---

## Solution Architect Check

Question:

Will this task damage architecture?

Checks:

- Database impact
- Existing code reuse
- Duplicate logic
- Scalability

---

## QA Engineer Check

Question:

How will we test this?

Checks:

- Main user flows
- Regression risks
- Critical bugs
- Acceptance checklist

---

## UX Reviewer Check

Question:

Will the user understand this?

Checks:

- Simplicity
- Clarity
- Navigation
- Visual consistency

---

## Security Engineer Check

Question:

Can this expose private data or break permissions?

Checks:

- User roles
- Admin roles
- Supabase RLS
- File uploads
- Messages
- Private profiles

---

## Rule

No major task goes to Codex without this review.

---

## Output Format For Codex

Every Codex task should include:

1. Goal
2. Files to inspect
3. What to change
4. What not to change
5. Acceptance checklist
6. Regression checklist
