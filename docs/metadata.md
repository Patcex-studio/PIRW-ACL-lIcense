# Machine-Readable Metadata & Compliance Templates

**Complete, copy-paste snippets for embedding PIRW-ACL licensing information in your projects.**

PIRW-ACL requires standardized metadata to enable automated compliance checking, proper attribution chains, and interoperability across platforms. This guide provides templates for all major formats.

---

## Required Metadata Fields (§14.1)

Every Work must include the following mandatory fields in its metadata record:

| Field | Format | Example |
|-------|--------|----------|
| `identifier` | DOI, UUID, or URL | `https://github.com/example/work` or `10.xxxx/zenodo.xxxxx` |
| `contributor` | Name(s) and affiliation(s) | `Dr. Jane Smith (Example University)` |
| `license-version` | `PIRW-ACL-X.X` | `PIRW-ACL-1.0` |
| `commercial-tier` | `NC-Default` or `Commercial-Allowed` | `NC-Default` |
| `derivative-option` | `BY`, `SA`, or `BY-SA` | `BY` |
| `attribution-format` | MIME type identifier | `text/x-bibtex`, `application/ld+json` |
| `content-hash` | SHA-256 hex string | `a1b2c3d4e5f6...` |
| `timestamp` | ISO 8601 | `2026-05-24T12:34:56Z` |

---

## JSON-LD (Recommended for Web & Linked Data)

**Use for:** HTML5 documents, APIs, semantic web integration, dataset portals

### Basic Template

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "identifier": "https://github.com/example/my-dataset",
  "name": "Title of Your Work",
  "version": "1.0",
  "creator": {
    "@type": "Person",
    "name": "Dr. Jane Smith",
    "affiliation": "Example University"
  },
  "datePublished": "2026-05-24",
  "license": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
  "licenseIdentifier": "LicenseRef-PIRW-ACL-1.0",
  "licenseVersion": "1.0",
  "licenseTier": "NC-Default",
  "derivativeOption": "BY",
  "description": "A brief description of your work and its research contributions.",
  "keywords": ["research", "open-science", "data"],
  "contentHash": {
    "@type": "CryptographicHash",
    "hashAlgorithm": "sha256",
    "hashValue": "a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0u1v2w3x4y5z6a7b8c9d0e1f2"
  },
  "sdDatePublished": "2026-05-24T12:34:56Z",
  "isFamilyFriendly": true,
  "url": "https://github.com/example/my-dataset",
  "codeRepository": "https://github.com/example/my-dataset",
  "attributionFormat": "application/ld+json"
}
</script>
```

### Extended Template (with Contributor Chain)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "identifier": "https://doi.org/10.xxxx/zenodo.xxxxx",
  "name": "Research Dataset: Climate Models",
  "version": "2.1",
  "creator": [
    {
      "@type": "Person",
      "name": "Dr. Jane Smith",
      "affiliation": "Climate Research Institute"
    },
    {
      "@type": "Person",
      "name": "Prof. John Doe",
      "affiliation": "University of Example"
    }
  ],
  "contributor": [
    {
      "@type": "Person",
      "name": "Dr. Alice Johnson",
      "role": "Data curation"
    }
  ],
  "datePublished": "2026-05-24",
  "dateModified": "2026-06-01",
  "license": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
  "licenseIdentifier": "LicenseRef-PIRW-ACL-1.0",
  "licenseVersion": "1.0",
  "licenseTier": "NC-Default",
  "derivativeOption": "SA",
  "description": "A comprehensive dataset of global climate models from 1900 to 2025, with monthly temperature and precipitation records.",
  "keywords": ["climate", "temperature", "precipitation", "open-data"],
  "inLanguage": "en",
  "contentHash": {
    "@type": "CryptographicHash",
    "hashAlgorithm": "sha256",
    "hashValue": "a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0u1v2w3x4y5z6a7b8c9d0e1f2"
  },
  "sdDatePublished": "2026-05-24T14:22:18Z",
  "url": "https://example-repository.org/datasets/climate-models-v2.1",
  "distribution": {
    "@type": "DataDownload",
    "url": "https://example-repository.org/datasets/climate-models-v2.1/data.csv",
    "fileFormat": "CSV",
    "contentSize": "2.4 GB"
  },
  "attributionFormat": "application/ld+json",
  "isBasedOn": {
    "@type": "CreativeWork",
    "name": "Original Climate Data Archive",
    "identifier": "https://example.org/climate-data-v1",
    "license": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE"
  }
}
</script>
```

---

## SPDX Identifier

**Use for:** Source code files, package manifests, compliance automation

### File Header (Python, JavaScript, etc.)

```python
# SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
# SPDX-FileCopyrightText: 2026 Dr. Jane Smith, Example University
# License: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
# License-Tier: NC-Default + BY
# Original-Work: https://github.com/example/my-dataset
```

### Package Manifest (package.json)

```json
{
  "name": "research-toolkit",
  "version": "1.0.0",
  "license": "LicenseRef-PIRW-ACL-1.0",
  "licenseText": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
  "licenseTier": "Commercial-Allowed + BY",
  "author": "Dr. Jane Smith <jane@example.edu> (Example University)",
  "repository": "https://github.com/example/research-toolkit",
  "pirwMetadata": {
    "licenseVersion": "1.0",
    "commercialTier": "Commercial-Allowed",
    "derivativeOption": "BY",
    "originalWork": "https://github.com/<YOUR-ORG>/pirw-license"
  }
}
```

### Debian/Linux (REUSE.Software Format)

```
SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
SPDX-FileCopyrightText: 2026 Dr. Jane Smith, Example University
License-Tier: NC-Default + BY
License-URL: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
```

---

## BibTeX (For Academic Citations)

**Use for:** Research papers, preprints, academic references

### Dataset

```bibtex
@dataset{smith_climate_dataset_2026,
  title     = {Research Dataset: Climate Models},
  author    = {Smith, Jane and Doe, John},
  year      = {2026},
  month     = May,
  day       = 24,
  publisher = {Example University},
  url       = {https://example-repository.org/datasets/climate-models-v2.1},
  doi       = {10.xxxx/zenodo.xxxxx},
  license   = {PIRW-ACL v1.0 (NC-Default + SA)},
  note      = {SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0},
  keywords  = {climate, temperature, open-data},
  version   = {2.1},
  howpublished = {https://github.com/<YOUR-ORG>/pirw-license}
}
```

### Software

```bibtex
@software{example_research_toolkit_2026,
  title     = {Research Toolkit: Data Analysis Framework},
  author    = {Smith, Jane},
  year      = {2026},
  url       = {https://github.com/example/research-toolkit},
  license   = {PIRW-ACL v1.0 (Commercial-Allowed + BY)},
  note      = {SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0},
  version   = {1.0.0},
  doi       = {10.xxxx/zenodo.xxxxx}
}
```

### Preprint/Working Paper

```bibtex
@preprint{smith_novel_approach_2026,
  title     = {A Novel Approach to Data Analysis},
  author    = {Smith, Jane},
  year      = {2026},
  month     = May,
  day       = 24,
  url       = {https://example-preprint-server.org/papers/2026.05.001},
  license   = {PIRW-ACL v1.0 (NC-Default + BY)},
  note      = {SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0},
  archiveprefix = {arXiv},
  eprint    = {2605.xxxxx}
}
```

---

## RDF/Turtle (For Semantic Web)

**Use for:** Linked data, ontology integration, knowledge graphs

```turtle
@prefix schema: <https://schema.org/> .
@prefix pirw: <https://github.com/<YOUR-ORG>/pirw-license/> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix spdx: <http://spdx.org/rdfterms#> .

<https://github.com/example/my-dataset>
  a schema:CreativeWork ;
  schema:name "Research Dataset: Climate Models" ;
  schema:version "2.1" ;
  schema:creator <https://orcid.org/0000-0001-2345-6789> ;
  schema:datePublished "2026-05-24" ;
  dcterms:license pirw:LICENSE ;
  spdx:licenseIdentifier "LicenseRef-PIRW-ACL-1.0" ;
  schema:licenseTier "NC-Default" ;
  schema:derivativeOption "SA" ;
  dcterms:hasPart <https://github.com/example/my-dataset/v2.0> ;
  schema:contentHash [
    a spdx:CryptographicHash ;
    spdx:checksumValue "a1b2c3d4e5f6..." ;
    spdx:checksumAlgorithm "SHA256"
  ] .

<https://orcid.org/0000-0001-2345-6789>
  a schema:Person ;
  schema:name "Dr. Jane Smith" ;
  schema:affiliation <https://example.edu> .
```

---

## CSV (Tabular Metadata)

**Use for:** Dataset catalogs, bulk metadata exports, spreadsheet systems

```csv
identifier,name,version,creator,datePublished,license,licenseVersion,licenseTier,derivativeOption,contentHash,timestamp,url
https://github.com/example/dataset-1,Climate Dataset,2.1,Dr. Jane Smith,2026-05-24,PIRW-ACL,1.0,NC-Default,SA,a1b2c3d4e5f6...,2026-05-24T14:22:18Z,https://example.org/datasets/climate-v2.1
https://github.com/example/code-2,Research Toolkit,1.0.0,Dr. Jane Smith,2026-05-24,PIRW-ACL,1.0,Commercial-Allowed,BY,b2c3d4e5f6g7...,2026-05-24T15:30:45Z,https://github.com/example/research-toolkit
```

---

## API Response Headers (For REST/GraphQL APIs)

**Use for:** APIs serving licensed content, downloads, query results

### HTTP Headers

```http
Content-Type: application/json
X-License: PIRW-ACL-1.0
X-License-Tier: NC-Default + BY
X-License-URL: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
X-License-Attribution: Dr. Jane Smith, Example University
X-Content-Hash-SHA256: a1b2c3d4e5f6...
X-Deposited: 2026-05-24T12:34:56Z
Access-Control-Expose-Headers: X-License, X-License-Tier, X-License-URL, X-License-Attribution
```

### JSON Response Body

```json
{
  "data": [
    {
      "id": 1,
      "value": "example",
      "_license": {
        "identifier": "LicenseRef-PIRW-ACL-1.0",
        "version": "1.0",
        "tier": "NC-Default + BY",
        "url": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
        "attribution": "Dr. Jane Smith, Example University",
        "timestamp": "2026-05-24T12:34:56Z"
      }
    }
  ],
  "meta": {
    "license": "LicenseRef-PIRW-ACL-1.0",
    "license_tier": "NC-Default + BY",
    "license_url": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE"
  }
}
```

---

## Markdown (For README & Documentation)

**Use for:** README.md, contributing guides, project documentation

### Header

```markdown
# My Research Dataset

**License:** PIRW-ACL v1.0 (NC-Default + BY)  
**SPDX-License-Identifier:** `LicenseRef-PIRW-ACL-1.0`  
**Creator:** Dr. Jane Smith, Example University  
**Date:** 2026-05-24  
**Repository:** https://github.com/<YOUR-ORG>/pirw-license

---

For full license terms, see [LICENSE](../../LICENSE).
```

### Attribution Block

```markdown
## Attribution

This work is licensed under the **PIRW Argued Custom License v1.0** (NC-Default + BY).

**Original Work:**
- **Title:** My Research Dataset
- **Creator:** Dr. Jane Smith, Example University
- **Date:** 2026-05-24
- **Source:** https://github.com/<YOUR-ORG>/my-dataset
- **License:** [PIRW-ACL v1.0](https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE)

**Usage:** This work may be freely used and adapted for non-commercial purposes with proper attribution.
```

---

## Attribution Formats (§4.2)

Choose ONE format appropriate to your medium and include in all distributions:

| Medium | Format | Example |
|--------|--------|----------|
| **Print** | BibTeX footnote | See BibTeX section above |
| **HTML/Web** | JSON-LD metadata | See JSON-LD section above |
| **Source Code** | File header comment | See SPDX section above |
| **Data Catalog** | CSV/Tabular record | See CSV section above |
| **API Response** | HTTP header + JSON body | See API section above |
| **README** | Markdown block | See Markdown section above |
| **Academic Paper** | Citation in references | Smith, J. (2026). My Research Dataset. PIRW-ACL v1.0. Retrieved from https://github.com/example/dataset |

---

## Complete Project Example: README.md

```markdown
# Climate Research Dataset v2.1

**License:** PIRW-ACL v1.0 (NC-Default + Share-Alike)  
**SPDX-License-Identifier:** `LicenseRef-PIRW-ACL-1.0`  

## Overview

A comprehensive global climate dataset from 1900–2025.

## Citation

```bibtex
@dataset{smith_climate_2026,
  title = {Climate Research Dataset v2.1},
  author = {Smith, Jane and Doe, John},
  year = {2026},
  doi = {10.xxxx/zenodo.xxxxx}
}
```

## License Terms

This dataset is licensed under [PIRW-ACL v1.0](https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE):

- **Commercial Use:** Not permitted (except under [Open Business Exception](https://github.com/<YOUR-ORG>/pirw-license/blob/main/docs/choose.md#open-business-exception))
- **Derivatives:** Must use Share-Alike (same license terms)
- **Attribution:** Required in all uses

## Usage

1. Download the dataset
2. Include the citation above
3. If you create adaptations, release under PIRW-ACL v1.0 with Share-Alike

For questions, see [FAQ](https://github.com/<YOUR-ORG>/pirw-license/blob/main/docs/faq.md) or open an issue.
```

---

## Validation & Compliance Checking

**REUSE.Software Compliance:**

Store the `reuse.toml` file (included in the repository) and run:

```bash
pip install reuse
reuse lint
```

All Works should pass `reuse lint` to ensure proper SPDX compliance.

---

## Additional Resources

- **SPDX License List:** https://spdx.org/licenses/
- **SPDX Spec:** https://spdx.github.io/spdx-spec/
- **REUSE.Software:** https://reuse.software/
- **Schema.org:** https://schema.org/
- **Zenodo DOI Guide:** https://guides.github.com/features/mastering-markdown/

---

## Questions or Issues?

- See [FAQ](faq.md) for common questions
- Open a [Discussion](../../../discussions) for guidance
- File a [Compliance Report](../../../issues/new?template=compliance-report.md) if you encounter violations
