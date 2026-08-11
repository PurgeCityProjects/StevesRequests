# Changelog

All notable public changes to SteveRequests should be documented in this file.

This project should follow a clear, dated changelog format for public releases. Do not fabricate historical versions.

## [Unreleased]

### Added

- Established the public release repository structure for SteveRequests.
- Added verified public documentation for the current backend-centered Second Life/OpenSim accounting and device-management implementation.
- Documented verified runtime components, configuration names, data-handling categories, third-party integration points, and security-sensitive operator configuration.
- Documented the verified ZIP source-distribution release model, canonical application version source, safe configuration template, and release package audit controls.

### Changed

- Replaced the placeholder README with public release, support, and distribution guidance.
- Clarified that no real public release has been published yet and that `0.0.0+unreleased` is an unreleased development sentinel, not a release tag.
- Clarified that public installation uses the generated ZIP artifact, `api/.env.example`, `api/requirements.txt`, PostgreSQL setup, SQL seed files, and included LSL scripts.
- Updated security and privacy documentation to reflect release-package exclusions and LSL connection placeholder cleanup.

### Removed

- Removed the unverified open-source license file from the proposed public release structure pending owner review.

## Release Entry Template

Use this template when publishing the first real public release:

```markdown
## [x.y.z] - YYYY-MM-DD

### Added

- ...

### Changed

- ...

### Fixed

- ...

### Security

- ...
```
