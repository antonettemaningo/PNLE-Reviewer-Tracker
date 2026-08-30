# Setup

## Current V3 Full

1. Open `index.html` in a modern browser.
2. The app stores its local state in browser `localStorage`.
3. Use **Settings → Export Full Backup** to create a JSON backup.
4. Use **Settings → Import Backup** to restore a backup.

## Reviewer files

The current browser implementation can directly index text from TXT, MD, and CSV files. Other accepted file types are stored as organized attachments, but their text is not automatically extracted by the current V3 Full build.

## AI

The local AI mode is reviewer-first and only uses indexed reviewer text plus the app's coverage/mistake data.

If an external AI endpoint is configured, keep private API keys on the server rather than placing them in this HTML file.

## Cloud

The current UI includes fields for a Supabase project URL and anonymous public key, but the V3 Full build does not yet implement the database/auth table layer required for true cloud synchronization.

## Recommended next migration

When the project grows, separate:

- UI into `frontend/`
- server/API logic into `backend/`
- persistent records into `database/`
- uploaded/static material into `assets/`
- documentation into `docs/`
