<!--
SPDX-FileCopyrightText: 2025 BrainCraft.io
SPDX-License-Identifier: CC-BY-4.0
-->

# Contributing to BrainCraft.io

First of all, thank you for your interest in contributing to BrainCraft.io — a community committed to open knowledge, equity, and sustainable software ecosystems.

## Code of Conduct

Please review and respect our [Code of Conduct](./CODE_OF_CONDUCT.md). All contributors are expected to create a safe, respectful, and inclusive environment.

## How to Contribute

There are many ways to contribute, including but not limited to:

- 🐛 Submitting bug reports and feature requests
- 📝 Improving documentation or translations
- 💻 Contributing code and tests
- 💬 Participating in community discussions
- 👀 Reviewing pull requests
- 🎨 Designing graphics and improving UI/UX
- 📢 Writing blog posts and tutorials
- 🧪 Testing pre-release versions

We welcome contributions from everyone — individuals, teams, students, educators, and professionals across industries.

## Getting Started

### 1. Find Something to Work On

- Check out our [good first issue](https://github.com/braincraftio/.github/labels/good%20first%20issue) label
- Browse [help wanted](https://github.com/braincraftio/.github/labels/help%20wanted) issues
- Look through open [feature requests](https://github.com/braincraftio/.github/labels/enhancement)
- Join discussions about upcoming features

### 2. Before You Start

- Comment on the issue to let others know you're working on it
- Ask questions if anything is unclear
- For large features, discuss your approach first
- Check if someone else is already working on it

## Development Setup

Each project may have specific setup requirements. Generally:

```bash
# Clone the repository
git clone https://github.com/braincraftio/[project-name]
cd [project-name]

# Install dependencies (varies by project)
npm install    # For Node.js projects
go mod tidy    # For Go projects
pip install -r requirements.txt  # For Python projects

# Run tests
npm test       # Node.js
go test ./...  # Go
pytest         # Python
```

See individual project READMEs for specific instructions.

## Workflow

### 1. Fork and Clone

```bash
# Fork on GitHub, then:
git clone https://github.com/YOUR-USERNAME/[project-name]
cd [project-name]
git remote add upstream https://github.com/braincraftio/[project-name]
```

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-number-description
```

### 3. Make Your Changes

- Write clean, readable code
- Add tests for new functionality
- Update documentation as needed
- Follow existing code style

### 4. Commit Your Changes

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```bash
# Format: <type>(<scope>): <subject>

git commit -m "feat: add new authentication method"
git commit -m "fix: resolve memory leak in parser"
git commit -m "docs: update installation instructions"
git commit -m "test: add unit tests for auth module"
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code changes that neither fix bugs nor add features
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### 5. Push and Create Pull Request

```bash
git push origin feature/your-feature-name
```

Then open a pull request on GitHub.

## Pull Request Process

### Before Submitting

- [ ] Tests pass locally
- [ ] Code follows project style guidelines
- [ ] Documentation is updated
- [ ] Commit messages follow conventions
- [ ] PR description clearly explains changes

### PR Description Template

Your PR description should include:

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix (non-breaking change)
- [ ] New feature (non-breaking change)
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented complex code
- [ ] I have updated the documentation
- [ ] My changes generate no new warnings
```

### Code Review Process

1. Automated checks run (tests, linting, security)
2. Maintainers review code for:
   - Correctness and completeness
   - Performance implications
   - Security considerations
   - Architectural fit
3. Address feedback through new commits
4. Once approved, maintainer merges PR

## Code Style Guidelines

### General Principles

- **Clarity over cleverness**: Write code that's easy to understand
- **Consistency**: Follow existing patterns in the codebase
- **Documentation**: Comment complex logic and public APIs
- **Testing**: Aim for high test coverage of critical paths

### Language-Specific Guidelines

#### Go
- Follow [Effective Go](https://golang.org/doc/effective_go.html)
- Use `gofmt` and `golint`
- Write table-driven tests

#### JavaScript/TypeScript
- Use ESLint configuration
- Prefer functional programming patterns
- Use TypeScript for type safety

#### Python
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- Use type hints where appropriate
- Write docstrings for public functions

### Documentation Standards

- Use clear, concise language
- Include code examples
- Keep README files up to date
- Document breaking changes

## DCO (Developer Certificate of Origin)

We use the [Developer Certificate of Origin (DCO)](https://developercertificate.org/) to ensure contributors have the right to submit their work.

### Signing Your Commits

Add a sign-off to your commits:

```bash
git commit -s -m "Your commit message"
```

This adds a `Signed-off-by` line to your commit message.

### What This Means

By signing off, you certify that:
1. You created the contribution or have the right to submit it
2. The contribution is made under the project's license
3. You understand the contribution may be public forever

## Community Support

### Where to Get Help

- 💬 [GitHub Discussions](https://github.com/braincraftio/workspace/discussions)
- 🐛 [Issue Tracker](https://github.com/braincraftio/.github/issues)
- 📧 Email: hello@braincraft.io

### Being a Good Community Member

- Be respectful and inclusive
- Help others when you can
- Give credit where it's due
- Be patient with new contributors
- Celebrate successes together

## Recognition

We value all contributions and recognize our contributors through:
- Credits in release notes
- Contributors section in documentation
- Shoutouts in community updates
- Invitation to maintainer team (for regular contributors)

## Questions?

If you have questions about contributing:
1. Check existing documentation
2. Search closed issues and discussions
3. Ask in GitHub Discussions
4. Email us at hello@braincraft.io

Together, we're building infrastructure for a more equitable and joyful technological future.

## Licensing of Contributions

All contributions to BrainCraft.io repositories are made under our dual-license model:

- **Code and configuration** are licensed under the [Apache License 2.0](LICENSE-Apache-2.0.txt)
- **Documentation and creative assets** are licensed under the [Creative Commons Attribution 4.0](LICENSE-CC-BY-4.0.txt)

By submitting a pull request, issue, or suggestion, you agree that your contributions may be used under either or both licenses as applicable. Please include SPDX headers when appropriate.

To summarize:
> You retain copyright to your work, but grant BrainCraft.io the right to
> use, distribute, and relicense it under the above terms.

For SPDX tag guidance, see: [https://spdx.org/licenses/](https://spdx.org/licenses/)

---

*Thank you for helping make BrainCraft.io better! Your contributions make a difference.* 💜