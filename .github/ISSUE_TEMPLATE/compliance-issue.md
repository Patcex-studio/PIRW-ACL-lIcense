---
name: PIRW-ACL Compliance Issue
description: Report a suspected license breach, attribution error, or misuse
title: "[Compliance] <Short summary>"
labels: ["compliance", "triage-needed"]
assignees: []
body:
  - type: input
    id: violation-summary
    attributes:
      label: Summary
      description: Briefly describe the suspected compliance issue
      placeholder: "Example: Missing attribution in commercial product, unauthorized DRM, etc."
    validations:
      required: true
  - type: textarea
    id: details
    attributes:
      label: Details
      description: Provide facts, links, and impacted work references
      placeholder: |
        - Source of the original PIRW work: [link]
        - Suspected violation location: [link]
        - License tier of original work: [NC-Default / Commercial-Allowed]
        - Evidence: [screenshots, code snippets, etc.]
    validations:
      required: true
  - type: dropdown
    id: severity
    attributes:
      label: Severity
      description: How critical is this violation?
      options:
        - "🔴 High - Attribution falsification or commercial breach"
        - "🟡 Medium - Missing attribution (unintentional)"
        - "⚪ Low - Unclear compliance, needs review"
    validations:
      required: true
  - type: input
    id: your-contact
    attributes:
      label: Your Contact (optional)
      description: Email or GitHub handle if you want to be contacted
      placeholder: your@email.com
    validations:
      required: false
---