# Security Policy

## Supported Versions

We release patches for security vulnerabilities in the following versions:

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| < Latest| :x:                |

## Reporting a Vulnerability

We take the security of HLS Player seriously. If you believe you have found a security vulnerability, please report it to us as described below.

### How to Report

**Please do NOT report security vulnerabilities through public GitHub issues.**

Instead, please report them via:

- **Email**: Create a new issue with the title "SECURITY: [Brief Description]" and we'll provide a secure communication channel
- **GitHub Security Advisories**: Use the [Security Advisory](https://github.com/mnmltsai/hls-player/security/advisories/new) feature (preferred)

### What to Include

Please include the following information in your report:

- Type of vulnerability (e.g., XSS, URL injection, etc.)
- Full paths of affected source files
- Location of the affected code (tag/branch/commit or direct URL)
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the vulnerability and how it could be exploited

### Response Timeline

- We will acknowledge your report within **48 hours**
- We will provide a detailed response within **7 days** indicating next steps
- We will keep you informed of the progress toward a fix
- We will notify you when the vulnerability is fixed

## Security Best Practices for Users

### Players (HTML)

1. **Only load streams from trusted sources**
   - The players accept URLs via query parameters
   - Malicious URLs could attempt to exploit your browser

2. **Keep your browser updated**
   - Modern browsers have built-in protections
   - Update regularly for latest security patches

3. **Use HTTPS streams when possible**
   - HTTP streams can be intercepted or modified
   - HTTPS provides encryption and integrity

### Browser Extension

1. **Review permissions before installing**
   - Extension needs `<all_urls>` to detect HLS streams
   - Only install from trusted sources

2. **Be cautious with detected streams**
   - Extension automatically detects `.m3u8` URLs
   - Verify the source before playing

3. **Keep extension updated**
   - Updates may include security fixes
   - Enable automatic updates in your browser

## Known Security Considerations

### URL Handling
- Players accept URLs via query parameters (`?url=`, `?src=`, `?v=`)
- URL validation is implemented to prevent injection attacks
- Blocked URL schemes: `javascript:`, `data:`, `file:`, `blob:`
- Only HTTP(S) URLs with `.m3u8` extension are allowed

### Content Security Policy
- Players should be served with appropriate CSP headers
- Inline scripts are used for simplicity but can be migrated to external files

### Extension Permissions
- Extension requires broad permissions to detect streams across all websites
- No data is collected or transmitted
- All processing is done locally in your browser

### Third-Party Dependencies
- HLS.js: Loaded from CDN (https://cdn.jsdelivr.net)
- Media Chrome: Loaded from CDN (https://cdn.jsdelivr.net)
- Consider using Subresource Integrity (SRI) for additional security

## Disclosure Policy

- We follow responsible disclosure principles
- Security issues are disclosed publicly only after:
  - A fix is available
  - Reasonable time has passed for users to update
  - Coordination with the reporter (if applicable)

## Security Updates

Security updates will be released as:
- Immediate patches for critical vulnerabilities
- Regular updates for minor security improvements
- Announced via GitHub releases and README

## Contact

For security concerns, please use the reporting methods above. For general questions, open a regular GitHub issue.

## Attribution

We appreciate the security research community and will acknowledge reporters (with their permission) in:
- Release notes
- CHANGELOG.md
- README.md (Hall of Fame section, if established)

Thank you for helping keep HLS Player and its users safe!
