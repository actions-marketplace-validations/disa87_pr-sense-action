# PR-Sense &nbsp;·&nbsp; Instant AI Pull-Request Summaries ![Marketplace](https://img.shields.io/badge/GitHub%20Marketplace-Install-orange?logo=github) ![Version](https://img.shields.io/github/v/tag/disa87/pr-sense-action) ![CI](https://img.shields.io/github/actions/workflow/status/disa87/pr-sense-action/pr-sense.yml)

> **TL;DR**  
> PR-Sense posts a lightning-fast, bilingual TL;DR (German + English) into every pull request **and** flags potential breaking changes – zero setup required.

<div align="center">
  <!-- optional demo GIF – replace with your own -->
  <img src="docs/demo.gif" alt="Demo GIF" width="700">
</div>

---

## ✨ Features
| | |
|---|---|
| **Bilingual summary** | ≤ 150 characters per language (DE + EN) |
| **Breaking-Change radar** | Markdown bullet list, one line German &#124; English |
| **OpenAI cost included** | No API key needed – PR-Sense pays the tokens |
| **Org-wide usage counter** | Free 100 · Team 1 000 · Pro 10 000 · Enterprise 100 000 PR/month |
| **Automatic monthly reset** | Counter rolls over at the 1<sup>st</sup> of each month |
| **Large diff support** | Up to 15 000 diff lines; smart context cut-off |
| **Secure by design** | Only diff snippet leaves GitHub; usage data stored in a vendor-controlled private Gist |

---

## 🚀 Quick Start

```yaml
# .github/workflows/pr-sense.yml
name: PR-Sense
on: pull_request_target

permissions:
  contents: read
  pull-requests: write
  issues: write

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: disa87/pr-sense-action@v1
