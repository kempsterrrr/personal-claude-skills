---
name: c2pa-spec-compliance
description: Verifies software compliance with the C2PA specification. Invoke during planning or code review to check implementations against the spec. Provide code/design context and optionally a target version.
license: MIT
metadata:
  author: William Kempster
  version: "2.0"
  spec-source: https://github.com/c2pa-org/specifications
---

# C2PA Compliance Check

Verify code or designs against the C2PA (Coalition for Content Provenance and Authenticity) specification.

## Input

When invoking this skill, provide:
- **Code or design to review**: The specific files, functions, or design decisions to check
- **Review type**: `planning` | `code-review` | `testing`
- **Version** (optional): Target spec version (defaults to latest)

## Output

Return a compliance report with:
- **Version checked**: The spec version used
- **Findings**: List of compliance issues or confirmations, each citing the relevant spec section
- **Verdict**: `compliant` | `non-compliant` | `needs-clarification`

## Process

1. **Determine version**:
   - Use provided version if specified
   - Or check project config (`package.json`, `Cargo.toml`, etc.) for C2PA library versions
   - Or discover latest by fetching `https://github.com/c2pa-org/specifications/tree/main/build/site/specifications` and finding the highest numbered folder (e.g., if folders are 1.0, 1.1, 2.0, 2.1, 2.2, 2.3, 2.4 → use 2.4)

2. **Fetch relevant spec sections**: Use WebFetch to retrieve the specification:
   ```
   https://github.com/c2pa-org/specifications/blob/main/build/site/specifications/{version}/specs/C2PA_Specification.html
   ```

   Other documents if needed:
   - `specs/ContentCredentials.html` - Content credentials
   - `guidance/Guidance.html` - Implementation guidance
   - `ai-ml/ai_ml.html` - AI/ML requirements

3. **Compare implementation to spec**: For each C2PA-relevant component in the code/design:
   - Find the corresponding spec requirement
   - Verify the implementation matches
   - Note any deviations with spec section reference

4. **Report findings**: Return structured findings with spec citations

## C2PA Components to Check

When reviewing, look for these areas:
- **Manifest/JUMBF structure**: Box format, labels, nesting
- **Claims**: Required fields, claim linkage
- **Assertions**: Standard labels, custom handling
- **Signatures**: Algorithm support, certificate handling
- **Hash binding**: Asset hashing, hard/soft binding
- **Trust validation**: Certificate chains, revocation

## Example Invocation

```
Review type: code-review
Version: 2.3
Code: [manifest.rs - the create_manifest function]

Check that the manifest structure and required claim fields
comply with C2PA 2.3 specification.
```

## Example Output

```
## C2PA Compliance Report

**Spec Version**: 2.3
**Component**: create_manifest function

### Findings

1. **Compliant**: JUMBF box structure uses correct `c2pa` label
   (per spec section 6.2)

2. **Non-compliant**: Missing `claim_generator` field in claim
   (required per spec section 8.1.2)

3. **Compliant**: Signature algorithm ES256 is supported
   (per spec section 12.3)

### Verdict: non-compliant

**Action required**: Add `claim_generator` field to claim structure.
```

## References

See `references/` for:
- `VERSIONS.md` - Version matrix and URL construction
- `WORKFLOW.md` - Detailed review workflows by phase
- `CHECKLIST.md` - Compliance checklist template
