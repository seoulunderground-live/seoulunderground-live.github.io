# Seoul Underground Live - Static Site

This is a **static site** automatically deployed from the private crawler repository.

## Build Information

- **Build Time**: 2025-11-09T19:29:09Z
- **Source Commit**: [`45469109535ca79f41ea5cbc19c787f7c68ede35`](https://github.com/keunwoochoi/seoulunderground.live/commit/45469109535ca79f41ea5cbc19c787f7c68ede35)
- **Branch**: `main`
- **Workflow Run**: [View logs](https://github.com/keunwoochoi/seoulunderground.live/actions/runs/19213353922)

## Commit Details

- **Author**: Keunwoo Choi <gnuchoi+github@gmail.com>
- **Message**: fix slack noti (#34)

* done

* Use CSS variable for secondary text color in admin list

Code review feedback: replaced hardcoded #666 color with var(--text-secondary)
for better theme consistency and maintainability. Applied to both datetime and
price elements in the admin event list.

## Deployment

- **Live Site**: https://seoulunderground.live
- **GitHub Pages**: https://seoulunderground-live.github.io

## Data Snapshot

The static JSON files in `/api/` were exported from the local backend at build time.
Events shown are from the crawler's database as of the build timestamp above.

---

*This README is auto-generated during deployment. Do not edit manually.*
