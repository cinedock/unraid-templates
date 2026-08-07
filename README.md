# CineDock for Unraid

Community Applications metadata, the Unraid Docker template and the portable Docker Compose file
for CineDock.

CineDock is a television-first interface for the Emby, Jellyfin or Plex server you already run. It uses
your existing server users, libraries, playback, transcoding, watched state and resume positions.
It does not scan, copy or modify media files.

## Installation

The Community Applications submission was auto-approved on 6 August 2026. CineDock will become
searchable in the Unraid Apps tab after the next catalog build publishes. This repository is the
canonical template and submission source.

After installing, open `http://YOUR-UNRAID-IP:8945` and follow the setup wizard.

## Docker Compose and other platforms

The public image supports `linux/amd64` and `linux/arm64`. Download `compose.yaml`, then run:

```sh
docker compose up -d
```

Open `http://YOUR-DOCKER-HOST:8945` and follow the setup wizard. The same Compose file can be used
as a Portainer Stack, a Synology Container Manager Project, or a QNAP Container Station
Application. CineDock's settings are retained in the `cinedock_config` Docker volume.

- **Portainer:** open **Stacks**, add a stack, and paste or upload `compose.yaml`.
- **Synology DSM 7.2:** open **Container Manager > Project**, create a project, and select
  `compose.yaml` as its source.
- **QNAP:** open **Container Station > Create > Create Application**, then paste `compose.yaml`.

CasaOS packaging will follow after the common Compose installation has been tested on both amd64
and arm64 hardware.

## Support

Use this repository's [issue tracker](https://github.com/cinedock/unraid-templates/issues) for
installation, template and application support.

## TV app

The optional Android TV preview is published separately at
[CineDock Downloads](https://github.com/cinedock/downloads/releases).

## Support development

CineDock is free. If it is useful to you, you can optionally
[support its continued development](https://buymeacoffee.com/cinedock).
