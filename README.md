<!--
SPDX-FileCopyrightText: 2025 BrainCraft.io
SPDX-License-Identifier: Apache-2.0
-->

# .github

[![REUSE Compliant](https://img.shields.io/badge/REUSE-compliant-green)](https://reuse.software/)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Organization-wide default community health files, reusable workflows, and GitHub configuration for BrainCraft.io.

## 📋 Overview

This special `.github` repository provides:
- 🏥 **Community Health Files** - Default files for all repos (CONTRIBUTING, SECURITY, etc.)
- 🔄 **Reusable Workflows** - Shared GitHub Actions workflows
- 📝 **Templates** - Issue and PR templates for consistency
- 🎨 **Organization Profile** - Public-facing organization README
- 📐 **Standards** - Code ownership, .gitignore, and dependency management templates

## 🚀 Quick Start

### For Repository Maintainers

1. **Using Default Files**: Any file in this repo's `.github/` directory will be used as a default for repos that don't have their own version.

2. **Using Reusable Workflows**:
   ```yaml
   jobs:
     license-check:
       uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
   ```

3. **Using Templates**: Copy templates from the `templates/` directory and customize for your repository.

### For Contributors

See our [Contributing Guidelines](.github/CONTRIBUTING.md) to get started. We welcome contributions from everyone!

## 📁 Repository Structure

```
.github/                        # This repository
├── .github/                    # Community health files (inherited by all repos)
│   ├── ISSUE_TEMPLATE/        # Issue templates
│   ├── PULL_REQUEST_TEMPLATE/ # PR templates  
│   ├── CODE_OF_CONDUCT.md     # Code of conduct
│   ├── CONTRIBUTING.md        # Contribution guidelines
│   ├── FUNDING.yml           # Funding/sponsorship links
│   ├── GOVERNANCE.md         # Governance model
│   ├── SECURITY.md           # Security policy
│   ├── SUPPORT.md            # Support resources
│   └── pull_request_template.md # Default PR template
├── profile/                   # Organization profile
│   ├── README.md             # Displayed on github.com/braincraftio
│   └── assets/               # Images and media
├── workflows/                 # Reusable workflows
├── templates/                 # Template files for new repos
├── LICENSES/                  # License texts (REUSE standard)
└── REUSE.toml                # License compliance configuration
```

## 🏥 Community Health Files

The following files in `.github/` are automatically inherited by all repositories in the organization:

| File | Purpose | Override |
|------|---------|----------|
| `CODE_OF_CONDUCT.md` | Community behavior standards | Repo-specific overrides org default |
| `CONTRIBUTING.md` | How to contribute | Repo-specific overrides org default |
| `SECURITY.md` | Security vulnerability reporting | Repo-specific overrides org default |
| `SUPPORT.md` | Where to get help | Repo-specific overrides org default |
| `FUNDING.yml` | Sponsorship/donation links | Repo-specific extends org default |
| `GOVERNANCE.md` | Decision-making process | Repo-specific overrides org default |

## 📝 Issue & PR Templates

We provide comprehensive templates for:
- 🐛 **Bug Reports** - Structured bug reporting with environment details
- ✨ **Feature Requests** - Propose new features with use cases
- 📚 **Documentation** - Report docs issues or improvements
- 🔒 **Security** - Redirects to private security reporting

### Using Templates

Templates are automatically available when creating issues/PRs. For specific PR templates:
```
https://github.com/braincraftio/[repo]/compare/main...branch?template=feature.md
```

## 🔄 Reusable Workflows

Current workflows available:
- `spdx-header-check.yml` - Validates SPDX license headers

Coming soon:
- License compliance checking
- Security scanning
- Code quality checks
- Automated releases

## 📐 Templates

The `templates/` directory contains starter files for new repositories:

- **CODEOWNERS.template** - Define code ownership and review assignments
- **dependabot.yml.template** - Automated dependency updates configuration
- **.gitignore.template** - Comprehensive ignore patterns for multiple languages

## 📜 License Compliance

This repository is [REUSE compliant](https://reuse.software/), ensuring clear and machine-readable licensing:

- ✅ Every file has a clear license
- 📄 Standard license texts in `LICENSES/`
- 🤖 Automated compliance checking
- 📊 SBOM generation support

### Our Dual-License Model

- **Code & Configuration**: [Apache License 2.0](LICENSE-Apache-2.0.txt)
- **Documentation & Media**: [Creative Commons Attribution 4.0](LICENSE-CC-BY-4.0.txt)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](.github/CONTRIBUTING.md) for details on:
- Code style and standards
- Pull request process
- Development setup
- Testing requirements

## 🔒 Security

Security is a top priority. Please see our [Security Policy](.github/SECURITY.md) for:
- Vulnerability reporting procedures
- Security update process
- Responsible disclosure guidelines

**Never report security issues publicly!**

## 💬 Support

Need help? Check out our [Support Guide](.github/SUPPORT.md) or:
- 💭 [GitHub Discussions](https://github.com/braincraftio/.github/discussions)
- 🐛 [Issue Tracker](https://github.com/braincraftio/.github/issues)
- 📧 Email: hello@braincraft.io

## 🏛️ Governance

Learn about our decision-making process in [GOVERNANCE.md](.github/GOVERNANCE.md).

## 💝 Funding

Support BrainCraft.io development:
- [GitHub Sponsors](https://github.com/sponsors/braincraftio)
- [Open Collective](https://opencollective.com/braincraftio)
- [Ko-fi](https://ko-fi.com/braincraftio)
- [Patreon](https://patreon.com/braincraftio)

## 📊 Status

- **Compliance**: REUSE compliant ✅
- **Health**: All community files present ✅
- **Templates**: Issue & PR templates ready ✅
- **Workflows**: Basic workflows available 🚧

## 🔗 Links

- [Organization Profile](https://github.com/braincraftio)
- [Documentation](https://github.com/braincraftio/.github/wiki)
- [Discussions](https://github.com/braincraftio/.github/discussions)

---

*Building the future of open source, one commit at a time.* 💜