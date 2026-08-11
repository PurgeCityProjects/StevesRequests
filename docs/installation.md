# Installation

This page documents the verified current deployment shape for SteveRequests and the remaining public-release packaging gaps.

Official releases should be downloaded only from:

<https://github.com/PurgeCityProjects/StevesRequests/releases>

No verified public installer, standalone binary, or packaged release artifact exists yet. Do not treat private development checkout steps as the final public installation method.

## Supported Platform Status

The development startup documentation and scripts are Windows-oriented and reference Windows 10/11 with PowerShell. The current backend is a Python FastAPI service that connects to PostgreSQL and is launched with Uvicorn/FastAPI CLI during development.

Verified runtime components:

- Windows 10/11 with PowerShell for the documented development startup flow.
- Python 3.11 or newer.
- PostgreSQL, with the current development documentation referencing PostgreSQL 18.
- A Python virtual environment containing FastAPI, Uvicorn, psycopg, python-dotenv, httpx, Pydantic, PyNaCl, and related dependencies.
- LSL scripts deployed into Second Life/OpenSim objects for in-world device behavior.

TODO: OWNER REVIEW REQUIRED - Confirm the final supported operating systems and whether non-Windows backend hosting is supported for public releases.

TODO: OWNER REVIEW REQUIRED - Publish a clean dependency file or packaged runtime for public releases. The development workspace references `requirements.txt`, but no verified `api/requirements.txt` file is present in the inspected project.

## Configuration Required

The backend reads configuration from environment variables, with `.env` support through `python-dotenv`.

Verified configuration names include:

- `DB_HOST`
- `DB_PORT`
- `DB_NAME`
- `DB_USER`
- `DB_PASSWORD`
- `API_WRITE_KEY`
- `MANAGER_API_KEY`
- `NETWORK_ID`
- `HEARTBEAT_TIMEOUT_SECONDS`
- `MONTHLY_FUNDING_GOAL_L`
- `MONTHLY_REPORT_DISCORD_WEBHOOK_URL`
- `DISCORD_PUBLIC_KEY`
- `DISCORD_ALLOWED_ROLE_IDS`
- `DISCORD_ALLOWED_USER_IDS`
- `DISCORD_APPLICATION_ID`
- `DISCORD_GUILD_ID`

Protect API keys, manager keys, database credentials, Discord keys, Discord webhook URLs, and any tunnel/public endpoint configuration. Do not post `.env` contents in public issues.

## Download

1. Open the GitHub Releases page.
2. Select the intended release version.
3. Download the release artifact for your operating system or deployment environment.

TODO: OWNER REVIEW REQUIRED - Add exact artifact names and platform mapping after the first public release package exists.

## Install

TODO: OWNER REVIEW REQUIRED - Add verified installation steps for the actual public release package format.

The current development implementation is started as a backend service from the API directory, using a Python virtual environment and a PostgreSQL database. Development notes also reference exposing the local backend through a Cloudflare tunnel for in-world object access, but no public production hosting model is confirmed yet.

Do not use placeholder commands as real installation instructions.

## First Launch And Setup

Before first launch, operators need:

- A configured PostgreSQL database for SteveRequests data.
- Backend environment variables for database access and API authentication.
- LSL scripts installed into the relevant Second Life/OpenSim objects.
- In-world objects configured to reach the backend URL and present the matching API key.
- Optional Discord configuration if Discord interactions or report delivery are used.

The backend includes startup schema creation/migration logic for several runtime tables, but public release setup should still include a verified database initialization process before the first release.

TODO: OWNER REVIEW REQUIRED - Provide a clean public first-run checklist after release packaging and hosting are finalized.

## Launch

The development startup flow launches the FastAPI app with Uvicorn or the FastAPI CLI from the backend API directory. The inspected development scripts bind the backend to localhost during development.

TODO: OWNER REVIEW REQUIRED - Confirm the public launch command, service manager, port, host binding, and production deployment pattern.

## Update

SteveRequests is intended to distribute public releases through GitHub Releases. Operators should update by installing the next official release artifact and applying any documented database or LSL deployment steps for that release.

The current implementation also contains backend endpoints and version maps for in-world script update manifests, but those component script versions are not a substitute for an application-level public release version.

TODO: OWNER REVIEW REQUIRED - Define the supported public update path after release packaging is confirmed.

## Uninstall

TODO: OWNER REVIEW REQUIRED - Add uninstall steps after packaging and deployment layout are confirmed.

A complete uninstall may need to account for the backend runtime, local environment files, PostgreSQL database/data directory, logs, and deployed in-world LSL scripts.

## Troubleshooting

If installation or startup fails, open a bug report and include:

- SteveRequests version or release artifact name.
- Operating system or hosting environment.
- Backend startup command or service type.
- PostgreSQL version and connection error text, with passwords removed.
- Whether the issue involves backend startup, database access, in-world object communication, Discord integration, media stream checks, or reporting.
- Relevant logs with secrets and personal information removed.

Do not include API keys, manager keys, database passwords, Discord webhook URLs, Discord public keys, tunnel URLs tied to private deployments, avatar data that is not needed for the report, or full private database dumps.
