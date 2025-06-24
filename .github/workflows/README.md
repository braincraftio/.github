<!--
SPDX-FileCopyrightText: 2025 BrainCraft.io
SPDX-License-Identifier: CC-BY-4.0
-->

# Organization Workflows

This directory contains reusable GitHub Actions workflows that provide standardized automation across all BrainCraft.io repositories. These workflows follow a dual-purpose design pattern, running directly in this repository while also being callable from any other repository in the organization.

## Table of Contents

- [Quick Start](#quick-start)
- [Available Workflows](#available-workflows)
  - [SPDX License Header Check](#spdx-license-header-check)
  - [Markdown Link Validation](#markdown-link-validation)
- [How to Use Workflows](#how-to-use-workflows)
  - [Basic Usage](#basic-usage)
  - [With Custom Parameters](#with-custom-parameters)
  - [Integration Patterns](#integration-patterns)
- [Workflow Architecture](#workflow-architecture)
  - [Dual-Purpose Design](#dual-purpose-design)
  - [Input Parameters](#input-parameters)
  - [Output Artifacts](#output-artifacts)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## Quick Start

To use any workflow in your repository, create a `.github/workflows/` directory and add a workflow file:

```yaml
name: License and Link Checks
on: [push, pull_request]

jobs:
  license-check:
    uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
  
  link-check:
    uses: braincraftio/.github/.github/workflows/markdown-link-check.yml@main
```

## Available Workflows

### SPDX License Header Check

**File**: `spdx-header-check.yml`

Validates SPDX license headers and REUSE compliance across your repository. Generates Software Bill of Materials (SBOM) and provides detailed feedback on missing or incorrect license headers.

**Features:**
- REUSE specification compliance validation
- SPDX SBOM generation in standard format
- Detailed error reporting with suggested fixes
- Support for custom REUSE tool versions
- Configurable working directories

**Triggers:**
- Push to main/master branches
- Pull requests to main/master branches
- Manual workflow dispatch

**Artifacts:**
- SPDX SBOM (JSON format, 30-day retention)

### Markdown Link Validation

**File**: `markdown-link-check.yml`

Validates all links in Markdown files to ensure they remain accessible and functional. Supports custom configuration and provides comprehensive reporting.

**Features:**
- Comprehensive link validation (HTTP/HTTPS, anchors, relative paths)
- Custom configuration support
- Scheduled validation (weekly)
- Pull request commenting on failures
- Configurable timeout and retry logic

**Triggers:**
- Push to main/master branches (when .md files change)
- Pull requests to main/master branches (when .md files change)
- Weekly schedule (Sundays at midnight UTC)
- Manual workflow dispatch

**Artifacts:**
- Detailed link check logs (7-day retention, on failure)

## How to Use Workflows

### Basic Usage

The simplest way to use organization workflows is to reference them directly:

```yaml
name: Repository Validation
on: [push, pull_request]

jobs:
  license-compliance:
    uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
  
  documentation-quality:
    uses: braincraftio/.github/.github/workflows/markdown-link-check.yml@main
```

### With Custom Parameters

Workflows accept input parameters for customization:

```yaml
name: Custom Validation
on: [push, pull_request]

jobs:
  license-check:
    uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
    with:
      python-version: '3.11'
      reuse-version: '2.1.0'
      working-directory: './src'
  
  link-check:
    uses: braincraftio/.github/.github/workflows/markdown-link-check.yml@main
    with:
      config-file: '.github/link-check-config.json'
      check-modified-only: true
      fail-on-error: false
```

### Integration Patterns

**Conditional Execution:**
```yaml
jobs:
  license-check:
    if: github.event_name == 'push' || github.base_ref == 'main'
    uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
```

**Matrix Strategy:**
```yaml
jobs:
  multi-directory-check:
    strategy:
      matrix:
        directory: ['./docs', './api', './examples']
    uses: braincraftio/.github/.github/workflows/markdown-link-check.yml@main
    with:
      file-path: ${{ matrix.directory }}
```

**Dependent Jobs:**
```yaml
jobs:
  license-check:
    uses: braincraftio/.github/.github/workflows/spdx-header-check.yml@main
  
  link-check:
    needs: license-check
    uses: braincraftio/.github/.github/workflows/markdown-link-check.yml@main
```

## Workflow Architecture

### Dual-Purpose Design

Each workflow operates in two modes:

1. **Direct Execution**: Runs automatically in the `.github` repository when triggered by push, pull request, or schedule events
2. **Reusable Call**: Can be invoked from other repositories using the `workflow_call` trigger

This design ensures workflows are tested and validated in the central repository while remaining available for organization-wide use.

### Input Parameters

All workflows accept optional input parameters with sensible defaults:

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `python-version` | string | `'3.x'` | Python version for tool installation |
| `working-directory` | string | `'.'` | Directory to run checks in |
| `config-file` | string | `'mlc_config.json'` | Configuration file path |
| `fail-on-error` | boolean | `true` | Whether to fail workflow on errors |

### Output Artifacts

Workflows generate artifacts for further analysis:

- **SPDX SBOM**: Machine-readable software bill of materials
- **Link Check Reports**: Detailed logs of validation results
- **Error Summaries**: Human-readable failure explanations

## Best Practices

### Repository Setup

1. **Create workflow early**: Add organization workflows when setting up new repositories
2. **Use consistent naming**: Follow established patterns for workflow file names
3. **Document customizations**: Comment any non-standard parameter usage

### Configuration Management

1. **Centralize config files**: Store workflow configurations in `.github/` directory
2. **Version control configs**: Include configuration files in repository history
3. **Environment-specific settings**: Use different configs for development vs. production

### Error Handling

1. **Review failure logs**: Check workflow summaries and artifacts for detailed error information
2. **Fix issues promptly**: Address license and link issues before they accumulate
3. **Use failure notifications**: Configure team notifications for workflow failures

### Performance Optimization

1. **Scope appropriately**: Use `file-path` and `working-directory` parameters to limit scope
2. **Cache dependencies**: Workflows include caching for better performance
3. **Schedule wisely**: Use scheduled runs for comprehensive checks, not every commit

## Troubleshooting

### Common Issues

**SPDX License Check Failures:**
- Missing SPDX headers on files
- Incorrect license identifiers
- Files not covered by REUSE.toml configuration

*Solution*: Review the generated error report and add appropriate SPDX headers or update REUSE.toml to exclude files that don't require headers.

**Markdown Link Check Failures:**
- Broken external links
- Invalid internal references
- Temporary network issues

*Solution*: Examine the detailed link report, fix broken links, or add problematic URLs to the ignore list in your configuration file.

**Workflow Not Found Errors:**
- Incorrect repository reference
- Missing `@main` version specifier
- Private repository access issues

*Solution*: Verify the workflow path follows the pattern `braincraftio/.github/.github/workflows/workflow-name.yml@main`.

### Configuration Examples

**Custom REUSE Configuration** (`REUSE.toml`):
```toml
version = 1

[[annotations]]
path = ["tests/**", "examples/**"]
SPDX-License-Identifier = "CC0-1.0"
SPDX-FileCopyrightText = "2025 BrainCraft.io"

[[annotations]]
path = "vendor/**"
SPDX-License-Identifier = "LicenseRef-vendor"
SPDX-FileCopyrightText = "Various vendors"
```

**Custom Link Check Configuration** (`mlc_config.json`):
```json
{
  "ignorePatterns": [
    { "pattern": "^http://localhost" },
    { "pattern": "^https://example.internal" },
    { "pattern": "^#" }
  ],
  "timeout": "30s",
  "retryOn429": true,
  "retryCount": 3,
  "aliveStatusCodes": [200, 201, 202, 204, 301, 302, 307, 308]
}
```

### Getting Help

1. **Check workflow logs**: Review the detailed logs and artifacts generated by failed workflows
2. **Review configuration**: Verify input parameters and configuration files are correct
3. **Consult documentation**: Reference the workflow files directly for parameter details
4. **Create issues**: Report bugs or request features in the `.github` repository

## Contributing

Workflows are maintained in the central `.github` repository. To contribute:

1. **Follow existing patterns**: New workflows should use the dual-purpose design
2. **Include comprehensive documentation**: Document all inputs, outputs, and usage examples
3. **Add proper testing**: Ensure workflows are tested in the central repository
4. **Update this guide**: Add documentation for new workflows to this README

### Workflow Development Guidelines

- Use semantic versioning for workflow references (`@main`, `@v1.0.0`)
- Include SPDX headers in all workflow files
- Provide sensible defaults for all input parameters
- Generate meaningful artifacts and summaries
- Follow security best practices for secret handling
- Implement proper error handling and user feedback

---

*This documentation is maintained alongside the workflow implementations. For the most current information, refer to the individual workflow files and their inline documentation.*