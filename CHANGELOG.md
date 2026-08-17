# CineDock changelog

This file records user-visible changes in each published CineDock container release, beginning with
the Unraid Community Applications launch. Earlier builds were internal development versions and are
not part of the public release history. Git commit history remains the technical audit trail.

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
