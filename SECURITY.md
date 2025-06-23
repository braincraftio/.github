<!--
SPDX-FileCopyrightText: 2025 BrainCraft.io
SPDX-License-Identifier: CC-BY-4.0
-->

# Security Policy

## Supported Versions

We release patches for security vulnerabilities. Which versions are eligible for receiving such patches depends on the project:

| Version | Supported          |
| ------- | ------------------ |
| latest  | :white_check_mark: |
| < latest| :x:                |

_Note: For projects with formal release cycles, this table will be updated with specific version support windows._

## Reporting a Vulnerability

We take the security of BrainCraft.io projects seriously. If you have discovered a security vulnerability in any BrainCraft.io-owned repository, please report it to us as described below.

### Where to Report

**Please do not report security vulnerabilities through public GitHub issues.**

Instead, please report them via one of these methods:

1. **GitHub Security Advisories** (Preferred):
   - Navigate to the Security tab of the affected repository
   - Click "Report a vulnerability"
   - Fill out the security advisory form

2. **Email**:
   - Send details to: security@braincraft.io

### What to Include

Please include the following information to help us triage your report quickly:

- **Description**: Clear description of the vulnerability
- **Impact**: What can an attacker achieve with this vulnerability?
- **Affected Components**: Specific files, functions, or modules affected
- **Steps to Reproduce**:
  1. Detailed steps to reproduce the issue
  2. Include any relevant code snippets or proof-of-concept
  3. Screenshots if applicable
- **Possible Fix**: If you have suggestions on how to fix the issue
- **Your Environment**:
  - OS and version
  - Project version or commit hash
  - Any relevant dependencies and their versions

### What to Expect

- **Acknowledgment**: We will acknowledge receipt of your vulnerability report within 48 hours
- **Initial Assessment**: Within 7 days, we will send you an initial assessment of your report
- **Status Updates**: We will keep you informed about the progress of addressing the vulnerability
- **Resolution Timeline**: We aim to resolve critical vulnerabilities within 30 days, high severity within 60 days

### What We Promise

- We will not take legal action against you if you:
  - Give us reasonable time to respond to your report before public disclosure
  - Avoid privacy violations, destruction of data, and interruption or degradation of our services
  - Only interact with accounts you own or with our explicit permission
- We will acknowledge your contribution (unless you prefer to remain anonymous)
- We will strive to keep you informed about the progress of addressing your finding

## Disclosure Policy

We follow a coordinated disclosure model:

1. **Private Disclosure**: Security vulnerabilities are first disclosed privately to the project maintainers
2. **Fix Development**: We develop and test fixes for the vulnerability
3. **Patch Release**: We release patches for all supported versions
4. **Public Disclosure**: After patches are available, we publicly disclose the vulnerability details
5. **Credit**: We credit the reporter (unless anonymity is requested)

## Security Best Practices

For contributors and maintainers:

### Code Security
- Follow secure coding practices
- Validate all inputs
- Use parameterized queries for database operations
- Implement proper authentication and authorization
- Keep dependencies updated

### Dependency Management
- Regularly run `npm audit`, `pip audit`, or equivalent
- Monitor security advisories for dependencies
- Use tools like Dependabot for automatic updates
- Review dependency licenses for compatibility

### Secret Management
- Never commit secrets, API keys, or credentials
- Use environment variables for sensitive configuration
- Implement secret scanning in CI/CD pipelines
- Rotate credentials regularly

### Security Tools
We use the following tools to maintain security:
- GitHub Security Advisories
- CodeQL for static analysis
- SPDX/REUSE for license compliance
- Dependabot for dependency updates
- Secret scanning

## Recognition

We value and recognize security researchers who help keep our projects safe. Contributors who responsibly disclose vulnerabilities will be acknowledged in our release notes and security advisories (unless they prefer to remain anonymous).

## Contact

- Security Email: security@braincraft.io
- General Support: See [SUPPORT.md](./SUPPORT.md)

---

*Thank you for helping keep BrainCraft.io and our users safe!*