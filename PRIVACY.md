# Privacy

This privacy document is a public-facing skeleton for SteveRequests. It must be reviewed and completed before the first public release.

TODO: OWNER REVIEW REQUIRED - Confirm the final privacy wording, retention policy, user rights process, privacy contact, and any deployment-specific data handling before release.

## Verified Data Handling In The Current Implementation

The current SteveRequests implementation is a FastAPI backend backed by PostgreSQL. It receives and stores data needed for Second Life/OpenSim accounting and device management.

Verified categories handled by the backend include:

- Second Life/OpenSim avatar identifiers and names used for staff, renters, managers, admins, owners, device actors, and payments.
- Device identifiers, labels, device types, runtime object keys, live claim tokens, heartbeat timestamps, initialization state, and configuration revision data.
- Tip, donation, rent, payout, refund, manager-withdrawal, lease, rental unit, and accounting event data, including Linden dollar amounts and timestamps.
- Staff session information, including role, login/logout state, AFK state, presence, elapsed time, and payout/accounting calculations.
- Profile media values such as image UUIDs and DJ stream URLs when users/operators configure them.
- System, device, role, manifest, version-map, and mutation audit records.
- Optional Discord user IDs, role IDs, usernames/display names from interaction payloads, and Discord report delivery status when Discord integration is configured.

## Local Storage

The backend stores application data in PostgreSQL. The inspected development workspace also contains a local PostgreSQL data directory and PostgreSQL log files.

The backend reads environment configuration through environment variables and `.env` support. The `.env` file can contain database credentials, API keys, manager keys, Discord configuration, and webhook URLs.

TODO: OWNER REVIEW REQUIRED - Confirm the final public deployment storage locations for packaged releases.

## Network Requests And Third-Party Services

Verified network behavior includes:

- The backend serves HTTP API endpoints for in-world Second Life/OpenSim scripts and operator/admin clients.
- The backend connects to PostgreSQL for persistent storage.
- Optional Discord integration verifies Discord interaction signatures when configured.
- Optional scheduled report delivery posts report text to a configured Discord webhook URL.
- Media stream health checks make outbound HTTP requests to operator-configured stream URLs and playlist URLs.
- Development notes reference use of a Cloudflare tunnel to expose a local backend to in-world scripts, but no public production hosting model is confirmed.

No verified Twitch or OBS integration was found in the inspected current implementation.

TODO: OWNER REVIEW REQUIRED - Confirm whether any production deployment sends data to additional hosting providers, monitoring systems, backup systems, or other services.

## Credentials And Sensitive Configuration

The implementation uses API keys and manager keys to authorize backend writes and admin/manager actions. It may also use database credentials, Discord configuration values, Discord webhook URLs, and live device claim tokens.

Users and operators should protect:

- `.env` files and environment variable dumps.
- Database passwords and connection details.
- `API_WRITE_KEY` and `MANAGER_API_KEY` values.
- Discord webhook URLs, public keys, application IDs, guild IDs, allowed role IDs, and allowed user IDs.
- Public tunnel URLs or deployment URLs that are tied to private deployments.
- Database backups and logs that contain avatar, payment, session, or device data.

## Logs

Verified logging behavior includes backend messages printed to the server terminal and PostgreSQL logs in the development data directory. The development workspace also contains historical patch/update diagnostic logs.

TODO: OWNER REVIEW REQUIRED - Confirm final packaged-release log locations and retention behavior.

## Telemetry, Analytics, Crash Reporting, And Tracking

No dedicated analytics, telemetry, crash-reporting, or tracking service was identified in the inspected current implementation. The development virtual environment contains `sentry-sdk`, but no verified application initialization or use of Sentry was found in `api/main.py`.

TODO: OWNER REVIEW REQUIRED - Confirm whether production packaging, hosting, or future releases enable analytics, telemetry, crash reporting, monitoring, or tracking outside the inspected backend code.

## Retention And Deletion

The implementation stores accounting, device, session, role, rental, and audit data in PostgreSQL. Automatic retention/deletion behavior was not established from the inspected code.

TODO: OWNER REVIEW REQUIRED - Define retention periods, backup retention, deletion request handling, and any records that must be retained for accounting or operational reasons.

## Public Issue Safety

Users should not submit credentials, API keys, access tokens, private account data, avatar/payment records, database dumps, full logs, tunnel URLs, Discord webhook URLs, or other sensitive information through public GitHub Issues.

## Contact

TODO: OWNER REVIEW REQUIRED - Add the correct privacy contact method for Purge City Projects.

## Legal Review

This document is not final legal advice. Purge City Projects should review it for accuracy before publishing the first public release.
