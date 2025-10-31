# Seoul Underground Live - Static Site

This is a **static site** automatically deployed from the private crawler repository.

## Build Information

- **Build Time**: 2025-10-31T05:37:17Z
- **Source Commit**: [`e885faaabe07b95d36d7142a26b0496b083df605`](https://github.com/keunwoochoi/seoulunderground.live/commit/e885faaabe07b95d36d7142a26b0496b083df605)
- **Branch**: `main`
- **Workflow Run**: [View logs](https://github.com/keunwoochoi/seoulunderground.live/actions/runs/18963805280)

## Commit Details

- **Author**: Keunwoo Choi <gnuchoi+github@gmail.com>
- **Message**: Fix workflow verification steps for nested JSON structure

- Update deploy-pages.yml to check seoul/jazz/events.en.json instead of flat events.en.json
- Update deploy-test.yml with same fix
- Use 'ls -lhR' to show recursive directory structure
- Use 'find' to locate all JSON files for size check

Fixes the workflow verification errors after locality/genre refactoring.

## Deployment

- **Live Site**: https://seoulunderground.live
- **GitHub Pages**: https://seoulunderground-live.github.io

## Data Snapshot

The static JSON files in `/api/` were exported from the local backend at build time.
Events shown are from the crawler's database as of the build timestamp above.

---

*This README is auto-generated during deployment. Do not edit manually.*
