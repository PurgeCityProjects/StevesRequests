---
name: Feature request
description: Suggest an improvement or new behavior for SteveRequests
title: "[Feature]: "
labels: ["enhancement"]
body:
  - type: markdown
    attributes:
      value: |
        Please describe the problem or use case first. Do not include credentials, private account data, or other sensitive information.
  - type: textarea
    id: problem
    attributes:
      label: Problem or use case
      description: What problem would this solve, or what workflow would it improve?
    validations:
      required: true
  - type: textarea
    id: proposed_behavior
    attributes:
      label: Proposed behavior
      description: What would you like SteveRequests to do?
    validations:
      required: true
  - type: textarea
    id: alternatives
    attributes:
      label: Alternatives considered
      description: What alternatives or workarounds have you considered?
    validations:
      required: false
  - type: textarea
    id: additional_context
    attributes:
      label: Additional context
      description: Add any other relevant context, screenshots, examples, or constraints.
    validations:
      required: false
---
