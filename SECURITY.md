# Security Policy

## Reporting A Vulnerability

Please do not publicly disclose exploitable security vulnerabilities in GitHub Issues before Purge City Projects has had a reasonable opportunity to investigate and respond.

TODO: OWNER REVIEW REQUIRED - Confirm the preferred private security reporting method, such as GitHub private vulnerability reporting or a dedicated security contact.

Until a private reporting method is verified, users should avoid posting exploit details, credentials, tokens, private logs, or sensitive account information in public issues.

## Supported Versions

TODO: OWNER REVIEW REQUIRED - Add supported version information after the first public release exists.

| Version | Supported |
| ------- | --------- |
| No public release yet | Not applicable |

## Verified Security-Sensitive Areas

The current implementation is a backend service with authenticated write/admin endpoints, a PostgreSQL database, optional Discord integration, media stream checks, and Second Life/OpenSim object communication.

Protect the following configuration and runtime data:

- Backend API keys, including `API_WRITE_KEY` and `MANAGER_API_KEY`.
- Database credentials and PostgreSQL data directories/backups.
- `.env` files and environment variable dumps.
- Discord webhook URLs and Discord integration configuration.
- Public tunnel URLs or deployment URLs used to expose private backend instances.
- Device live claim tokens, runtime object keys, and API configuration embedded in in-world scripts.
- Logs or database exports containing avatar identifiers, names, payment/accounting records, session data, rental data, or device state.

## Release Package Controls

The private development release builder stages a ZIP artifact and audits it before publication. The candidate audit verified exclusion of `.git`, real `.env` files, live database data, database dumps, logs, caches, virtual environments, patch backups, generated internal artifact packs, and known private secret patterns.

The LSL connection scripts were changed for release readiness so they use deployment placeholders rather than hard-coded production endpoint/API-key values, and the connection script no longer prints the API key in owner chat.

## Backend Exposure

The backend exposes HTTP API endpoints for in-world scripts and operator/admin workflows. Write and manager/report endpoints require API-key headers in the implementation, but deployment operators are still responsible for protecting the backend URL, API keys, database, and hosting environment.

If a local development backend is exposed through a tunnel or public URL, treat that URL and its API key as sensitive. Rotate keys if they are posted publicly or shared with untrusted parties.

## Public Issues

Public GitHub Issues may be used for general bugs and feature requests, but they should not contain:

- Exploit details.
- API keys, manager keys, database credentials, webhook URLs, or OAuth-style secrets.
- Private account data or private avatar/payment/session/rental records.
- Full logs containing sensitive values.
- Database dumps or backups.
- Personal information.

## Security Updates

Security fixes should be documented in GitHub Releases and [CHANGELOG.md](CHANGELOG.md) when appropriate, without exposing unnecessary exploit details.

TODO: OWNER REVIEW REQUIRED - Confirm whether GitHub private vulnerability reporting will be enabled for this repository.
