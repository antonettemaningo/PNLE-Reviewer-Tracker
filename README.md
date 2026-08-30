# PNLE Study Command Center

**Current build:** V3 Full  
**Type:** Offline-first single-page HTML study application

This package organizes the current PNLE Command Center build as a proper project while preserving the original HTML file you provided.

## Project structure

```text
PNLE-Study-Command-Center/
├── index.html
├── PNLE_Command_Center_V3_Full.html
├── README.md
├── assets/
│   ├── images/
│   ├── icons/
│   └── sounds/
├── data/
│   ├── coverage.json
│   ├── quotes.json
│   └── bible-verses.json
└── docs/
    └── SETUP.md
```

## What's included in the current V3 Full build

- Dashboard with overall and NP I–V progress
- Reviewer upload/pasted-text indexing
- Custom NP/topic coverage tracking
- Reviewer-first local AI assistant
- Optional secure AI endpoint configuration
- Adaptive practice and mock exam modes
- Mistake bank and weak-area detection
- Flashcards
- Progress/analytics views
- Study timer with completion sound
- Notes
- Local account creation/sign-in
- Appearance customization
- Backup export/import
- Optional Supabase configuration placeholder for future cloud sync

## Important note about the current architecture

The application is still primarily a self-contained HTML application. The project folders are now prepared so future work can move data, assets, and documentation out of the HTML without losing the current build.

The current cloud-sync button is an adapter/configuration placeholder: the V3 Full file states that Supabase database/auth tables still need to be created before real sync can run.

## How to run

Open `index.html` in a modern browser.

For the simplest offline use, no server is required.

For future development, a local static server is recommended so browser behavior is closer to a deployed site.

## Preserving your original material

The supplied V3 Full HTML is preserved as:

- `PNLE_Command_Center_V3_Full.html`

The same current build is also available as:

- `index.html`

The `assets/`, `data/`, and `docs/` folders are intentionally separated so your original reviewer materials and future project files can be added without turning the HTML into the only source of truth.

## Future expansion

A later production version can be migrated into:

```text
frontend/
backend/
database/
assets/
docs/
```

That would be appropriate when adding real authentication, cloud storage, multi-device synchronization, server-side AI, and larger reviewer/document processing.
