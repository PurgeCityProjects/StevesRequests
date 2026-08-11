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

At the time this repository structure was created, no application-level public release version is documented here. The development project contains script-family version maps for LSL components, but those are not a public application release version. Do not create a version tag or GitHub Release until real release artifacts and release notes are ready.

## Release Model

SteveRequests public distribution is intended to use GitHub Releases.

A normal public release should include:

1. A version tag.
2. A GitHub Release created from that tag.
3. Release notes describing the user-facing changes.
4. Downloadable release artifact(s), such as installers, deployment archives, or packages.
5. A matching entry in [CHANGELOG.md](CHANGELOG.md).

Release artifacts should be attached to GitHub Releases. They should not be committed directly into the repository unless there is a specific documented reason.

TODO: OWNER REVIEW REQUIRED - Confirm the exact public release artifact format before the first release.

## Installation

See [docs/installation.md](docs/installation.md).

The current implementation is a backend service plus database and in-world scripts. No verified public installer or packaged end-user release artifact exists yet.

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
