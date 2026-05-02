# /kb:wrap-up Command Implementation Strategy
# This file tracks the logic for the wrap-up command to be implemented via skill calls.

1.  **Analyze**: Run `git status` and check `docs/state/CURRENT_STATE.md`.
2.  **Summarize**: Identify key achievements from the current session history.
3.  **Update**:
    - Update `docs/state/CURRENT_STATE.md` (progress).
    - Update `docs/session-state/next-actions.md` (achievements & next steps).
4.  **Inquire**: Ask if the user wants to commit changes.
5.  **Exit**: Short farewell.
