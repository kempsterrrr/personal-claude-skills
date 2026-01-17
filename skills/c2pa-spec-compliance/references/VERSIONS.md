# C2PA Specification Versions Reference

## Discovering Latest Version

To find the latest version, fetch:
```
https://github.com/c2pa-org/specifications/tree/main/build/site/specifications
```

The highest numbered folder is the latest version (e.g., 2.4 > 2.3 > 2.2).

## Known Versions

| Series | Versions |
|--------|----------|
| 2.x | 2.0, 2.1, 2.2, 2.3, ... |
| 1.x (Legacy) | 1.0, 1.1, 1.2, 1.3, 1.4 |

## Full URL Construction

Repository: `https://github.com/c2pa-org/specifications`
Branch: `main`
Path prefix: `build/site/specifications/{version}/`

### Document URLs by Version

Replace `{version}` with target version (e.g., `2.3`):

```
Core Specification:
https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/specs/C2PA_Specification.html

Content Credentials:
https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/specs/ContentCredentials.html

Implementation Guidance:
https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/guidance/Guidance.html

AI/ML Guidance:
https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/ai-ml/ai_ml.html
```

## Directory Structure Per Version

Each version folder contains:

```
{version}/
├── index.html              # Version landing page
├── specs/
│   ├── C2PA_Specification.html
│   ├── ContentCredentials.html
│   ├── _attachments/
│   └── _images/
├── guidance/
│   ├── Guidance.html
│   ├── _attachments/
│   └── _images/
├── ai-ml/
│   ├── ai_ml.html
│   ├── _attachments/
│   └── _images/
├── softbinding/
│   └── [soft binding docs]
└── explainer/
    └── [explainer docs]
```

## Version Selection Logic

```
1. Use explicitly provided version if given

2. Check project for version requirement:
   - package.json: "c2pa" or "@c2pa/*" dependency versions
   - Cargo.toml: c2pa crate version
   - requirements.txt: c2pa-python version
   - Project documentation or config

3. If not found, discover latest from GitHub (highest numbered folder)
```

## Major Version Differences

### 1.x to 2.x
- Significant structural changes to manifest format
- New assertion types
- Updated cryptographic requirements
- Enhanced trust model

### Within 2.x
- Incremental additions and clarifications
- New optional features
- Bug fixes and errata

## Fetching Specification Content

To retrieve and analyze specification content:

```python
# Example: Fetch specific section
url = f"https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/specs/C2PA_Specification.html"
# Use WebFetch tool with specific query about the section needed
```

When checking compliance, always reference the exact specification version and section.
