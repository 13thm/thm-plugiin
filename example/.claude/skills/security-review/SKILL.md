---
name: security-review
description: Comprehensive security review and vulnerability assessment
version: "1.0.0"
author: Security Team
---

# Security Review Skill

Perform thorough security analysis of code changes.

## When to Use

Invoke this skill when:
- Reviewing code that handles sensitive data
- Analyzing authentication/authorization flows
- Checking for common vulnerabilities (XSS, SQL injection, CSRF)
- Validating input sanitization
- Reviewing API security

## Security Checks

### Authentication & Authorization
- Proper authentication implementation
- Role-based access control
- Session management
- Token handling and expiration

### Input Validation
- User input sanitization
- SQL injection prevention
- XSS prevention
- Command injection防护
- File upload validation

### Data Protection
- Encryption at rest and in transit
- Sensitive data handling
- Logging security (no secrets in logs)
- Secure storage of credentials

### API Security
- Rate limiting
- API authentication
- CORS configuration
- Proper error responses (no information leakage)

## Output Format

Provide:
1. Risk level (Critical/High/Medium/Low)
2. Vulnerability description
3. Affected code locations
4. Recommended fix
5. Code examples if applicable

## Notes

- Prioritize critical vulnerabilities
- Consider attack surface and exposure
- Validate assumptions about trust boundaries
