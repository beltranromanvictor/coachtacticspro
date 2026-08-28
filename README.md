# Coach Tactics Pro — v2

An offline-first soccer tactical board and match-planning PWA for multiple teams and game formats.

## What's new in v2

- Multi-team workspace (Oregon SC, Randos, Spartak seeded by default)
- 11v11, 9v9, 8v8, 7v7, 6v6 and 5v5 formats
- Roster + bench substitution workflow
- Player details: name, number, role, primary position, preferred foot, availability
- Formation presets
- Drag players and ball
- Opponent overlay
- 5 attacking lanes / 3 defensive lanes with left-center-right bias
- Shift + drag tactical arrows
- Tactical moments (build-up, progression, final third, transitions, pressing, set pieces)
- Timeline with reorder, duplicate and delete controls
- Animated phase-to-phase movement
- Tactical Library for reusable sequences
- Match Day Console
- Match-plan archive on the device
- **Save + Download Match Plan**: every saved game automatically downloads its own `.matchplan.json` file
- Import a single match-plan file
- Full-app backup / restore
- Offline PWA cache via service worker

## Match-plan files

Saving a match creates a portable file such as:

`Oregon_SC_vs_Middleton_2026-09-05.matchplan.json`

It includes the team, roster, starting lineup, game format, formation, opponent, date, venue, competition, objectives, set-piece notes, tactical phases, player coordinates and animation sequence.

Use **Open match-plan file** inside the app to load one later.

## Deploy on GitHub Pages

Upload the entire contents of this folder to the root of your GitHub Pages repository. GitHub Pages must serve the files over HTTPS.

After replacing an older version, open the live GitHub Pages URL while connected to the internet and refresh it once or twice. v2 uses a new service-worker cache name (`coach-tactics-pro-v2`), so the old application cache is removed during activation.

## Install the GitHub Pages version for offline use

The recommended offline workflow is **not** to download `index.html` from GitHub and open it as a local file. Service workers are designed for secure origins such as HTTPS; your GitHub Pages site already provides that environment.

### iPhone / iPad

1. Publish/update the repository in GitHub Pages.
2. While online, open the **GitHub Pages URL** in Safari (not the repository page on github.com).
3. Let the app load completely.
4. Tap **Share**.
5. Choose **Add to Home Screen**.
6. Enable **Open as Web App** if shown.
7. Tap **Add**.
8. Open Coach Tactics Pro from the new Home Screen icon once while still online.
9. Test it: turn on Airplane Mode and reopen the Home Screen app.

The interface files are cached by the service worker. Your rosters, library and match archive live in local browser storage on that device.

### Mac / Windows / Chromebook with Chrome

1. Open the GitHub Pages URL in Chrome while online.
2. Open Chrome's menu.
3. Choose **Cast, save and share → Install page as app…** (wording may vary slightly), or use the install icon in the address bar when available.
4. Install the app.
5. Launch it once online.
6. Disconnect from Wi-Fi and launch it again to verify offline access.

### Updating an installed offline copy

When you push a new app version to GitHub:

1. Reconnect the device to the internet.
2. Open the installed app.
3. Leave it open long enough for the service worker to check the GitHub Pages files.
4. Close and reopen the app. A refresh may be needed for major updates.

Your local team data remains separate from the cached app files. Still, use **Full backup** before major updates or periodically during the season.

## Data and privacy

There is no backend in this version. GitHub hosts the application code only. Player names, plans, lineups and notes are stored locally on each device. They are not automatically synchronized between devices.

Use:

- **Full backup** for all teams, matches and tactical library data.
- **Save + download match plan** for a portable copy of one game.

Browser/site data can be cleared by the operating system or user, so downloaded backups should be treated as the durable copy.

## v3 animation controls

The animation timeline now supports presentation controls for coaching sessions:

- Speed: 0.25x, 0.5x, 0.75x, 1x, 1.5x, 2x
- Pause / resume during playback
- Previous / Next phase buttons
- Keyboard shortcuts: Left Arrow = previous phase, Right Arrow = next phase, Space = pause/resume
- Phase indicator showing current phase / total phases
- Keyboard shortcuts are ignored while typing in a text field, number field, textarea, or select.

### Updating an already-installed desktop PWA

1. Replace the files in your GitHub Pages repository with the new version, keeping the same paths.
2. Wait for GitHub Pages to finish deploying.
3. Open the installed Coach Tactics Pro desktop app while connected to the internet.
4. Leave it open briefly so the browser can download and activate the new service worker/cache.
5. Close the app completely and open it again.
6. Confirm that the animation controls now show the speed selector and Previous/Pause/Next buttons.
7. If the old version remains, open the GitHub Pages URL in the browser, refresh once, then close and reopen the installed app.

The v3 service worker uses a new cache name (`coach-tactics-pro-v3`), so it removes the old application cache after activation. Your rosters and match plans are stored separately in browser local storage and are not intentionally erased by this application update. As a precaution, use **Full backup** before major updates.


## v4 — Smooth Presentation controls

- Saved phases are now treated as **keyframes**.
- Left / Right arrows move one interpolation frame at a time instead of jumping directly between phases.
- Shift + Left / Right jumps to the previous / next keyframe.
- Click any saved phase to start playback from that keyframe.
- The timeline slider can scrub to any point in the sequence.
- **Play from here** starts from the current frame rather than forcing playback from Phase 1.
- Presentation Mode enlarges the pitch and hides the planning panels while preserving keyboard controls.
- Escape exits Presentation Mode.
- The normal interface places the pitch across the full top width; squad, timeline, library, and match tools begin below.

### Keyboard
- `←` previous animation frame
- `→` next animation frame
- `Shift + ←` previous saved keyframe
- `Shift + →` next saved keyframe
- `Space` play / pause
- `Escape` exit Presentation Mode

### Updating an already installed desktop PWA to v4
1. Replace the repository files with the contents of this v4 package and push/commit.
2. Wait until GitHub Pages shows `v4 · smooth presentation · offline first`.
3. Open the installed desktop app while online.
4. Close it completely and reopen it once.
5. The v4 service worker uses a new cache name (`coach-tactics-pro-v4`) and removes older app caches while preserving local roster/match data.
6. Make a Full Backup before major updates as a precaution.
