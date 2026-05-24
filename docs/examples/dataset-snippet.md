# Dataset Licensing Example

This example shows how to license and document a research dataset under PIRW-ACL (§14).

## Scenario: Climate Temperature Dataset

### README Header

```markdown
# Global Climate Temperature Records 2000–2025

**License:** PIRW-ACL v1.0 (NC-Default + SA)  
**SPDX-License-Identifier:** `LicenseRef-PIRW-ACL-1.0`  
**Creator:** Dr. Jane Smith, Climate Research Institute  
**Date:** 2026-05-24  
**DOI:** https://doi.org/10.5281/zenodo.xxxxx  
```

### JSON-LD (for data portal)

```json
{
  "@context": "https://schema.org",
  "@type": "Dataset",
  "name": "Global Climate Temperature Records 2000–2025",
  "version": "1.2",
  "creator": {
    "@type": "Person",
    "name": "Dr. Jane Smith",
    "affiliation": "Climate Research Institute"
  },
  "datePublished": "2026-05-24",
  "license": "https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE",
  "licenseIdentifier": "LicenseRef-PIRW-ACL-1.0",
  "licenseTier": "NC-Default",
  "derivativeOption": "SA",
  "keywords": ["climate", "temperature", "open-data"]
}
```

### BibTeX Citation

```bibtex
@dataset{smith_climate_2026,
  title = {Global Climate Temperature Records 2000–2025},
  author = {Smith, Jane and Doe, John},
  year = {2026},
  month = May,
  doi = {10.5281/zenodo.xxxxx},
  license = {PIRW-ACL v1.0 (NC-Default + SA)},
  note = {SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0}
}
```

### CSV Header

```csv
# SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
# License-Tier: NC-Default + SA
# Creator: Dr. Jane Smith, Climate Research Institute
# Date: 2026-05-24
date,temperature_anomaly_C,std_error_C,quality_flag
2000-01-01,-0.421,0.084,VALID
```

### Usage & Attribution

**Non-Commercial Use Only:** This dataset is for academic research, education, and non-profit use only. Commercial entities must request a Commercial Waiver.

**Attribution Required:** In all publications and reports, include the BibTeX citation above.

**Share-Alike Required:** Any derivative dataset or tool must use PIRW-ACL v1.0 with Share-Alike.

See [Choose Your Tier](../choose.md) for commercial waiver process.

See [Metadata Templates](../metadata.md) for complete field definitions and additional formats.
