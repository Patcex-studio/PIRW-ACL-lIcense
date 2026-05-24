# Frequently Asked Questions (FAQ)

**Organized by topic.** See [LICENSE](../LICENSE) for complete legal text and section references.

---

## COMMERCIAL USE & TIER SELECTION

**Q: What does "Non-Commercial" mean?**

A: Per LICENSE §1 (Definitions), Non-Commercial use is limited to:
- Research, education, and non-profit activities
- Academic publishing and teaching
- Personal projects
- Internal organizational use without revenue

Prohibited: Selling the Work, integrating it into revenue-generating products (SaaS, APIs, subscriptions), or using it as the basis for commercial services.

---

**Q: Can I use an NC-Default Work for a SaaS product?**

A: No. NC-Default prohibits commercial integration (§6.3). You must either:
1. Request a Commercial Waiver from the Contributor (see [Waiver Process](choose.md#commercial-waiver-process))
2. Choose a different, Commercial-Allowed Work
3. Reimplement the functionality from scratch

---

**Q: What is the "Open Business Exception"?**

A: Per LICENSE §6.3, entities with **≤$500,000 annual revenue** using the Work **primarily for research/education** are automatically treated as Non-Commercial—no waiver required.

**Requirements:**
- Your organization's gross annual revenue does NOT exceed $500k
- You're using the Work for research, education, or non-profit purposes
- You're NOT selling or licensing the Work as a product
- You're NOT integrating it into a subscription/SaaS platform

---

**Q: Our startup makes $600k in revenue. Can we use NC-Default Works?**

A: No, the Open Business Exception doesn't apply (§6.3). You must:
1. Request individual Commercial Waivers
2. Use Works licensed as "Commercial-Allowed"
3. Seek alternative solutions

---

**Q: Can I change my tier selection after deposit?**

A: Per [Tier Selector](choose.md#changing-your-tier-later), you can **upgrade** from NC-Default to Commercial-Allowed in a new version. However, existing distributions under the old tier remain valid. You cannot retroactively restrict commercial rights.

---

## ATTRIBUTION & GHOSTING PREVENTION

**Q: What attribution is required?**

A: Per LICENSE §4 (Attribution Chain):
- Identify the original Contributor(s) and their affiliation
- Include the Work title and version
- Link to the Repository source
- Display the selected tier ("NC-Default + BY" or equivalent)
- For derivatives, include all upstream Contributors

See [Metadata Templates](metadata.md) for copy-paste formats.

---

**Q: Where should I put attribution?**

A: Per §4.4, attribution must be **reasonable to the medium**:
- **Papers:** Bibliography, footnote, or acknowledgments
- **Websites:** Visible footer, header, or data attribute
- **Code:** File header comment or manifest metadata
- **APIs:** HTTP header or JSON response body
- **Data:** CSV/metadata record or dataset README

Attribut must NOT be hidden behind hyperlinks or paywalls.

---

**Q: If I cite a Work in my bibliography, do I need to include full attribution details?**

A: A proper academic citation (author, title, date, URL) satisfies §4 for published papers. For code and data reuse, add the license tier ("NC-Default + BY") to the citation.

---

**Q: What if I lose track of where I found the Work?**

A: Make a reasonable effort to locate the original source. If you cannot:
1. Document your search effort
2. Credit "[Unknown Contributor], licensed under PIRW-ACL v1.0"
3. Include the license URL
4. File a [Compliance Report](../../../issues/new?template=compliance-report.md) to help identify the original author

---

**Q: Can I use a Work without attribution if I significantly modify it?**

A: No. Attribution is unconditional. §4.5 makes falsification of attribution an **incurable breach** triggering automatic termination (§11.4).

---

## DERIVATIVE WORKS & SHARE-ALIKE

**Q: What is a "Derivative Work" or "Adaptation"?**

A: Per LICENSE §1, an Adaptation requires **substantive modification** of the Work's structure, data, or methodology while retaining recognizable elements.

**Examples that ARE Adaptations:**
- Significantly reorganizing data or methodology
- Remixing multiple datasets into a new composite
- Translating code with substantial rewrites
- Extending algorithms with new features

**Examples that ARE NOT Adaptations:**
- Including a table or figure with attribution
- Citing the Work in a bibliography
- Using data as input to an unrelated algorithm
- Aggregating multiple works in a catalog (simple compilation)

---

**Q: If I use Share-Alike (SA), what license terms must my derivative use?**

A: Per §7.3, your derivative must:
1. Use PIRW-ACL v1.0 (or compatible version)
2. Apply the **same commercial tier** (NC-Default or Commercial-Allowed)
3. Apply the **same derivative option** (BY or SA)

Example: If you adapt an NC-Default + SA Work, your derivative must also be NC-Default + SA.

---

**Q: Does combining an SA Work with a BY Work trigger Share-Alike for the whole product?**

A: Yes. Per [Tier Selector Guidance](choose.md#combining-works-under-different-tiers), the **most restrictive terms apply**:
- If any source is NC-Default, the derivative is NC-Default
- If any source is SA, the derivative is SA

---

**Q: Does citing a paper trigger Share-Alike?**

A: No. §7.4 explicitly excludes simple citations, aggregations, and bibliographies from the SA requirement. Citations are not Adaptations.

---

**Q: Can I use a Share-Alike Work inside a proprietary product?**

A: Only if you select Commercial-Allowed + SA. If it's NC-Default + SA:
1. The Work cannot be used commercially at all (NC-Default blocks revenue use)
2. Even if commercial were permitted, the Share-Alike means your entire product must use the same license

This is by design—to preserve openness in collaborative research.

---

## PATENT RIGHTS & IDEA PRIORITY

**Q: Does PIRW-ACL affect my patent rights?**

A: No. Per LICENSE §8.2, this License **does not grant or waive any patent rights**. You retain full freedom to:
- Pursue patent protection for the underlying idea
- License patents separately
- Exercise all patent rights

The License merely provides timestamped priority evidence, not patent ownership transfer.

---

**Q: What is the "Idea Priority Evidence" in the Repository?**

A: Per §8.1, upon deposit, the Repository creates:
1. Cryptographic hash (SHA-256) of your Work
2. Trusted timestamp (RFC 3161 standard)

This serves as public, immutable proof that you conceived the idea at that date. Useful for:
- Defensive publication (preventing others' patent claims)
- Establishing prior art
- Scientific priority disputes

---

**Q: If I deposit an idea in the Repository, can I still file a patent?**

A: Yes, but timing matters. In most jurisdictions, **public disclosure triggers a 1-year grace period** for patent filing (U.S. AIA §102, EU EPC §6). Deposit in PIRW counts as public disclosure, so:
- **File within 12 months** of deposit to preserve patent rights
- Consider filing **before** deposit if patent protection is critical
- Some jurisdictions (e.g., Japan) have no grace period, so file first

Consult a patent attorney for your jurisdiction.

---

## MORAL RIGHTS & INTEGRITY

**Q: What are "Moral Rights"?**

A: Per LICENSE §5.1, Moral Rights are your inalienable rights to:
1. Be credited as the author
2. Prevent distortion or misrepresentation of your Work

These cannot be waived and survive termination of the License (§15.1).

---

**Q: What counts as "distortion" or "misrepresentation"?**

A: Per §5.2, prohibited distortions include:
- Publishing your preliminary hypothesis as if it were proven fact
- Removing caveats or limitations you included
- Using your data to reach contradictory conclusions without reanalysis
- Falsifying your methodology or results
- Presenting your work as supporting claims you explicitly rejected

**Permitted:** Fair criticism, reinterpretation with proper acknowledgment, or use of your data in novel contexts (with attribution).

---

**Q: If someone misrepresents my Work, what can I do?**

A: Per §5.3, you may demand:
1. **Correction** – The misrepresentation is fixed
2. **Retraction** – The false claim is withdrawn
3. **Removal** – The derivative is taken down from all platforms

The Repository Operator must act **expeditiously** to enforce this. You may also seek damages via the [mandatory arbitration process](../LICENSE#L370) (§11.2).

---

## ENFORCEMENT & DISPUTES

**Q: What happens if someone violates the license?**

A: Per LICENSE §11.3, material breaches (missing attribution, unauthorized commercial use, distortion, DRM) result in **automatic termination** of all rights. The breacher must:
1. Cease use immediately
2. Destroy copies (except those in archives)
3. Pay damages if pursued

For cure procedures, see §11.5.

---

**Q: What is an "incurable breach"?**

A: Per §11.4, **attribution falsification** is incurable and results in immediate termination without a cure period. Examples:
- Removing your name from a derivative
- Falsely claiming authorship
- Hiding the original license

Other breaches (unauthorized commercial use, distortion) have a 30-day cure period.

---

**Q: How are disputes resolved?**

A: Per §11.2, disputes follow a **mandatory low-cost arbitration process**:
1. Issue reported to PIRW Steward
2. Steward facilitates binding arbitration
3. If unresolved, escalate to courts in Zurich, Switzerland (§17.1) for injunctive relief only

**Goal:** Keep disputes affordable and resolvable within the community.

---

**Q: Can I terminate someone's license if they breach?**

A: As the Contributor, yes (§11.1). Upon notice of material breach, give the licensee 30 days to cure (except for attribution falsification, which terminates immediately). If uncured, the license terminates automatically.

You may seek damages and injunctive relief through arbitration (§11.2).

---

**Q: What if I accidentally violate the license?**

A: Per §11.5, most violations (other than attribution falsification) are curable:
1. You receive notice
2. You have 30 days to remedy (e.g., add missing attribution)
3. If you cure, the license is reinstated

For reinstatement after more serious breaches, you may need to provide a **public acknowledgment** of the error.

---

## TECHNICAL RESTRICTIONS & DRM

**Q: Can I apply encryption or DRM to a Work under PIRW-ACL?**

A: No. Per LICENSE §9.1, applying **Digital Rights Management (DRM) or Technological Protection Measures (TPM)** violates the License, even if you offer a waiver.

**Examples of prohibited measures:**
- Paywalls or authentication that blocks open access
- Encryption that prevents viewing without a key
- Watermarking that prevents copying
- Streaming-only delivery (denying download)

---

**Q: What if I use DRM to protect my derivative?**

A: Per §9.2, if you apply DRM to a derivative, you must **provide an unrestricted, full-content copy** to the Repository or a designated open archive within a reasonable time after notice.

This ensures the original Work remains publicly available.

---

## WARRANTY & LIABILITY

**Q: Are there warranties on the Work?**

A: No. Per LICENSE §12.1, Works are provided **"as-is" without any warranty**. This acknowledges that scientific ideas and data may be:
- Preliminary or incomplete
- Later superseded by new research
- Subject to error or revision

---

**Q: Can I sue the Contributor if their Work causes me harm?**

A: Per §12.2, Contributor liability is **limited to the maximum extent permitted by law**. However, §12.3 creates an exception:

**Fraudulent conduct (intentional misrepresentation) is NOT excluded.** If the Contributor knowingly falsified data or findings, you may pursue damages.

---

## REPOSITORY OPERATOR RIGHTS

**Q: Can the Repository Operator delete my Work?**

A: No. Per LICENSE §10.1, the Repository Operator retains a **perpetual, irrevocable right** to host, archive, and redistribute any Work, even if you request withdrawal.

This preserves scientific integrity and prevents loss of historical contributions.

---

**Q: Is the Repository Operator liable if someone uses my Work to cause harm?**

A: No. Per §10.2, the Operator has immunity from liability for user-generated derivatives, provided they:
1. Maintain an effective abuse-reporting system
2. Act expeditiously to address valid complaints (e.g., [Compliance Reports](../../../issues/new?template=compliance-report.md))

---

## LICENSE VERSIONING & FUTURE UPDATES

**Q: Will this License change in the future?**

A: Yes. Per LICENSE §13.1, the PIRW Steward may issue updated versions (e.g., 1.1, 2.0), which are:
- **Backward compatible** – Existing Works remain valid under their original version
- **Explicitly versioned** – Each update has a clear version number
- **Opt-in** – Contributors may choose to adopt newer versions

---

**Q: Can I opt in to future versions automatically?**

A: Yes. Per §13.2, if you select "[opt-in] to the latest version" at deposit, your Work automatically adopts future Updates without re-depositing.

Default: Works remain under their original version unless opted in.

---

## METADATA & COMPLIANCE

**Q: Do I need to include all the metadata fields?**

A: Per LICENSE §14.1, **all eight mandatory fields are required**:
1. Identifier (DOI, UUID, or URL)
2. Contributor name(s) and affiliation(s)
3. License version ("PIRW-ACL-1.0")
4. Commercial tier ("NC-Default" or "Commercial-Allowed")
5. Derivative option ("BY" or "SA")
6. Attribution format (MIME type, e.g., "application/ld+json")
7. Content hash (SHA-256)
8. Timestamp (ISO 8601)

See [Metadata Templates](metadata.md) for copy-paste formats.

---

**Q: What if my project doesn't support all metadata formats?**

A: Include **at least one** machine-readable format:
- JSON-LD (preferred for web)
- SPDX header (preferred for code)
- CSV record (preferred for datasets)

Support for multiple formats is encouraged but not mandatory.

---

## MISCELLANEOUS

**Q: Which country's laws apply?**

A: Per LICENSE §17.1, **Switzerland (specifically Canton Zurich)** governs disputes unless you specify otherwise in your Work's metadata.

---

**Q: Can I use this license for software? Data? Academic papers?**

A: Yes. PIRW-ACL is **domain-agnostic** and applies to:
- Code and software
- Datasets and data files
- Academic papers and preprints
- Research protocols and methodologies
- Design documents and specifications
- Educational materials
- Any creative or intellectual work

---

**Q: How does PIRW-ACL compare to Creative Commons or MIT?**

A: Key differences:

| Feature | PIRW-ACL | CC-BY-NC | MIT |
|---------|----------|----------|-----|
| Commercial Tier | NC/Commercial-Allowed | Non-commercial only | Commercial (always) |
| Share-Alike Option | Yes (BY or SA) | Yes (SA variant) | No |
| Moral Rights | Robust (§5) | Limited | None |
| Idea Priority | Timestamped (§8) | None | None |
| DRM Prohibition | Yes (§9) | No explicit | No explicit |
| Patent Language | Explicit preservation (§8.2) | Limited | Patent protection denial |

Use PIRW-ACL if you need: commercial flexibility, strong attribution, idea priority, or moral rights protection.

---

**Q: Can I contribute improvements back to the PIRW-ACL License itself?**

A: Yes. Open an issue or discussion on the [PIRW-ACL Repository](../../../issues) with your suggestion. The PIRW Steward reviews proposals for future versions.

---

## Still Have Questions?

- Open a [Discussion](../../../discussions) for general guidance
- File a [Compliance Report](../../../issues/new?template=compliance-report.md) if you encounter violations
- Request a [Commercial Waiver](../../../issues/new?template=commercial-waiver.md) if needed
- Email the PIRW Steward for formal interpretation

See [LICENSE](../LICENSE) for complete legal text and full section references.
