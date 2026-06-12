# Admin Panel QA Checklist v2

## Purpose

This checklist prepares Manual QA for Admin Panel v1 after admin cleanup commits:

- `c608162 Disable legacy admin tab handlers`
- `7288fd6 Disable legacy admin fallback autorenders`

Goal:
confirm that Admin Panel cleanup did not break manual QA and that Admin Panel v1 is ready for Artur's review.

## Status

Draft

## Scope

Test only:

- `admin.html`
- Admin Panel navigation
- Admin Panel moderation screens
- Published Spots / base cards
- Spot Requests
- Reviews
- Core Moderation tabs

Do not test as part of this checklist:

- payments as a business process
- new feature creation
- database schema changes
- Supabase RLS
- auth architecture
- messaging architecture
- profile architecture
- map architecture

## Before Testing

1. Open the latest code archive or latest GitHub `origin/main`.
2. Confirm latest code commit is:
   `7288fd6 Disable legacy admin fallback autorenders`
3. Open `admin.html`.
4. Open browser DevTools console.
5. Log in with the allowed admin account.

If login fails, stop and take a screenshot of:

- login form;
- console errors;
- network errors if visible.

## Section Navigation

Click each left menu item.

For each click, expected result:

- the central screen changes;
- the left menu active state changes;
- the user is not left on the old Spot Requests screen;
- no new red console error appears.

### Dashboard

Click:
Dashboard

Expected:

- Dashboard screen is visible.
- Dashboard title or moderation summary is visible.
- Spot Requests list is not the only visible screen.

Error if:

- user remains on Spot Requests;
- blank screen;
- red console error.

Screenshot:
Dashboard after click.

### Moderation Inbox

Click:
Moderation Inbox

Expected:

- Moderation Inbox screen is visible.
- Queue area is visible.
- If there are no items, a clear empty/fallback message is visible.

Error if:

- screen remains Spot Requests;
- queue area is missing;
- red console error.

Screenshot:
Moderation Inbox after click.

### Spot Requests

Click:
Spot Requests

Expected:

- Spot Requests screen is visible.
- Spot request cards or empty/fallback message is visible.
- Filters inside Spot Requests remain clickable.

Test:

- click All;
- click New;
- click Returned / needs changes if visible.

Error if:

- filters do not react;
- cards disappear without fallback;
- red console error.

Screenshot:
Spot Requests after click.

### Published Spots

Click:
Published Spots

Expected:

- Published Spots screen is visible.
- Published spots list, base card, or safe fallback is visible.
- It must not remain on Spot Requests.

Test:

- click `Open / edit` if visible;
- click `Delete` if visible.

Expected for buttons:

- button reacts;
- modal/editor/fallback opens;
- if full logic is not available, user gets clear feedback.

Error if:

- button is dead;
- Published section is hidden behind another block;
- red console error.

Screenshot:
Published Spots / base table after click.

### Reviews

Click:
Reviews

Expected:

- Reviews screen is visible.
- Pending reviews or empty/fallback message is visible.
- Approve / Reject buttons react if review rows exist.

Error if:

- screen remains Spot Requests;
- approve/reject buttons do nothing;
- review publishes without moderation;
- red console error.

Screenshot:
Reviews after click.

### Users

Click:
Users

Expected:

- Users screen is visible.
- Users table or safe fallback is visible.
- Search field works if data is loaded.

Error if:

- screen remains Spot Requests;
- user table area is missing;
- red console error.

Screenshot:
Users after click.

### Confirmations

Click:
Confirmations

Expected:

- Confirmations screen is visible.
- Confirmation list or empty/fallback message is visible.

Error if:

- screen remains Spot Requests;
- action buttons are dead;
- red console error.

Screenshot:
Confirmations after click.

### Reports

Click:
Reports

Expected:

- Reports screen is visible.
- Placeholder/fallback message is acceptable.

Expected placeholder:
section may say that reports are prepared but not connected yet.

Error if:

- screen remains Spot Requests;
- blank screen;
- red console error.

Screenshot:
Reports after click.

### Records

Click:
Records

Expected:

- Records screen is visible.
- Core Moderation block may appear inside Records.
- Records content or "no data" message is visible.

Error if:

- screen remains Spot Requests;
- old V31/V32 fallback blocks appear unexpectedly as the main screen;
- red console error.

Screenshot:
Records after click.

### Instructors

Click:
Instructors

Expected:

- Instructors screen is visible.
- Instructor applications list, Core Moderation Instructor requests, or safe fallback is visible.

Error if:

- screen remains Spot Requests;
- blank screen;
- red console error.

Screenshot:
Instructors after click.

### Payments

Click:
Payments

Expected:

- Payments screen opens.
- Payment/business fallback may be visible.
- No new payment business logic is required for this QA.

Error if:

- screen remains Spot Requests;
- payment click changes map or public app behavior;
- red console error.

Screenshot:
Payments after click.

## Core Moderation Tabs

Open Records or Payments so the Core Moderation block is visible.

Click tabs:

- Records
- Business
- Payments
- Instructor requests

Expected:

- content inside the Core Moderation block changes;
- selected tab active state changes;
- if there is no data, clear "no data" message appears.

Error if:

- tab click does nothing;
- screen jumps to Spot Requests;
- central panel becomes blank;
- red console error.

Screenshots:

- Records tab
- Business tab
- Payments tab
- Instructor requests tab

## Spot Request Actions

Open:
Spot Requests

Test if a pending spot exists:

1. Click Approve on a request missing required fields.
2. Confirm approve is blocked.
3. Confirm admin sees a clear missing-fields message.
4. Confirm no object is auto-published.

Expected required fields:

- name;
- coordinates;
- country;
- at least one photo;
- approximate max depth.

Error if:

- invalid spot is approved;
- status changes despite validation failure;
- no message appears.

Screenshot:
validation message.

## Duplicate Warning

Open:
Spot Requests

Test if a possible duplicate exists:

1. Click Approve.
2. Confirm duplicate warning appears.
3. Cancel the confirmation.
4. Confirm the request is not auto-rejected, auto-deleted, or auto-merged.

Expected:

- warning only;
- final decision remains with moderator.

Error if:

- duplicate is automatically rejected;
- duplicate is automatically merged;
- duplicate is automatically deleted.

Screenshot:
duplicate warning.

## Main App Regression Check

Open:
`index.html`

Check:

- map opens;
- Add Place opens;
- profile opens;
- messages visually open or remain visually stable;
- no critical red console errors.

Error if:

- main app fails to load;
- Mapbox map fails to initialize;
- Add Place is broken;
- profile/messages are visibly broken.

Screenshots:

- map screen;
- Add Place screen;
- profile/messages if an issue appears.

## Console Rules

During all checks:

- keep DevTools console open;
- red errors must be screenshotted;
- warnings may be acceptable if UI works, but should be listed.

For each error, capture:

- screen name;
- action clicked;
- console message;
- screenshot.

## QA Result Format

Artur should report:

### Passed

List screens and actions that worked.

### Failed

List screens and actions that failed.

### Console Errors

Paste or screenshot errors.

### Screenshots

Attach screenshots for failed states and key successful sections.

### Final Decision

Choose one:

- Pass: ready for next small iteration.
- Pass with risks: usable but needs cleanup.
- Fail: not ready for next product work.

## Related Documents

- ../01_Product/Project_State.md
- ./Launch_Criteria.md
- ./Risk_Register.md
- ../07_Workflows/Night_Work_Mode.md
- ../06_Codex_Tasks/Master_Codex_Prompt.md

## Notes

- This checklist does not approve new features.
- If Admin Panel navigation fails again, next iteration should focus only on navigation.
- If login/auth/Supabase schema blocks testing, stop and report the blocker instead of changing code.
