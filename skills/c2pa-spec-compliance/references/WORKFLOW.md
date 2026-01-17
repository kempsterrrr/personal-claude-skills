# C2PA Compliance Review Workflows

Detailed workflows for each review phase.

## Planning Review

When reviewing plans or designs for C2PA compliance:

### 1. Identify C2PA-Relevant Components

Look for planned work involving:
- Manifest creation and embedding
- Signature generation and verification
- Claim and assertion handling
- Asset hashing and binding
- Trust chain validation

### 2. Verify Version Alignment

- Confirm which spec version the project targets
- Flag any version mismatches in dependencies
- Check if planned features exist in target version

### 3. Check for Breaking Changes

If upgrading versions:
- Review changelog for breaking changes
- Ensure planned implementation accounts for version differences
- Identify migration requirements

## Code Review

When reviewing code changes:

### 1. Manifest Structure

- Verify JUMBF box structure matches spec
- Check claim structure and required fields
- Validate assertion types and formats
- Confirm proper box nesting and ordering

### 2. Cryptographic Operations

- Verify signature algorithms are spec-approved
- Check certificate chain handling
- Validate hash algorithm usage
- Confirm timestamp handling if required

### 3. Binding Verification

- Hard binding implementation (embedded manifests)
- Soft binding implementation (external references)
- Asset hash calculations cover correct regions

### 4. Error Handling

- Validation error codes match spec definitions
- Trust signal handling is correct
- Graceful degradation for unknown assertions

## Testing Review

When reviewing or creating tests:

### 1. Validation Tests

- Valid manifest acceptance
- Invalid manifest rejection
- Tampered content detection
- Signature verification

### 2. Interoperability Tests

- Test against reference implementations
- Cross-version compatibility where required
- Round-trip encoding/decoding

### 3. Edge Cases

- Missing optional fields
- Unknown assertion types
- Expired certificates
- Revoked certificates
- Malformed JUMBF structures

## Common Compliance Issues

1. **Version Mismatch**: Using features from newer spec in older-targeted implementation
2. **Missing Required Fields**: Omitting mandatory claim or assertion fields
3. **Invalid Hash Binding**: Incorrect asset region hashing
4. **Unsupported Algorithms**: Using non-spec-approved crypto algorithms
5. **Trust Chain Gaps**: Incomplete certificate validation
6. **Label Format Errors**: Incorrect assertion or box labels
