# Installation

This page documents the verified current deployment shape for SteveRequests and the public ZIP release model established in the private development workspace.

Official releases should be downloaded only from:

<https://github.com/PurgeCityProjects/StevesRequests/releases>

No public release has been published yet. Do not use private development checkout paths or private database contents as an installation method.

## Supported Platform Status

The documented operator workflow is currently Windows-oriented.

Verified runtime components:

- Windows 10/11 with PowerShell for the documented operator workflow.
- Python 3.11 or newer.
- PostgreSQL, with the development environment using PostgreSQL 18.
- Python dependencies installed from `api/requirements.txt` in the release artifact.
- LSL scripts deployed into Second Life/OpenSim objects for in-world device behavior.

TODO: OWNER REVIEW REQUIRED - Confirm whether Linux hosting, Docker, managed PostgreSQL, or other deployment targets are officially supported.

## Release Artifact

The verified public artifact format is a versioned ZIP source distribution generated from the private development workspace. The candidate artifact built during release-process validation included:

- `api/main.py`
- `api/requirements.txt`
- `api/.env.example`
- `sql/`
- `manifests/`
- `lsl/`
- public install/update/uninstall/release docs
- `VERSION.txt`
- `RELEASE_CONTENTS.txt`

The candidate audit verified that the package excluded Git history, real `.env` files, live database data, database dumps, logs, caches, virtual environments, patch backups, generated internal artifact packs, and known private secret patterns.

## Configuration Required

The backend reads configuration from environment variables, with `.env` support through `python-dotenv`. Public releases should include `api/.env.example`; operators copy it to `api/.env` and fill in deployment-specific values.

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
- `PRESENCE_TIMEOUT_SECONDS`
- `STALE_CLOSE_INTERVAL_SECONDS`
- `DEFAULT_DEVICE_TYPE`
- `MONTHLY_INCOME_REPORT_ENABLED`
- `MONTHLY_FUNDING_GOAL_L`
- `MONTHLY_REPORT_DISCORD_WEBHOOK_URL`
- `DISCORD_PUBLIC_KEY`
- `DISCORD_ALLOWED_ROLE_IDS`
- `DISCORD_ALLOWED_USER_IDS`
- `DISCORD_APPLICATION_ID`
- `DISCORD_GUILD_ID`
- media stream check timeout/user-agent settings

Protect API keys, manager keys, database credentials, Discord keys, Discord webhook URLs, public tunnel/deployment URLs, and any API keys copied into LSL scripts. Do not post `.env` contents in public issues.

## Install Application Files

1. Download the official ZIP artifact from GitHub Releases.
2. Extract it to an installation directory, for example `C:\SteveRequests`.
3. Open PowerShell in the extracted directory.
4. Create a Python virtual environment:

```powershell
python -m venv .venv
```

5. Activate it:

```powershell
.\.venv\Scripts\Activate.ps1
```

6. Install dependencies:

```powershell
python -m pip install --upgrade pip
python -m pip install -r .\api\requirements.txt
```

## Configure

1. Copy `api\.env.example` to `api\.env`.
2. Fill in database settings and generated secrets.
3. Keep `api\.env` private.

Generate API secrets with a password manager or a command such as:

```powershell
python -c "import secrets; print(secrets.token_urlsafe(48))"
```

## PostgreSQL Setup

Create a PostgreSQL database and user for SteveRequests. Configure `api\.env` with the database connection settings.

The backend creates and upgrades many runtime tables on startup with `CREATE TABLE IF NOT EXISTS` and `ALTER TABLE` logic in `api/main.py`. The v2 updater manifest/version-map seed data is provided in the release SQL files:

- `sql/PHASE_1_FASTAPI_V2_SEED_SQL_2026_04_19.sql`
- `sql/PHASE_1_FASTAPI_V2_CONNECTION_SEED_UPDATE_2026_04_19.sql`

Apply those SQL files after schema creation and before relying on the v2 updater manifest/version-map endpoints.

TODO: OWNER REVIEW REQUIRED - Decide whether to keep the current phase-named SQL files or rename them into a stable public migration sequence before the first real release.

## Launch

From the extracted release directory:

```powershell
cd .\api
..\.venv\Scripts\python.exe -m uvicorn main:app --host 127.0.0.1 --port 8000
```

If the virtual environment is already activated, this equivalent command can be used from `api`:

```powershell
python -m uvicorn main:app --host 127.0.0.1 --port 8000
```

## Verify

In another PowerShell window:

```powershell
Invoke-RestMethod http://127.0.0.1:8000/health
Invoke-RestMethod http://127.0.0.1:8000/version
```

The health endpoint should return `ok: true`, `app_name: SteveRequests`, and the configured application version.

## LSL / Device Setup

The release package includes LSL scripts under `lsl/` grouped by script family. Operators must deploy the relevant scripts into Second Life/OpenSim objects and configure the object connection URL/API key for the backend deployment.

The development source was changed so release LSL scripts use placeholders instead of hard-coded production endpoint/key values. Operators must set deployment-specific values before in-world use.

## Network / Firewall

The backend must be reachable by the in-world objects. Localhost-only startup is appropriate for local testing, but production or in-world use requires a reachable HTTPS endpoint or tunnel configured by the operator.

Do not publish private tunnel URLs or API keys in public issues.

## Update

Use one update process: install the next official ZIP release over application files while preserving operator-owned configuration, secrets, PostgreSQL data, backups, logs, and service definitions.

At a high level:

1. Back up PostgreSQL and `api/.env`.
2. Stop the backend.
3. Extract the new release.
4. Replace application files while preserving configuration/secrets.
5. Reinstall dependencies from `api/requirements.txt`.
6. Apply release-specific SQL migrations or seed updates.
7. Restart and verify `/health` and `/version`.
8. Deploy updated LSL scripts if release notes require them.

TODO: OWNER REVIEW REQUIRED - Define formal supported-version and rollback policy before first public release.

## Uninstall

Stop the backend, then remove application files if they are no longer needed.

Treat these separately:

- application files and local virtual environment
- `api/.env` and other secrets
- PostgreSQL database/data/backups
- backend/PostgreSQL/service logs
- deployed in-world LSL scripts

Dropping the PostgreSQL database is destructive. Back it up first if records may be needed later.

## Troubleshooting

If installation or startup fails, open a bug report and include:

- SteveRequests version or release artifact name.
- Operating system or hosting environment.
- Backend startup command or service type.
- PostgreSQL version and connection error text, with passwords removed.
- Whether the issue involves backend startup, database access, in-world object communication, Discord integration, media stream checks, reporting, or LSL deployment.
- Relevant logs with secrets and personal information removed.

Do not include API keys, manager keys, database passwords, Discord webhook URLs, Discord public keys, tunnel URLs tied to private deployments, avatar data that is not needed for the report, full private database dumps, or full `.env` files.
