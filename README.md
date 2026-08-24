# Coach Tactics Pro

Offline-first soccer tactical board and match planner.

## Current features
- Multiple teams, initially Oregon SC, Randos, and Spartak
- 11v11, 9v9, 8v8, 7v7, 6v6, and 5v5 formats
- Team-specific rosters with names, numbers, and roles
- Formation presets by game format
- Drag-and-drop players and ball
- Optional opponent overlay
- Attacking 5-lane overlay
- Defensive 3-lane bias: left, center, or right
- Save tactical phases and coaching cues
- Animate transitions between saved phases
- Match plans by opponent/date/venue
- Export/import full JSON backup
- Local device storage
- Installable PWA with offline caching

## Put it online with GitHub Pages
1. Create a GitHub repository, for example `coach-tactics-pro`.
2. Upload every file/folder from this project to the repository root.
3. In GitHub open **Settings → Pages**.
4. Choose **Deploy from a branch**.
5. Select `main` and `/ (root)`.
6. Save, then open the Pages URL.
7. Keep HTTPS enabled.

## Use it offline
The recommended offline workflow is to install the GitHub Pages version as a PWA.

### iPhone / iPad
1. While online, open the GitHub Pages URL in Safari.
2. Share → **Add to Home Screen**.
3. Launch the new app icon once while online.
4. After that, the application shell can load offline and your locally saved rosters/plans remain on that device.

### Desktop
Open the GitHub Pages URL in a browser that supports installed web apps and use its Install/App option.

## Privacy and backups
This version has no cloud database or account system. Data stays in browser storage on the device. Clearing site/browser data can erase it, so use **Export backup** regularly. Importing the JSON backup recreates the stored teams and match plans on another device.

## Recommended next modules
- Starting XI / bench substitution workflow
- Set-piece designer (corners, free kicks, throw-ins, kickoffs)
- Tactical arrows, zones, cones, goals, and annotations
- Per-player position library and depth chart
- Opponent scouting templates
- Match timeline and substitutions
- Session planner and drill library
- PDF / image match-day sheet export
- Video clip links and tagging
- Optional authenticated cloud sync for multiple coaches while preserving offline-first behavior
