# Fix FreediveGo Docs Structure

## Goal

Clean and normalize the repository structure.

## Current Problems

1. `02_Roadmap` is inside `01_Product`.
2. There are two `05_AI_Agents` folders.
3. `Agent_Security_Engineer.md` is separated from the other agents.
4. `03_Decisions_OLD.md` is no longer needed.

## Required Final Structure

README.md

01_Product/
- Vision.md

02_Roadmap/
- Roadmap_2026.md

03_Decisions/
- Approved_Decisions.md

04_Current_Priorities/
- June_2026.md

05_AI_Agents/
- Agent_Product_Manager.md
- Agent_QA_Engineer.md
- Agent_Solution_Architect.md
- Agent_UX_Reviewer.md
- Agent_Security_Engineer.md
- Agent_Moderator.md
- Agent_Marketing_Director.md

## Required Actions

1. Move `Roadmap_2026.md` from `01_Product/02_Roadmap/` to `02_Roadmap/`.
2. Move `Agent_Security_Engineer.md` into the same `05_AI_Agents` folder as the other agents.
3. Keep only one `05_AI_Agents` folder.
4. Delete `03_Decisions_OLD.md`.
5. Do not change file contents unless needed.
6. Commit with message: `Fix documentation structure`.
