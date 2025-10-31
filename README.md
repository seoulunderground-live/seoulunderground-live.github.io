# Seoul Underground Live - Static Site

This is a **static site** automatically deployed from the private crawler repository.

## Build Information

- **Build Time**: 2025-10-31T05:44:31Z
- **Source Commit**: [`94dcb5a8570d84fb201b4cf4e839f5b651c072da`](https://github.com/keunwoochoi/seoulunderground.live/commit/94dcb5a8570d84fb201b4cf4e839f5b651c072da)
- **Branch**: `main`
- **Workflow Run**: [View logs](https://github.com/keunwoochoi/seoulunderground.live/actions/runs/18963850910)

## Commit Details

- **Author**: Keunwoo Choi <gnuchoi+github@gmail.com>
- **Message**: Add database validation step before export in workflows

Fail-fast check to prevent cryptic errors from empty database:
- Check event and venue counts before running export script
- Exit with clear error message if database is empty
- Show helpful command to fix the issue
- Display counts when validation passes

This prevents the confusing 'no such table: events' error from
propagating through the export script. Now both test and production
deployments will fail immediately with actionable error messages.

Fixes the root cause of the empty database deployment failure.

## Deployment

- **Live Site**: https://seoulunderground.live
- **GitHub Pages**: https://seoulunderground-live.github.io

## Data Snapshot

The static JSON files in `/api/` were exported from the local backend at build time.
Events shown are from the crawler's database as of the build timestamp above.

---

*This README is auto-generated during deployment. Do not edit manually.*
