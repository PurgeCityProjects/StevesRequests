# SteveRequests

SteveRequests is the official public release and support repository for SteveRequests, maintained by Purge City Projects.

This repository is the public distribution and support surface for SteveRequests. It is not the private development or source-of-truth repository. Development history, internal implementation work, private configuration, credentials, and development-only material are intentionally not published here.

## What Is SteveRequests?

SteveRequests is a backend-centered Second Life/OpenSim accounting and device-management system. The current implementation uses a FastAPI backend with PostgreSQL storage and LSL scripts for in-world objects.

Verified user-facing areas in the current implementation include:

- Device registration, bootstrap, heartbeat, configuration, and update manifest/version-map endpoints for in-world objects.
- Tip jar session tracking for manager, DJ, host, and dancer roles.
- Tip, donation, payout, refund, rent, rental unit, lease, renter, and manager-withdrawal accounting records.
- Admin and manager role management.
- Rental terminal, donation terminal, adboard terminal, and tip jar device types.
- Media/radio station state and stream health checks.
- Staff, income, open-session, and accounting reports.
- Optional Discord interaction/report integration when configured by the operator.

This README describes what users and operators need to know about public releases. It does not document private development architecture, internal history, or private deployment configuration.

## Official Releases

Official SteveRequests releases should be obtained only from this repository's GitHub Releases page:

<https://github.com/PurgeCityProjects/StevesRequests/releases>

Do not download SteveRequests installers, binaries, packages, or archives from unofficial mirrors, private links, chat attachments, or third-party redistribution sites unless Purge City Projects explicitly identifies them as official.

At the time this repository structure was created, no real public release has been published. The private development workspace now has an application-level version source in `api/main.py` (`__version__`), currently set to the unreleased sentinel `0.0.0+unreleased`. Do not create a version tag or GitHub Release from that sentinel.

## Release Model

SteveRequests public distribution is intended to use GitHub Releases.

The current verified release artifact model is a versioned ZIP source distribution. That matches the actual architecture: a Python FastAPI backend, PostgreSQL initialization/seed SQL, and LSL scripts that operators deploy into Second Life/OpenSim objects. A single desktop executable is not the current release model.

A normal public release should include:

1. A real application version set in the canonical version source.
2. A version tag for that release.
3. A GitHub Release created from that tag.
4. Release notes describing user-facing changes and upgrade requirements.
5. The generated ZIP release artifact attached to the GitHub Release.
6. A matching entry in [CHANGELOG.md](CHANGELOG.md).

Release artifacts should be attached to GitHub Releases. They should not be committed directly into the repository unless there is a specific documented reason.

## Installation

See [docs/installation.md](docs/installation.md).

The current implementation is a backend service plus database and in-world scripts. Public installation is designed around extracting the official ZIP artifact, configuring `api/.env` from `api/.env.example`, installing Python dependencies from `api/requirements.txt`, initializing PostgreSQL, and deploying the included LSL scripts.

## Support And Feedback

Use GitHub Issues for reproducible bugs and feature requests:

- Read [SUPPORT.md](SUPPORT.md) before opening an issue.
- Use the bug report template for defects.
- Use the feature request template for new behavior or workflow requests.

Do not include credentials, API keys, tokens, private account data, private logs, or personal information in public issues.

## Policies

- [Privacy](PRIVACY.md)
- [Terms](TERMS.md)
- [Security](SECURITY.md)
- [Support](SUPPORT.md)
- [Changelog](CHANGELOG.md)

## License And Rights

TODO: OWNER REVIEW REQUIRED - Confirm the intended software license before the first public release.

This repository is public, but public visibility alone does not grant permission to redistribute, modify, repackage, sell, or create derivative works from SteveRequests. Do not assume open-source rights unless a verified license file or release terms are added by Purge City Projects.
