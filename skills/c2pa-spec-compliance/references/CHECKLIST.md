# C2PA Compliance Checklist

Use this template when performing compliance reviews.

## Review Template

```markdown
## C2PA Compliance Review

**Spec Version**: [version]
**Review Date**: [date]
**Component**: [component name]
**Review Type**: [planning | code-review | testing]

### Manifest Structure
- [ ] JUMBF structure follows ISO/IEC 19566-5
- [ ] Required boxes present
- [ ] Labels formatted correctly (`c2pa`, `c2pa.assertions`)
- [ ] Proper box nesting and ordering

### Claims
- [ ] `dc:title` field present
- [ ] `claim_generator` field present
- [ ] `signature` field present
- [ ] Claim linkage valid (for redaction/update)
- [ ] Assertion references valid

### Assertions
- [ ] Standard assertion labels used correctly
- [ ] Custom assertions properly namespaced
- [ ] Assertion versioning handled

### Signatures
- [ ] Algorithm supported by spec version
- [ ] Certificate chain complete
- [ ] Certificate requirements met
- [ ] Timestamp present (if required)

### Hash Binding
- [ ] Correct asset regions hashed
- [ ] Hash algorithm spec-approved
- [ ] Hard binding correct (if used)
- [ ] Soft binding correct (if used)

### Trust Validation
- [ ] Trust anchor handling implemented
- [ ] Certificate validation complete
- [ ] Revocation checking implemented

### Validation Behavior
- [ ] Accepts conforming content
- [ ] Rejects non-conforming content
- [ ] Error codes match spec
- [ ] Unknown assertions handled gracefully

### Findings

| Item | Status | Spec Reference | Notes |
|------|--------|----------------|-------|
| | | | |

### Verdict

[ ] Compliant
[ ] Non-compliant
[ ] Needs clarification

### Required Actions

1. [action item]
```

## Quick Checks by Component

### For Manifest Creation
- Required claim fields present
- JUMBF structure valid
- Assertions properly referenced

### For Signature Operations
- Algorithm in approved list
- Certificate chain complete
- Timestamp handling correct

### For Validation Code
- All required checks performed
- Error codes match spec
- Trust signals correct
