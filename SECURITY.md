# Security Policy

## Reporting A Vulnerability

Do not post exploitable security details, Twitch tokens, private logs, or private runtime data in public GitHub Issues.

TODO: OWNER REVIEW REQUIRED - Confirm the private security reporting method before the first public release.

## Supported Versions

TODO: OWNER REVIEW REQUIRED - Add supported version information after the first public release.

| Version | Supported |
| ------- | --------- |
| No public release yet | Not applicable |

## Protect These Values

Users should protect:

- Twitch OAuth/access tokens and authorization files.
- Local runtime folders containing config, logs, browser session data, reports, and caches.
- Music-library paths and local file metadata if those are private.
- User-provided character models, animations, audio clips, and other assets.
- Local OBS Browser Source URLs when sharing screenshots or logs.
- Any private stream metadata endpoints configured for Icecast, Shoutcast, or local text metadata.

## Local Services

Steve serves local Browser Source outputs for OBS, including Now Playing and other stream outputs. These are intended for local OBS/browser use. Do not expose local Steve output ports to the public internet unless you understand the risk.

## Release Safety

Official releases should be downloaded from GitHub Releases for this repository. The Windows release source builds with Electron Builder and produces a Windows installer plus zip fallback.

The standard app release should not include private runtime config, Twitch tokens, logs, reports, development caches, private source history, optional custom Mixxx binaries, or rights-unverified character model/animation payloads.

## Public Issues

Public issues should not include:

- Twitch tokens or authorization files.
- Full runtime folders.
- Full logs with private data.
- Private music-library paths or filenames unless needed and intentionally shared.
- User-provided assets that are not yours to redistribute.
- Vulnerability exploit details before a fix is available.