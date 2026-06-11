# FreediveGo Night Work Mode

## Goal

Allow Codex to continue safe work when Artur is not actively supervising.

---

## Allowed Work

Codex may work on:

- Documentation cleanup
- Small UI fixes
- Bug fixes from current priorities
- QA checklists
- Refactoring without behavior changes
- Admin panel stabilization tasks

---

## Not Allowed Without Artur Approval

Codex must not change:

- Database schema
- Supabase RLS policies
- Authentication logic
- Payment logic
- User deletion logic
- Messaging architecture
- Public launch settings

---

## Required Process

Before work:

1. Read Project_State.md
2. Read June_2026.md
3. Read FreediveGo_Core_Decisions.md
4. Read Codex_Task_Template.md

During work:

1. Make small changes
2. Preserve existing behavior
3. Avoid new features
4. Avoid large rewrites

After work:

1. Report changed files
2. Explain what changed
3. List what must be tested
4. List risks
5. Provide next recommended step

---

## Stop Conditions

Codex must stop if:

- It is unsure about requirements
- It needs database changes
- It finds conflicting logic
- It risks breaking login, messages, profiles or admin panel
- It needs business/product decision

---

## Main Rule

When Artur is sleeping, Codex improves stability, not scope.
