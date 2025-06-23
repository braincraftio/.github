# Fix Broken Links

## Internal Path Fixes (files moved from .github/ to root)

### In README.md:
- `.github/CONTRIBUTING.md` → `CONTRIBUTING.md`
- `.github/SECURITY.md` → `SECURITY.md`
- `.github/SUPPORT.md` → `SUPPORT.md`
- `.github/GOVERNANCE.md` → `GOVERNANCE.md`

### In CONTRIBUTING.md:
- `../LICENSE-Apache-2.0.txt` → `LICENSE-Apache-2.0.txt`
- `../LICENSE-CC-BY-4.0.txt` → `LICENSE-CC-BY-4.0.txt`

### In profile/README.md:
- `https://github.com/braincraftio/.github/blob/main/.github/CONTRIBUTING.md` → `https://github.com/braincraftio/.github/blob/main/CONTRIBUTING.md`
- `https://github.com/braincraftio/.github/blob/main/.github/CODE_OF_CONDUCT.md` → `https://github.com/braincraftio/.github/blob/main/CODE_OF_CONDUCT.md`
- `https://github.com/braincraftio/.github/blob/main/.github/SECURITY.md` → `https://github.com/braincraftio/.github/blob/main/SECURITY.md`

## GitHub Discussions Links (change to workspace repo)

### In all files:
- `https://github.com/braincraftio/workspace/discussions` → `https://github.com/braincraftio/workspace/discussions`

## Remove Non-Existent Resources

### In SECURITY.md:
- Remove mention of `SECURITY_HALL_OF_FAME.md` (line ~114)
- Remove or update `https://braincraft.io/security.asc` PGP key references

### In README.md & FUNDING.yml:
- Remove `https://ko-fi.com/braincraftio` (account doesn't exist)