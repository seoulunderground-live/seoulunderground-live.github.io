# Seoul Underground Live - Static Site

This is a **static site** automatically deployed from the private crawler repository.

## Build Information

- **Build Time**: 2025-11-02T00:26:54Z
- **Source Commit**: [`6b37850579fe3abf72966a7fdcd217d0a018e361`](https://github.com/keunwoochoi/seoulunderground.live/commit/6b37850579fe3abf72966a7fdcd217d0a018e361)
- **Branch**: `main`
- **Workflow Run**: [View logs](https://github.com/keunwoochoi/seoulunderground.live/actions/runs/19004786850)

## Commit Details

- **Author**: Keunwoo Choi <gnuchoi+github@gmail.com>
- **Message**: Venue tab + about tab  (#11)

* feat: add Venues tab with enrichment improvements

Frontend:
- Add new Venues tab with card-style venue directory
- Implement venue sorting by event count (most active first)
- Add VenueCard component with comprehensive venue info display
- Fix multi-venue tag issue (fallback to venue_handle when venue_id is placeholder)
- Add i18n translations for venue-related fields
- Aggregate show times display (Mon-Fri: 20:30 instead of listing all days)
- Tab styling improvements (active tab more visible)

Backend:
- venues_enrich: add support for manual venue information from venue_manual_information.jsonl
- venues_enrich: manual data takes priority over Gemini enrichment
- export_static_json: filter events to today + future only (reduce JSON size)

Note: venue_candidates.csv updated but gitignored

* fix: export_static_json datetime type error

- Change _get_today_kst_start() to return datetime object instead of string
- crud.list_events expects datetime and calls .isoformat() on it
- Add tests to prevent regression of type errors in export functions

Fixes deployment error:
  AttributeError: 'str' object has no attribute 'isoformat'

* fix: hide placeholder venues from Venues tab

Filter out venues with no name_irl in the venues display.
These are automatically created placeholder venues when events
reference unknown venue handles, and shouldn't be shown to users.

Only shows venues that have been properly enriched with venue data.

* fix: stop creating placeholder venues in database

Changed event import behavior:
- No longer creates placeholder venues when events reference unknown handles
- Unknown venues are logged to venue_candidates.csv for manual review
- Events will have venue_id=None if venue not in database

This keeps the venue database clean - only venues from venue_handles.txt
that have been properly enriched should be in the database.

Manually deleted 5 existing placeholder venues from local database.

* fix: eliminate duplicate venue lookup logs in import_events

Fixed a double-call bug where ensure_venue was being called twice:
1. In import_events_from_directory (line 575)
2. In create_event_from_annotation (line 403)

This caused duplicate database queries and duplicate log messages for
every event with a missing venue (e.g. 100+ events from @sounddog_jazz
resulted in 200+ 'not in database' messages).

Changes:
- Store venue_id in annotation dict after first lookup (even if None)
- Check for key existence ('venue_id' in ann) not just truthiness
- Add session-level cache to log each missing venue only once per run
- Pass _missing_cache to ensure_venue to track already-logged venues

Result: Each missing venue now logs exactly once per import run.

* oh...

* updating deploy yaml to clean dist dir

* before naver map

* all!

* reflect gemini comment

* final fix! lets gooo

## Deployment

- **Live Site**: https://seoulunderground.live
- **GitHub Pages**: https://seoulunderground-live.github.io

## Data Snapshot

The static JSON files in `/api/` were exported from the local backend at build time.
Events shown are from the crawler's database as of the build timestamp above.

---

*This README is auto-generated during deployment. Do not edit manually.*
