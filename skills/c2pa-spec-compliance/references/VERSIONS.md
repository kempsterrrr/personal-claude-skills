# C2PA Specification Versions Reference

## Version Matrix

| Version | Status | Base URL |
|---------|--------|----------|
| 2.3 | **Latest** | `specifications/2.3/` |
| 2.2 | Stable | `specifications/2.2/` |
| 2.1 | Stable | `specifications/2.1/` |
| 2.0 | Stable | `specifications/2.0/` |
| 1.4 | Legacy | `specifications/1.4/` |
| 1.3 | Legacy | `specifications/1.3/` |
| 1.2 | Legacy | `specifications/1.2/` |
| 1.1 | Legacy | `specifications/1.1/` |
| 1.0 | Legacy | `specifications/1.0/` |

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
1. Check project for explicit version requirement
   - package.json: "c2pa" or "@c2pa/*" dependency versions
   - Cargo.toml: c2pa crate version
   - requirements.txt: c2pa-python version
   - Project documentation or config

2. If found, map library version to spec version

3. If not found, default to latest (2.3)
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
