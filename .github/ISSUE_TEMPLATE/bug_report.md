---
name: Bug report
description: Report a reproducible problem with SteveRequests
title: "[Bug]: "
labels: ["bug"]
body:
  - type: markdown
    attributes:
      value: |
        Thanks for reporting a problem. Before submitting, remove secrets, API keys, access tokens, personal information, private account data, and other sensitive details from logs, screenshots, and examples.
  - type: input
    id: version
    attributes:
      label: SteveRequests version
      description: Include the exact version from GitHub Releases, if available.
      placeholder: "Example: v1.2.3"
    validations:
      required: true
  - type: input
    id: environment
    attributes:
      label: Operating system / environment
      description: Include OS version, runtime environment, or hosting context as applicable.
      placeholder: "Example: Windows 11"
    validations:
      required: true
  - type: textarea
    id: expected
    attributes:
      label: Expected behavior
      description: What did you expect to happen?
    validations:
      required: true
  - type: textarea
    id: actual
    attributes:
      label: Actual behavior
      description: What happened instead?
    validations:
      required: true
  - type: textarea
    id: steps
    attributes:
      label: Reproduction steps
      description: Provide the smallest clear sequence of steps that reproduces the issue.
      placeholder: |
        1. ...
        2. ...
        3. ...
    validations:
      required: true
  - type: textarea
    id: logs
    attributes:
      label: Relevant logs or errors
      description: Paste relevant logs or errors after removing secrets, API keys, tokens, personal information, and private data.
      render: text
    validations:
      required: false
  - type: textarea
    id: screenshots
    attributes:
      label: Screenshots
      description: Add screenshots if they help explain the issue. Remove or redact sensitive information first.
    validations:
      required: false
---
