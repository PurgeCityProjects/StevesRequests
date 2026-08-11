# Privacy

Steve's Music Requests is a desktop app. The inspected release source stores setup, Twitch authorization, configuration, logs, reports, and user data locally on the user's machine.

## Data Stored Locally

Steve may store:

- Twitch channel/account settings and authorization data.
- Music-library folder paths and scanned music-library metadata.
- Request queue state, viewer interaction settings, reward mappings, commands, alerts, and Quick Actions.
- OBS Browser Source settings and local output configuration.
- Mixxx-related settings and queue/readback state used by Steve.
- User-provided character models, animations, and audio assets placed into Steve's runtime folders.
- Local logs, diagnostics, crash-event logs, reports, browser session data, and cache/temp files.

Runtime data is stored outside the installed application folder by default and can be moved from the app's Advanced / Diagnostics settings.

## Network Connections

Verified network behavior includes:

- Twitch chat and Twitch EventSub connections.
- Twitch Helix API requests for configured Twitch features.
- Local HTTP servers for OBS Browser Source outputs such as Now Playing.
- Local or configured metadata requests for Mixxx, Icecast, Shoutcast, and stream metadata when those features are enabled.

## Telemetry And Crash Reports

The inspected Electron source starts crash reporting with `uploadToServer: false` and writes crash/diagnostic events locally. No dedicated analytics or telemetry upload service was identified in the inspected release source.

TODO: OWNER REVIEW REQUIRED - Confirm whether any future production updater, hosting page, download service, or external support tooling adds telemetry, analytics, or server-side logging.

## Sensitive Information

Do not share publicly:

- Twitch OAuth/access tokens or authorization files.
- Local runtime folder contents.
- Full logs or crash reports without review.
- Private music-library paths or filenames if you do not want them public.
- OBS/browser-source URLs if they reveal private local setup.
- User-provided assets you do not have rights to distribute.

## Retention

Runtime data remains on the user's machine and is preserved by uninstall. Users can remove the configured runtime folder manually if they want to delete local setup and logs.

TODO: OWNER REVIEW REQUIRED - Confirm final privacy contact and any formal data request process before the first public release.