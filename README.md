# Steve's Music Requests

Steve's Music Requests is a Windows desktop companion from PurgeCityProjects for Twitch song requests, Mixxx workflows, OBS Browser Sources, Now Playing, viewer rewards, stream alerts, announcements, Quick Actions, and optional VRM character output.

This repository is the public release, documentation, policy, and support home for Steve's Music Requests. The current release source is `Renalynn217/Twitch-Requests` branch `agent/fix-now-playing-auto-resolution` at commit `ed08bc3fee71945f107b225e8b1d6df6dc8680d4`.

## What It Does

- Connects to Twitch chat and Twitch EventSub for chat messages, Channel Point redemptions, and stream events.
- Handles song requests from chat or Channel Point rewards.
- Integrates with a separately installed stock Mixxx setup for music-library and queue workflows.
- Publishes local OBS Browser Source outputs, including Now Playing, announcements, event queue, alerts, and character output.
- Stores setup, Twitch authorization, logs, user configuration, and runtime data locally on the user's machine.

## Install

Use the official Windows release artifact from GitHub Releases when available:

<https://github.com/PurgeCityProjects/StevesRequests/releases>

Preferred artifact: `Steves-Music-Requests-<version>-x64-win.exe`

Zip fallback: `Steves-Music-Requests-<version>-x64-win.zip`

See [docs/installation.md](docs/installation.md) for the short install and first-run guide.

## First Run

1. Launch Steve's Music Requests.
2. Connect your Twitch channel and authorize Twitch.
3. Choose and scan your music-library folder.
4. Install/configure stock Mixxx if you use Mixxx request workflows.
5. Copy the OBS Browser Source URLs for the outputs you want.
6. Add your own character assets if you use Character Output.

## Build Facts

- Runtime: Electron / Node.js.
- Version source: `package.json` (`0.1.0` in the inspected release branch).
- Release command in source: `npm run release:win`.
- Windows packaging: Electron Builder NSIS installer plus zip fallback.

## Support

Use GitHub Issues for reproducible bugs and feature requests. Do not post Twitch tokens, OAuth data, logs with private data, music-library paths you want private, or other sensitive information.

## License

Steve's Music Requests is licensed under the [MIT License](LICENSE). Third-party components keep their own licenses.