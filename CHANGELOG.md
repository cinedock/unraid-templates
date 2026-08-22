# CineDock changelog

This file records user-visible changes in each published CineDock container release, beginning with
the Unraid Community Applications launch. Earlier builds were internal development versions and are
not part of the public release history. Git commit history remains the technical audit trail.

## 4.6.2 — 22 August 2026

**A maintenance release. Nothing changes on screen**, and the Fire TV / Shield / Zidoo app is
unchanged at 0.2.4 (`versionCode 6`).

- The container and the Windows and Mac editions are back on the same version number, where they
  were before 4.6.1. That release was a Windows-only fix published without a matching container,
  which briefly made "which version am I on?" a question with two answers.
- Behind the scenes, the version number now lives in a single file that every part of the build
  reads, rather than being written into nine separate places. Forgetting one of those nine is what
  made the 4.5.0 release fail after it had already published.

## Desktop 4.6.1 - 21 August 2026

**Windows and Mac editions only. The container stays at 4.6.0 and needs no update.**

- The tray menu's labels are visible again. On Windows the right-click menu appeared with its items
  working but no text on them, so there was no way to tell what any of them did.

## 4.6.0 — 21 August 2026

**Television series, seasons and episodes now live together on one page.**

- Programme details and actions sit beside the fixed, sound-on trailer window instead of being
  stranded at the top-left of the screen.
- Season buttons open their episodes directly, and episodes use wide still images with clear
  watched and focus states.
- Cast, extras and an owned-library **More Like This** shelf remain available further down the page.
- The old **More** prompt and its empty gap are gone. **Remove from Continue Watching** now has a
  centred row of its own so the main action row stays tidy.
- Film pages are unchanged.
- CineDock can now show a quiet, local-only notice when a newer TV app is available. It does not
  add a cloud service or send viewing information anywhere.
- Windows and Mac: running a newer build now replaces an older one that is still sitting in the tray, instead of reopening the old version - so upgrading is once again simply "run the new file". Closing the window for the first time now says, once, that CineDock keeps running in the tray. The tray menu has gained a Help & user guide item.
- Container, Windows and both macOS editions are now 4.6.0. The separately versioned TV app is
  unchanged at 0.2.4 (`versionCode 6`).

## 4.5.1 — 20 August 2026

**The desktop upgrade notice now takes you to the update.** 4.5.0's "Upgrade available" chip
announced a newer build but was not clickable, and older desktops' Settings link pointed at the TV
app's page. The chip now opens the right release page when clicked. Desktop editions only —
containers never show the notice, and nothing else changes.

## 4.5.0 — 20 August 2026

**Collections, and a Home that belongs to the viewer.**

- **Collections merged across libraries.** A collection split over several libraries — the same
  franchise in Films, TV and a box-set library — is now one shelf, with a line saying where its
  titles came from. Works on Emby, Jellyfin and Plex.
- **A Collections tab that is the chooser.** Pick what appears on Home and in what order, from
  everything your server offers — your own collections, genres, library rows and CineDock's
  built-in shelves. Collections you make yourself arrive switched on; anything CineDock guessed at
  arrives off and marked New, so Home never rearranges itself behind you.
- **Home is per viewer.** Each profile keeps its own arrangement.
- **Continue Watching can be moved or switched off.** It stays first by default but is no longer
  locked there; switched off, it returns to the top of the picker so it is easy to find again.
- **Desktop editions announce a newer build beside the version number** in the header, instead of
  only in a line inside Settings.
- Fixed: changing shelves could leave Home showing the old arrangement for up to ten minutes;
  switching Continue Watching back on needed a full reload; row headings sat under the selection
  glow of the row beneath.
- Television polish: a lighter selection band, menus as words rather than chips, and a quieter
  watched tick. Browsers, phones and the TV app (0.2.4) unchanged.

## 4.4.0 — 19 August 2026

**The More Info screen, finished — and a line drawn under 4.3.4 and 4.3.5.** Those two shipped the
redesigned ten-foot info screen; four defects found on a real television the same night pulled them
back within hours. 4.4.0 fixes all of them, fixes what was found checking the fix, and adds the
identity the page was missing. Browsers and phones are unchanged; the TV app is unchanged (0.2.4).

**Fixed (television)**
- The info-screen trailer is now seen, not only heard: on Fire TV the clip played on a hardware plane
  behind the page and the rounded, clipped box never left a hole for it. It now plays in a fixed
  layer over the box, exactly as the row previews always have. No "TRAILER" label.
- Up on a film no longer marks it watched: the ▲ shortcut belongs to the season and episode screens
  only; on the detail screen Up just steps out of the cast rail.
- The Spotlight artwork no longer vanishes after an info screen; the billboard comes back intact and
  its trailer resumes.
- Browse All: the A–Z rail is no longer a dead end; Home from the menu really goes Home; deeper amber
  selection and a slightly enlarged selected poster, so it reads over pale art.
- Plex "Recently Added" shows the programme, not "Season 1" / "Season 18".
- Confirm dialogs open in silence and the trailer returns afterwards; backgrounding the app stops the
  info-screen clip.

**New (television info screen)**
- Clearlogo from your server replaces the typeset title (Plex, Emby, Jellyfin); type stays if none.
- Ratings with their source — IMDb, Rotten Tomatoes critic/audience, TMDB or the plain star — only
  what the server recorded.
- Plex-style action buttons; the director's portrait; the Dolby mark on Dolby badges.

Known and unchanged: on Emby and Jellyfin the info-screen trailer plays only for titles with a local
trailer file; Jellyfin's first Home load is slow.

## 4.3.5 — 18 August 2026

**Completes the redesigned More Info screen released in 4.3.4 earlier the same day.** The trailer
described in that release did not actually play on a television. This fixes it. Nothing else is new.

- **The trailer on the info screen now plays.** In 4.3.4 it was built and guarded but held behind a
  check on a flag that the Plex connection never sets, so on Plex it could never start at all, and
  on Emby it started for only about a third of films. Measured across 25 films on each: Plex
  reported "has a trailer" for none of them while a real trailer existed for 20; Emby agreed with
  itself, 9 and 9. The screen now simply asks for the trailer, exactly as the main billboard has
  always done. Sound on, plays once, still starts after a short pause so browsing stays quiet, and
  still stops the moment you press Play, open the episode list or leave the page.
- **The TRAILER badge follows what is actually playing**, so it no longer stays hidden during a
  trailer or appears when there is none.
- **Audio badges drop the technical qualifier**: `5.1(side)` now reads `5.1`.

Browsers and phones are unchanged, and the Fire TV / Shield / Zidoo app is unchanged (0.2.4).

## 4.3.4 — 18 August 2026

**The More Info screen has been redesigned for televisions.** Browsers and phones are unchanged, and
the Fire TV / Shield / Zidoo app is unchanged (0.2.4 remains current) — this is a container update
only.

- **The whole page fits one screen.** It used to run to one and a half screens for a film and over
  three screens for a long-running series, so Cast, Extras and Episodes sat below the fold. Nothing
  is hidden now, for a film or a twenty-season series alike.
- **It reads from the sofa.** The large picture that took nearly two-thirds of the screen height is
  gone; the artwork is dimmed behind the page and the moving picture is boxed, so text never sits on
  top of a picture. The description is noticeably larger, and the layout uses the full width of the
  screen instead of leaving a third of it empty.
- **Media information is shown** — resolution, HDR or Dolby Vision, video codec, frame rate, and the
  audio format with its channel layout — for a film and for each individual episode. Only what your
  own server reports is shown; nothing is guessed.
- **Director, studio and country** are shown where they are known.
- **Seasons and episodes have their own screens.** The season picker opens on the season you are
  actually watching, marked "You are here", and the episode list opens on the next episode you have
  not seen, marked NEXT. Each season shows its own artwork. Pressing OK on an episode plays it.
- **Marking things watched is now obvious.** Up marks a film, a season or a single episode watched
  or unwatched, and the screen says so. It was always possible; nothing told you.
- **The two actions that cannot be undone now ask first** — marking a whole season watched, and
  removing a title from Continue Watching — with the safe answer already selected.
- **A trailer plays, with sound, on the info screen** when your server holds a trailer file for that
  title; otherwise the still image stays. It starts after a short pause so browsing stays quiet, and
  it stops as soon as you press Play, open the episode list or leave the page.
- Fixed: the close button in the corner could never be reached with a remote control. It is hidden
  on televisions, where Back has always closed the page; mouse and touch keep it.
- Fixed: opening the info screen could leave the main billboard trailer playing behind it, so two
  soundtracks played at once.

## Fire TV / Shield / Zidoo app 0.2.4 — 18 August 2026

A new APK. Installs over any earlier version in place (same signing certificate); your saved
CineDock address is kept.

- **Zidoo players are now supported.** On a Zidoo, pressing Play opens the film in the box's own
  player instead of CineDock's built-in one, so HDR / Dolby Vision, lossless audio passthrough and
  frame-rate switching behave exactly as they do for the box's local files. Your resume position is
  carried in, the finishing position is carried back to your media server, and a finished episode
  offers the next one. Nothing extra to install on the box (no PlexToZidoo or ZidooPlexMod), and
  nothing to configure. Tested on a Zidoo Z9X 8K; other Zidoo models with the same player are
  expected to work but are untested.
- On Fire TV, Shield and every other device the app behaves exactly as 0.2.3 — the Zidoo path is
  used only when a Zidoo player is present.
- Needs container 4.3.3 or later for the interface to display correctly on a Zidoo (below).

## 4.3.3 — 18 August 2026

Zidoo support release for the interface; no new features for other devices. Pairs with app 0.2.4
above.

- The interface now displays correctly on the Zidoo Z9X's built-in browser engine (an older
  Chromium). Two things were wrong there: CineDock mistook the Zidoo for a desktop computer (it
  reports a mouse-style pointer and carries no "Android TV" marker) and showed it the desktop layout;
  and that engine lacks a few newer layout features, so posters in the rows were invisible until a
  card was selected. Both fixed — the TV app now always gets the television layout, and the page
  detects the missing features and uses exact equivalents. Fire TV, Shield and browsers are
  unaffected (verified identical layout).
- Help page and README: Zidoo Z9X 8K added to the tested devices; the old "Zidoo not supported"
  warning replaced. Download links now point at the latest app release.

## 4.3.2 — 17 August 2026

Performance release; no new features. The Fire TV / Shield app is unchanged (0.2.3 is current).

- Fixed the long black wait on first launch. On Plex, building the Home screen asked the server for
  its whole personalised hub set, which Plex computes slowly when it has been idle (measured 10.5 s
  cold) — almost all of the 12–15 seconds a new Fire TV Stick waited for Home. "Recently Released"
  now comes straight from the movie libraries; the row keeps the same titles in the same order.
- Home is never rebuilt in front of you when any copy exists: an expired copy is shown at once and
  refreshed in the background, and Home is pre-warmed a few seconds after the container starts.
  Measured on a Fire TV Stick with an empty cache: whole first screen in under a second, from 15.

## 4.3.1 — 16 August 2026

Bug-fix release; no new features. The Fire TV / Shield app is unchanged (0.2.3 is current).

- Removed a leftover bar that CineDock never used: on a TV app's first three launches an empty navy
  band with a blue line sat over the top menu for up to 45 seconds. New installs saw it every time.
- Fixed the Search and Requests pages opening with their heading and input partly under the header.
- The in-app help page now points at the new support page, cinedock.tv/support.

## Fire TV / Shield app 0.2.3 — 16 August 2026

A new APK. Installs over any earlier version in place (same signing certificate); your saved
CineDock address is kept.

- Fixed the app closing mid-film on 1 GB Fire TV Sticks (Fire TV Stick HD): the player could run
  out of memory because the app was limited to 128 MB of Java heap while holding both the
  interface and up to three minutes of buffered video. The app now requests the large heap and,
  on low-memory devices, buffers 30–90 seconds instead of 50–180 seconds.
- The container is unchanged; the interface still comes from it, so this APK does not need
  reinstalling for container updates.

## 4.3.0 — 16 August 2026

Major feature release: browse your whole library.

- Added **Browse All** — every library opens as a full poster grid of its entire contents, sorted by
  Title A–Z, Recently added, Release date or Rating, with an Unwatched filter and a genre filter.
  The grid is paged and windowed so a 15,000-title library stays usable on a Fire TV Stick.
- Added an **A–Z rail** for jumping straight to any letter; offsets come from the media server, so a
  jump to T lands on the first T.
- Added a **Genres** page listing every genre a library actually contains, with title counts and
  artwork, opening straight into the filtered grid.
- Added **See all** on repeatable-query rows (New Releases, Recently Added, each genre): press Left
  from the first tile of a shelf, or choose the card at the end of the row.
- Added a library sub-menu as a second line of the top menu carrying Browse All and Genres.
- All of the above work on Emby, Jellyfin and Plex, verified against each; the letter index sums
  exactly to the library total on all three.
- Every tab now uses the inset billboard composition Home already used.
- `?tv=1` / `?tv=0` / `?tv=auto` on the address force or restore the ten-foot layout.
- Fixed, from testing on a real Fire TV Stick: the A–Z rail sitting inside the television's
  overscan crop; "#" and "A" falling off the top of the rail; the grid opening a fifth of a
  screen down; the "you are here" letter lagging one behind the selection; the billboard trailer
  playing invisibly while focus was on the library menu; header controls running under the rail.
- CineDock TV app unchanged (0.2.2) — it loads the interface from the container, so existing
  installs pick this up on next launch.

## 4.2.1 — 14 August 2026

- Fixed Plex poster and backdrop delivery: the photo-transcode request now always supplies both
  width and height, so artwork arrives at the requested display size instead of silently falling
  back to full-resolution originals (measured 96.9% smaller posters, 93.0% smaller backdrops;
  shelves paint markedly faster on television devices).
- Versioned the artwork cache key so previously cached full-resolution images are not served after
  the fix.
- Wired the Hidden Gems and Short and Sweet smart collections into the Plex Home screen; the
  recipes shipped in 4.2.0 but were only reachable from Emby and Jellyfin.
- Enabled the "Create CineDock smart collections for me" Settings checkbox for Plex owners and
  removed the stale "(coming to Plex)" notice.

## 4.2.0 — 13 August 2026

Major feature release.

- Added chapter preview images for media available through a read-only local media mount. CineDock
  bundles ffmpeg, discovers common mount layouts automatically and keeps generated images in a
  size-capped cache. Existing Jellyfin trickplay support remains available.
- Added CineDock-managed **Hidden Gems** and **Short and Sweet** smart collections across Plex, Emby
  and Jellyfin, with balanced results from multiple libraries.
- Promoted Watchlist to a first-class top-navigation destination and removed the duplicate Home
  shelf and poster/Spotlight controls. Items can still be added or removed from More Info.
- Retained the faster Plex artwork delivery introduced in 4.1.7.

## 4.1.7 — 12 August 2026

- Fixed Plex poster requests downloading the full original artwork when a small poster was needed.
- Routed Plex artwork through the photo transcoder, reducing a measured 4.8 MB poster to about
  33 KB and removing the recurring 20–30 second delay while television shelves filled in.
- Preserved a fail-soft fallback so artwork still appears if a Plex server cannot transcode it.
- Kept Emby and Jellyfin artwork handling unchanged because those servers already honour their
  requested image size.

## 4.1.6 — 11 August 2026

- Restored transparent navigation over Spotlight artwork at the top of Home, Films and TV.
- Made navigation and the poster-bleed mask turn true black while browsing shelves and on pages
  without a Spotlight.
- Removed the television-only font clamps that caused inconsistent sizing at 720p, 1080p and 4K.
- Adopted the field-tested television proportions used by ManchVideo for posters, rows, navigation
  spacing and library Spotlights while retaining CineDock's gold identity and inset Home layout.
- Corrected device guidance: Fire TV and NVIDIA Shield are identified as tested; other Android TV
  and Google TV devices are described as expected to work but untested; the incorrect Zidoo support
  claim was removed.

## 4.1.5 — 11 August 2026

- Deduplicated simultaneous section requests so the same library work is not repeated in flight.
- Began warming Films and TV after Home becomes usable, reducing the delay on first opening them.
- Rendered large browser libraries progressively in four-shelf chunks instead of constructing every
  card before showing the page.

## 4.1.4 — 10 August 2026

- Added the approved inset Spotlight presentation on Home and persistent true-black navigation with
  a solid shelf mask.
- Improved person biographies, filmography grid navigation and Back history from an actor to the
  previously selected film or series.
- Made labels, dates and profile reporting clearer and more accurate.
- Revised public setup and no-media guidance.

## 4.1.3 — 9 August 2026

- Closed the remaining delayed row-preview race so a trailer lookup that finishes after CineDock is
  backgrounded cannot create media or restart sound over another app.
- Restricted container-stored Plex, Emby and Jellyfin credentials to their matching configured
  server addresses; a browser-supplied address can no longer receive a stored server secret.
- Restricted relayed Plex HLS manifests, segments and redirects to the configured Plex origin so a
  Plex token is never forwarded to a foreign host.
- Repaired the container-configured Plex path: a blank candidate list now uses the configured Plex
  address, and Home-user/PIN switching can use the stored owner token without exposing it to the
  setup page.
- Bound Plex account-link polling and QR codes to the browser session that started them, and
  cancelled abandoned polling when the wizard is closed or the server type changes.
- Preserved TMDB, progress-reporting and collection preferences when changing server or user.
- Added clear handling for servers that return no selectable users.
- Made container publication run the complete test suite and a built-image smoke test before
  publishing multi-architecture images from an immutable release tag.

## 4.1.2 — 9 August 2026

- Ported ManchVideo's visibility lifecycle handling so active Spotlight and row trailers stop
  immediately when CineDock is backgrounded. The remaining in-flight row lookup race was closed in
  4.1.3.
- Added the boot-hidden media sweep for Android TV WebViews opened without foreground visibility.

## 4.1.1 / CineDock TV 0.2.2 — 9 August 2026

- Added container fields for Plex, Emby and Jellyfin server addresses and credentials, plus TMDB,
  so configured servers can be selected without retyping credentials on the television.
- Improved the television setup wizard's focus visibility, user selection and single-user flow.
- Added secure Plex account linking and clearer TV guidance; account linking remains the fallback
  when a stored Plex-token profile does not open directly on NVIDIA Shield.
- Expanded plain-English setup, trailer, extras and supported-device guidance.
- Published CineDock TV version code 4 with the permanent signing identity used by earlier releases.

## 4.1.0 / CineDock TV 0.2.1 — 8 August 2026

- Reworked Spotlight using the proven ManchVideo full-bleed presentation.
- Balanced Spotlight choices across releases, anticipated titles and the wider library instead of
  simply mirroring the first shelf.
- Let real trailers run to completion; static artwork advances after 25 seconds.
- Added left/right Spotlight browsing, OK for More Info and right-click for the next title.
- Improved cast biography loading with staged rendering and caching.
- Added the shelf-first phone companion layout without changing the television/desktop layout.
- Replaced the obsolete `BETA` label with the running container version.
- Made CineDock TV claim music audio focus during cold launch and resume so the first trailer does
  not remain silent until a D-pad event.
- Restored self-hosted Spotlight trailers in CineDock TV after a retired Samsung/Tizen flag had
  incorrectly disabled them whenever the native TV bridge was detected.
- Added a user guide explaining recognised trailer and extras layouts, playable sources, television
  limitations and media-server rescanning.

## 4.0.2 / CineDock TV 0.2.0 — 7 August 2026

- Added Plex alongside Emby and Jellyfin, including household users, watch state and collections.
- Added CineDock TV playback with native audio-track, subtitle, surround and HDR handling.
- Added television D-pad navigation, guarded exit and public TV setup/help guidance.
- Published matching AMD64 and ARM64 container images to GHCR and Docker Hub.

## 4.0.1 — 7 August 2026

Initial public launch through Unraid Community Applications.

- Made CineDock installable from the Unraid Apps tab using the public container and persistent
  configuration storage.
- Verified a clean Community Applications installation and first-time connection flow.
- Made **Get CineDock on my TV** the first Settings item so owners could find the television download
  and illustrated setup guide immediately after configuring the container.
- Added structured public support forms for Docker/setup, TV playback and feature requests.
