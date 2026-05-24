# Code/Software Licensing Example

This example shows how to license code repositories under PIRW-ACL (§14).

## Python File Header

```python
# SPDX-License-Identifier: LicenseRef-PIRW-ACL-1.0
# SPDX-FileCopyrightText: 2026 Dr. Jane Smith, Climate Research Institute
# License: https://github.com/<YOUR-ORG>/pirw-license/blob/main/LICENSE
# License-Tier: Commercial-Allowed + BY
```

## package.json (Node.js)

```json
{
  "name": "climate-toolkit",
  "version": "1.0.0",
  "license": "LicenseRef-PIRW-ACL-1.0",
  "author": "Dr. Jane Smith <jane@example.edu> (Climate Research Institute)",
  // pirwMetadata — документационное поле. npm не валидирует, но полезно для compliance-сканеров.
  "pirwMetadata": {
    "commercialTier": "Commercial-Allowed",
    "derivativeOption": "BY"
  }
}
```

## README.md Header

```markdown
# Climate Analysis Toolkit

**License:** PIRW-ACL v1.0 (Commercial-Allowed + BY)  
**SPDX-License-Identifier:** `LicenseRef-PIRW-ACL-1.0`  
**Author:** Dr. Jane Smith  
**Date:** 2026-05-24  

## Citation

```bibtex
@software{smith_climate_toolkit_2026,
  title = {Climate Analysis Toolkit},
  author = {Smith, Jane},
  year = {2026},
  url = {https://github.com/example/climate-toolkit},
  license = {PIRW-ACL v1.0 (Commercial-Allowed + BY)}
}
```
```

## reuse.toml (REUSE.Software Compliance)

```toml
version = 1

[[annotations]]
path = "**/*.py"
path = "**/*.js"
SPDX-FileCopyrightText = "2026 Dr. Jane Smith"
SPDX-License-Identifier = "LicenseRef-PIRW-ACL-1.0"
```

See [Metadata Templates](../metadata.md) for additional file formats.
