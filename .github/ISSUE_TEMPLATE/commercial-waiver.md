---
name: Commercial Waiver Request
description: Request permission to use an NC-Default work for commercial purposes
title: "[Waiver] <Project/Work Name>"
labels: ["commercial-waiver"]
assignees: []
body:
  - type: input
    id: work-url
    attributes:
      label: Work URL
      description: Link to the PIRW work you want to use
      placeholder: https://github.com/...
    validations:
      required: true
  - type: textarea
    id: use-case
    attributes:
      label: Intended Commercial Use
      description: Describe your product, revenue model, and how you'll use the work
      placeholder: "Example: SaaS platform for academic data analysis, subscription-based, will integrate dataset X as core feature"
    validations:
      required: true
  - type: dropdown
    id: revenue-tier
    attributes:
      label: Annual Revenue
      description: Your entity's total annual gross revenue
      options:
        - "<$500k (Open Business Exception may apply)"
        - "$500k - $1M"
        - "$1M - $10M"
        - "$10M+"
    validations:
      required: true
  - type: textarea
    id: attribution-plan
    attributes:
      label: Attribution Plan
      description: How will you credit the original contributor?
      placeholder: "Example: Will include BibTeX citation in documentation and JSON-LD in website header"
    validations:
      required: true
---