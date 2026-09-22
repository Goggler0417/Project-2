# Tagmark v2.29

Hotfix for the v2.28 startup failure.

- Restored `recordTagIds()` which was accidentally omitted during the v2.28 renderer refactor.
- This fixes `Can't find variable: recordTagIds` during startup/render-cache construction.
- No database reset or migration is required.
