# CineDock for Unraid

Community Applications metadata, the Unraid Docker template and the portable Docker Compose file
for CineDock. Also the home page for the CineDock app on the TrueNAS Apps catalogue.

**Website: <https://cinedock.tv>** — what it looks like, downloads for Windows, Mac and Fire TV, and the
setup guide. Help, common fixes and reporting a problem: <https://cinedock.tv/support>.

## Rediscover your library.

**CineDock gives Plex, Emby or Jellyfin an enhanced browsing experience on the NVIDIA Shield TV,
on an Amazon Fire TV Stick, on Zidoo media players, or in a browser on your computer or tablet.**

CineDock is a television-first interface for the Emby, Jellyfin or Plex server you already run. It uses
your existing server users, libraries, playback, transcoding, watched state and resume positions.
It does not scan, copy or modify media files.

Since 4.5, the Home screen belongs to each viewer: the **Collections** tab is a picker for
everything your server offers — your own collections, genres, library rows and CineDock's built-in
shelves — switched on and off and reordered per profile. Collections split across several libraries
are merged into one shelf, and Continue Watching can be moved or switched off like any other.

## Installation

CineDock is in Unraid Community Applications: open the **Apps** tab, search for **CineDock** and
click **Install**. This repository is the canonical template and submission source.

After installing, open `http://YOUR-UNRAID-IP:8945` and follow the setup wizard.

## TrueNAS

CineDock is in the official [TrueNAS Apps catalogue](https://apps.truenas.com/catalog/cinedock_community/)
(Community train, added 17 August 2026). On TrueNAS open **Apps > Discover Apps**, search for
**CineDock** and choose **Install**. Leave the WebUI port at the default `31080` (or pick another
free port), keep the default ixVolume for configuration storage, then open the app's **Web Portal**
or `http://YOUR-TRUENAS-IP:31080` and follow the setup wizard. Full walkthrough:
<https://cinedock.tv/guide>.

## Docker Compose and other platforms

The public image supports `linux/amd64` and `linux/arm64`. Download `compose.yaml`, then run:

```sh
docker compose up -d
```

Open `http://YOUR-DOCKER-HOST:8945` and follow the setup wizard. The same Compose file can be used
as a Portainer Stack, a Synology Container Manager Project, or a QNAP Container Station
Application. CineDock's settings are retained in the `cinedock_config` Docker volume.

Optional server/credential pairs (`EMBY_SERVER_URL` + `EMBY_API_KEY`, `JELLYFIN_SERVER_URL` +
`JELLYFIN_API_KEY`, or advanced `PLEX_SERVER_URL` + `PLEX_TOKEN`) keep
server credentials in the container; leave the television credential field blank when the matching
variable is configured. Plex account linking remains the recommended Plex setup route.

The Compose file uses `ghcr.io/cinedock/cinedock:latest`. The identical multi-platform image is
also mirrored publicly as [`getcinedock/cinedock:latest`](https://hub.docker.com/r/getcinedock/cinedock)
on Docker Hub.

- **Portainer:** open **Stacks**, add a stack, and paste or upload `compose.yaml`.
- **Synology DSM 7.2:** open **Container Manager > Project**, create a project, and select
  `compose.yaml` as its source.
- **QNAP:** open **Container Station > Create > Create Application**, then paste `compose.yaml`.

The CasaOS package has passed its local validator and is awaiting inclusion through
[CasaOS AppStore pull request #998](https://github.com/IceWhaleTech/CasaOS-AppStore/pull/998).

## Release history

See the [CineDock changelog](CHANGELOG.md) for user-visible changes in every published container
release since the Unraid Community Applications launch.

## Support

Use this repository's [issue tracker](https://github.com/cinedock/unraid-templates/issues) for
installation, template and application support.

## Fire TV / Shield / Zidoo app

The CineDock TV app is published separately at
[CineDock Downloads](https://github.com/cinedock/downloads/releases). It is tested on Amazon Fire TV
devices, NVIDIA Shield TV and the Zidoo Z9X 8K (on a Zidoo, from app 0.2.4 with container 4.3.3, it
plays through the box's own player).

## Support development

CineDock is free. If it is useful to you, you can optionally
[support its continued development](https://buymeacoffee.com/cinedock).
