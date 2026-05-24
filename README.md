# PIRW Argued Custom License (PIRW-ACL v1.0)

**A machine-readable, modular license for open science, research data, and public ideas.**

PIRW-ACL v1.0 is designed for engineers, researchers, data scientists, and open-source maintainers who need:

- 🛡️ **Clear Commercial Boundaries** – Control whether your work can be monetized (NC-Default) or freely used commercially (Commercial-Allowed)
- 🔐 **Anti-Ghosting Attribution** – Robust, machine-readable attribution chains prevent credit theft and enforce cumulative authorship
- ⏱️ **Idea Priority Evidence** – Timestamped, immutable deposits serve as defensive publication for patent priority
- 🎓 **Open Science by Default** – Non-commercial research, education, and non-profit uses are always permitted
- 🤝 **Share-Alike Options** – Optional reciprocal licensing for collaborative, open-source style projects
- ⚖️ **Moral Rights Protection** – Authors retain integrity rights and cannot be distorted or misrepresented
- 🚫 **No Digital Handcuffs** – Prohibition on DRM/TPM ensures open access cannot be undermined by technological restrictions

---

## Effective Date
**24 May 2026** – This License is effective immediately upon access, download, or use of any Work.

---

## Core Principles

### 1. Public Warehouse Model
Works deposited under PIRW-ACL are committed to public, unrestricted access. The Repository Operator retains perpetual hosting and archival rights, ensuring continuity even if the original Contributor withdraws the Work (§10).

### 2. Modular Tier Selection
At deposit, Contributors select two dimensions:

| Dimension | Options |
|-----------|----------|
| **Commercial Use** | NC-Default (non-commercial only, waivers available) OR Commercial-Allowed (any use permitted) |
| **Derivatives** | BY (attribution-only) OR SA (share-alike, same terms downstream) |

See [Choose Your Tier](docs/choose.md) for detailed guidance.

### 3. Automatic Acceptance
No signature, click-wrap, or registration required. Using a Work constitutes automatic acceptance of this License (§2.2).

### 4. Redundant Safeguards
Attribution, commercial restrictions, and integrity protections are enforced through multiple, overlapping mechanisms (§16), preventing loopholes.

---

## Quick Start

### For Users / Downstream Developers

1. **Read the full license:** [LICENSE](LICENSE)
2. **Choose your tier:** [Tier Selector](docs/choose.md)
3. **Copy metadata into your project:** [Machine-Readable Snippets](docs/metadata.md)

### Recommended project metadata
```text
SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
License-Tier: NC-Default + BY
License-URL: https://github.com/Patcex-studio/PIRW-ACL-lIcense/blob/main/LICENSE
```

### For integration

**Add the badge to your README:**
```markdown
[![License: PIRW-ACL v1.0](https://img.shields.io/badge/License-PIRW--ACL--1.0-blue)](https://github.com/Patcex-studio/PIRW-ACL-lIcense/blob/main/LICENSE)
```

**Add JSON-LD metadata to your HTML:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "license": "https://github.com/Patcex-studio/PIRW-ACL-lIcense/blob/main/LICENSE",
  "name": "Your Work Title",
  "version": "1.0",
  "licenseIdentifier": "LicenseRef-PIRW-ACL-1.0",
  "licenseTier": "NC-Default + BY"
}
</script>
```

---

## Key Rights Granted (§3)

✅ **Everyone Can:**
- Reproduce, display, and share the Work globally
- Index, crawl, and text-mine the Work for any purpose (including commercial data mining)
- Create internal (non-distributed) adaptations for non-commercial purposes

✅ **Non-Commercial Users Can:**
- Prepare, modify, and distribute adaptations under the same license tier
- Use the Work in research, education, and non-profit contexts without restriction

✅ **Commercial Users (if Commercial-Allowed) Can:**
- Build products and services using the Work
- Monetize derivatives under the selected derivative option (BY or SA)
- Integrate into SaaS, APIs, and commercial platforms

❌ **Everyone Must NOT:**
- Falsify, remove, or hide attribution (§4.5, §11.4 – **incurable breach**)
- Distort or misrepresent the Work's content (§5.2)
- Apply DRM or technological restrictions (§9.1)
- Use the Work commercially if NC-Default is selected (without waiver)

---

## Attribution Requirements (§4)

All uses must include **clear, prominent, machine-readable attribution** that identifies:

1. **Original Contributor(s)** – Name and affiliation
2. **Work Title** – With version/date if applicable
3. **Repository Source** – Link to original deposit
4. **License & Tier** – "PIRW-ACL v1.0 (NC-Default + BY)" or equivalent
5. **Cumulative Chain** – For derivatives, all upstream contributors

**Formats:**
- Print: Visible in citations or footnotes
- Web: Visible in page header, footer, or data attributes
- Code: Header comment or code metadata
- Data: CSV/JSON metadata records
- API: Response headers or JSON-LD

See [Machine-Readable Metadata](docs/metadata.md) for copy-paste snippets.

---

## Open Business Exception (§6.3)

**Entities ≤ USD 500k annual revenue** are automatically treated as **Non-Commercial** if:
- The Work is **not sold or licensed** as a standalone product
- Use is **primarily for research, education, or charity**
- The Work is **not integrated into revenue-generating services** (SaaS, APIs, subscriptions)

**Example:** A 3-person startup using PIRW-licensed research data to build a free open-source tool is permitted. Integrating it into a paid SaaS platform would require a Commercial Waiver or Commercial-Allowed tier.

---

## Moral Rights & Integrity Protection (§5)

Contributors retain **inalienable moral rights**, including:
- Right to attribution
- Right to object to distortion or misrepresentation
- Right to demand correction of serious mischaracterizations

If a derivative work seriously misrepresents your findings, the Repository Operator will act expeditiously to take it down (§5.3).

---

## Idea Priority & Patent Rights (§8)

**Upon deposit, the Repository creates:**
- Cryptographic hash (SHA-256) of the Work package
- Trusted timestamp (RFC 3161 standard)

**This serves as:**
- Public proof of your priority for the idea
- Defensive publication protecting against later patent claims
- **Does NOT grant or waive any patent rights** – you retain full patent freedom

You may pursue patent protection later without contradiction (§8.2).

---

## Enforcement & Dispute Resolution (§11)

**Breaches include:**
- Missing or falsified attribution → **Incurable, automatic termination**
- Unauthorized commercial use → 30-day cure period
- Distortion of content → 30-day cure period
- DRM/TPM applied to derivative → 30-day cure period

**Process:**
1. Notice of breach issued
2. 30-day cure period (except attribution falsification)
3. If uncured: mandatory binding arbitration via PIRW Steward (§11.2)
4. Escalation to courts in Zurich, Switzerland (§17.1) for injunctive relief only

**Reinstatement:** Most breaches can be reinstated upon written cure; attribution falsification requires public acknowledgment (§11.5).

---

## License Versioning (§13)

- **Current Version:** 1.0 (Effective 24 May 2026)
- **Future Versions:** Backward compatible, explicit version numbering (e.g., 1.1, 2.0)
- **Opt-In Clause:** Contributors may select "Opt-in to Latest Version" at deposit, automatically adopting future updates
- **Default:** Works remain under their original version unless opted in

---

## Compliance & Standards

✅ **SPDX-Compliant:** SPDX-License-Identifier: `LicenseRef-PIRW-ACL-1.0`

✅ **REUSE.Software Compliant:** Use the included `reuse.toml` for automated compliance checking

✅ **Schema.org Compatible:** JSON-LD metadata for machine-readable licensing

✅ **Open Definition Aligned:** Meets Open Knowledge Foundation requirements for open licenses

---

## Resources

📖 [Full License Text](LICENSE) – Read the complete legal instrument

⚙️ [Tier Selector & Decision Guide](docs/choose.md) – Understand each configuration option

📋 [Metadata Templates](docs/metadata.md) – Copy-paste snippets for your project

❓ [Frequently Asked Questions](docs/faq.md) – Common use cases and clarifications

💻 [Integration Examples](docs/examples/) – Code, data, and paper snippets

---

## Support & Governance

**Report Issues or Request Clarification:**
- [Commercial Waiver Request](issues/new?template=commercial-waiver.md)
- [Compliance / Attribution Report](issues/new?template=compliance-issue.md)
- [Discussions & Questions](discussions)

**PIRW Steward & Dispute Resolution:**
For low-cost arbitration and license interpretation, contact the PIRW Steward (details in LICENSE §11.2).

---

## Governing Law

**Jurisdiction:** Switzerland (Canton Zurich)

**Applicable Law:** Swiss civil law, without conflict-of-law principles

See [LICENSE §17.1](LICENSE#L400) for full details.

---

## Badge

[![License: PIRW-ACL v1.0](https://img.shields.io/badge/License-PIRW--ACL--1.0-blue)](https://github.com/Patcex-studio/PIRW-ACL-lIcense/blob/main/LICENSE)
