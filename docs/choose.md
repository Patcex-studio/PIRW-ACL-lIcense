# License Tier Selector & Decision Guide

**Select your tier at deposit.** Record your choices in the Work's metadata (see [Metadata Template](metadata.md)).

This guide helps you understand the 2-dimensional configuration space: **Commercial Use** × **Derivative Works**.

---

## The Two Dimensions

### Dimension 1: Commercial Use

#### NC-Default (Non-Commercial Only)
**Permitted:** Research, education, non-profit, academic publishing  
**Prohibited:** Revenue-generating products, SaaS, APIs, paid services (without waiver)  
**Default:** Yes (unless you explicitly select Commercial-Allowed)  
**§ Reference:** LICENSE §6.1–6.3

**Use Cases:**
- Academic preprints and working papers
- Research datasets for citations in non-profit institutions
- Publicly shared hypotheses and research notes
- Educational materials for universities and online courses
- Open-source tools developed by individual researchers

**Exception:** The [Open Business Exception](../LICENSE#L350) allows entities with <$500k annual revenue to use NC-Default Works for research/education at no cost, without requesting a waiver.

#### Commercial-Allowed
**Permitted:** Any commercial use, including SaaS, APIs, licensing, bundling  
**Restriction:** Attribution and derivative-work terms still apply  
**Default:** No (you must explicitly select this)  
**§ Reference:** LICENSE §6.2

**Use Cases:**
- Industry-academic partnerships
- Commercial APIs that expose open-source research
- For-profit consulting using research data
- Commercial training materials
- Data products sold to enterprises
- Startup MVPs using academic datasets

---

### Dimension 2: Derivative Works

#### BY (Attribution-Only)
**Requirement:** Any derivative or adaptation must include attribution to the original Contributor(s)  
**Restriction:** No further conditions on the derivative  
**Freedom:** Maximum reuse; derivative works can be placed under any license  
**§ Reference:** LICENSE §7.1–7.2

**Use Cases:**
- Code that will be incorporated into proprietary software
- Data that will be bundled with other licensed datasets
- Research that builds on your findings (normal scientific citation)
- Educational materials that remix your content
- Technical documentation that cites your methodology

**Attribution Format:** See [Machine-Readable Attribution](metadata.md#attribution-formats).

#### SA (Share-Alike)
**Requirement:** Any derivative or adaptation must be distributed under PIRW-ACL with the **same tier** (NC-Default or Commercial-Allowed)  
**Effect:** Creates a "copyleft" for open science  
**Scope:** Only substantive modifications trigger SA; simple citations, aggregations, and bibliographies do not  
**§ Reference:** LICENSE §7.1, §7.3–7.4

**What IS an Adaptation (triggers SA):**
- Substantial changes to data structure, methodology, or analysis
- Remixing multiple datasets into a new composite
- Translating code into a different programming language with significant rewrites
- Extending an algorithm with new features or optimizations

**What IS NOT an Adaptation (does NOT trigger SA):**
- Simply citing the Work in a bibliography
- Including a small excerpt or figure with attribution
- Using data as input to an unrelated algorithm
- Aggregating multiple works without modification (e.g., a dataset catalog)
- Linking to or referencing the original Work

**Use Cases:**
- Open-source research frameworks that should remain open
- Community-driven datasets that should grow collaboratively
- Reproducible research notebooks shared among labs
- Scientific standards and protocols that benefit from collective improvement
- Collaborative benchmarks that all participants maintain under the same license

---

## The Four Tier Combinations

| Tier | Commercial Use | Derivatives | Best For | Example |
|------|---|---|---|---|
| **NC-Default + BY** | ❌ Non-commercial only (waivers available) | Attribution-only | Preprints, hypotheses, open datasets for academic reuse | A researcher publishing draft findings that others will cite and adapt for academic work |
| **NC-Default + SA** | ❌ Non-commercial only (waivers available) | Share-Alike required | Collaborative notebooks, open-source research tools, shared protocols | A lab publishes a data-processing pipeline; downstream users improve it and contribute improvements back under the same terms |
| **Commercial-Allowed + BY** | ✅ Any use permitted | Attribution-only | Industry partnerships, open APIs, datasets suitable for commercial products | A company builds a SaaS platform on research data, with proper attribution |
| **Commercial-Allowed + SA** | ✅ Any use permitted | Share-Alike required | Open-source research tools, community benchmarks, shared frameworks | An open-source research library used by multiple companies; all improvements must be contributed back |

---

## Decision Tree

```
Start: Do you want to allow commercial use of your Work?
│
├─ NO, I only want non-profit research/education use
│  ├─ Use: NC-Default
│  ├─ Next: Do you want downstream adaptations to stay under the same license?
│  │
│  ├─ NO, let others use it however they want (with attribution)
│  │  └─ CHOOSE: NC-Default + BY
│  │
│  └─ YES, I want improvements shared back with the community
│     └─ CHOOSE: NC-Default + SA
│
└─ YES, commercial use is okay with me
   ├─ Use: Commercial-Allowed
   ├─ Next: Do you want downstream adaptations to stay under the same license?
   │
   ├─ NO, let commercial partners integrate freely
   │  └─ CHOOSE: Commercial-Allowed + BY
   │
   └─ YES, any commercial improvements should be open-source too
      └─ CHOOSE: Commercial-Allowed + SA
```

---

## Recording Your Tier Selection

### In Project Metadata (Required)

Add to your project root or dataset documentation:

```yaml
# PIRW License Configuration
license: PIRW-ACL v1.0
license-url: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
license-tier: "NC-Default + BY"  # or "NC-Default + SA" or "Commercial-Allowed + BY" or "Commercial-Allowed + SA"
license-effective-date: "2026-05-24"
```

### In Source Code Headers (For Code)

```python
# SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
# License-Tier: NC-Default + BY
# Repository: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
# Author: <Your Name>
# Date: 2026-05-24
```

### In JSON-LD (For Websites/Datasets)

```json
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "license": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
  "name": "Your Work Title",
  "version": "1.0",
  "licenseIdentifier": "LicenseRef-PIRW-ACL-1.0",
  "licenseTier": "NC-Default + BY",
  "creator": { "@type": "Person", "name": "Your Name" }
}
```

---

## Changing Your Tier Later

**Can I upgrade from NC-Default to Commercial-Allowed?**

Yes. Upon written request to the Repository Operator, you may issue a new version of your Work with the updated tier. Existing distributions under the old tier remain valid; only new distributions use the new tier. Version your Work (v1.0 = NC-Default + BY, v1.1 = Commercial-Allowed + BY).

**Can I downgrade from Commercial-Allowed to NC-Default?**

No. Once you permit commercial use, you cannot retroactively restrict it for that version. However, you may release a new version under NC-Default; existing users of the Commercial-Allowed version retain their rights.

**Can I switch from BY to SA?**

Yes, same process as above. New versions can have different derivative terms; old versions remain under their original terms.

---

## Commercial Waiver Process (For NC-Default Works)

If your Work is NC-Default and a commercial entity wishes to use it, they may request a waiver.

### How to Request a Waiver

1. **Go to:** [Commercial Waiver Request](../../../issues/new?template=commercial-waiver.md)
2. **Provide:**
   - URL of the Work
   - Intended commercial use (product description, revenue model)
   - Annual revenue tier (<$500k or >$500k)
3. **Wait for Contributor response** (within 30 days is courteous)

### What Happens Next

- **Automatic Exception:** If annual revenue < $500k and use is for research/education, the [Open Business Exception](../LICENSE#L350) applies automatically—no waiver needed.
- **Granted:** You receive a written waiver letter granting commercial rights under specified conditions.
- **Denied:** The Contributor declines. You must cease commercial use or pursue a different Work.
- **Negotiated Terms:** The Contributor may offer a waiver with conditions (e.g., revenue-sharing, attribution placement).

### Waiver Duration

Waivers are perpetual for the granted version unless otherwise specified in the waiver letter. If you upgrade the Work version, the old waiver does not automatically transfer; a new waiver request may be required.

---

## Examples by Domain

### Academic Research
**Tier:** NC-Default + SA

**Rationale:** Academic work benefits from open sharing and reciprocal improvement. The SA requirement ensures that derivative research tools stay in the academic commons.

**Example:** "I'm publishing my dataset of seismic measurements. I want other researchers to improve and distribute the analysis tools, but I want to ensure those improvements remain open for the whole research community."

---

### Startup Using Research Data
**Tier:** Commercial-Allowed + BY

**Rationale:** The startup needs freedom to commercialize; attribution ensures the researchers get credit and visibility.

**Example:** "I'm building a SaaS platform for clinical data analysis using publicly available research datasets. I want to ensure proper academic attribution but need commercial freedom to build a sustainable product."

---

### Educational Materials
**Tier:** Commercial-Allowed + BY

**Rationale:** Teachers and for-profit online platforms both benefit; attribution credits the original author.

**Example:** "I'm publishing a tutorial on machine learning. Universities, bootcamps, and online platforms should all be able to use, adapt, and teach from it with attribution."

---

### Open-Source Software Library
**Tier:** Commercial-Allowed + SA

**Rationale:** Contributors should be able to use the library in commercial products, but all improvements should be contributed back to benefit the community.

**Example:** "I'm publishing a bioinformatics toolkit. Companies can build commercial tools with it, but any enhancements they make must be open-sourced so the broader community benefits."

---

## Additional Guidance

### Dealing with Ambiguity

If your use case doesn't fit neatly into one tier:

1. **Err on the side of the Contributor:** Choose the more restrictive tier initially.
2. **Request Clarification:** Use [Discussions](../../../discussions) to ask for guidance.
3. **Request a Waiver:** If you think you qualify, use the [Commercial Waiver process](../../../issues/new?template=commercial-waiver.md).

### Combining Works Under Different Tiers

If you create a derivative combining NC-Default + SA and Commercial-Allowed + BY works:

1. **Respect both tiers:** The derivative must follow the most restrictive terms.
   - NC-Default applies to the derivative (commercial use prohibited unless all source works permit it)
   - SA applies to the derivative (all sources using SA mean the derivative must also use SA)

2. **Document lineage:** Include all upstream Contributors in the attribution chain.

---

## Next Steps

1. **Choose your tier** from the four options above.
2. **Record it** in your project metadata (use the templates above).
3. **Copy attribution snippets** from [Machine-Readable Metadata](metadata.md).
4. **For help:** See [FAQ](faq.md) or open a [Discussion](../../../discussions).
