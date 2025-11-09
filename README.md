# Seoul Underground Live - Static Site

This is a **static site** automatically deployed from the private crawler repository.

## Build Information

- **Build Time**: 2025-11-09T01:32:01Z
- **Source Commit**: [`b186e2308593911213554cd256b8a51cd9a89f79`](https://github.com/keunwoochoi/seoulunderground.live/commit/b186e2308593911213554cd256b8a51cd9a89f79)
- **Branch**: `main`
- **Workflow Run**: [View logs](https://github.com/keunwoochoi/seoulunderground.live/actions/runs/19201429492)

## Commit Details

- **Author**: Keunwoo Choi <gnuchoi+github@gmail.com>
- **Message**: Web electronic (#32)

* ok improved prompts for electronic

* minor

* beta-testing electronic features, views, etc.

* feat: Add Korean+English venue name format for Electronic genre

- Update frontend to show '한국어 (English)' format for venue names in Korean mode
- Only applies to Electronic genre on Venues tab (jazz unchanged)
- Fix unit tests: add required locality/genre parameters to all test calls
- Fix test_import_venue_masters.py: add locality='seoul', genre='jazz' to all import_venue_from_master calls
- Fix test_extract_core.py: add locality='seoul', genre='jazz' to all extract_from_image_and_text calls
- Deployment workflows already support electronic genre via export_static_json.py

* chore: trigger test deployment with electronic data

* fix: Address code review issues

- Security: Sanitize album names in icloud_sync.py to prevent AppleScript injection
- Code quality: Remove duplicate TARGET_GENRE and venues_fetch_profile in README.md
- Refactor: Simplify comment stripping logic in file_utils.py
- Import placement: Move 'import config' to top of extract_core.py

* chore: Remove documentation and personal notes from git tracking

These files are personal scratchpads, implementation notes, and temporary
documentation that should not be in the main repository:
- Implementation notes (ELECTRONIC_GENRE_IMPLEMENTATION.md, etc.)
- Personal notes (README_NOTE_KEUNWOO2.md)
- Temporary automation scripts (daily_story2.sh)
- Internal documentation (docs/PARTIALPROMPT_SYSTEM.md, etc.)

Files remain locally but are now untracked.

* update gitignore

## Deployment

- **Live Site**: https://seoulunderground.live
- **GitHub Pages**: https://seoulunderground-live.github.io

## Data Snapshot

The static JSON files in `/api/` were exported from the local backend at build time.
Events shown are from the crawler's database as of the build timestamp above.

---

*This README is auto-generated during deployment. Do not edit manually.*
