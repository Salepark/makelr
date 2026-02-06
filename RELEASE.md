# Makelr Release Process

This document describes how Makelr versions are prepared, released, and maintained.

Our goals are:
- Predictable releases
- Clear communication
- Safe upgrades
- Traceable changes

---

## Versioning

Makelr follows **Semantic Versioning**:

MAJOR.MINOR.PATCH

- MAJOR: Breaking changes (incompatible API, schema, or workflow changes)
- MINOR: New features, backward-compatible
- PATCH: Bug fixes and small improvements, backward-compatible

Examples:
- 1.0.0 → first stable release
- 1.1.0 → new features added
- 1.1.1 → bug fix only

---

## Release Types

### 1. Major Release (X.0.0)

Used when:
- Database schema or API changes are breaking
- Core architecture changes
- Migration is required for users

Requirements:
- Migration guide (if applicable)
- Architecture / design docs updated
- CHANGELOG.md updated with clear breaking changes section

---

### 2. Minor Release (X.Y.0)

Used when:
- New features are added
- Existing features are improved
- No breaking changes

Requirements:
- CHANGELOG.md updated
- Basic regression testing
- UI and docs updated if needed

---

### 3. Patch Release (X.Y.Z)

Used when:
- Bug fixes
- Performance improvements
- Small internal refactors

Requirements:
- CHANGELOG.md updated
- Tests pass
- No behavior-breaking changes

---

## Release Workflow

### Step 1: Prepare

- Make sure the main branch is stable
- All tests must pass
- Review open issues and pull requests
- Decide the next version number

---

### Step 2: Update Documentation

- Update CHANGELOG.md
  - Move items from [Unreleased] to the new version section
  - Add release date
- Update any relevant docs:
  - README.md
  - ARCHITECTURE.md
  - DEVELOPMENT.md (if needed)

---

### Step 3: Version Bump

- Update version number in:
  - package.json (if applicable)
  - Any other version references in the project

- Commit message example:
  chore: bump version to 0.8.0

---

### Step 4: Create Release Commit

- Ensure the commit includes:
  - Version bump
  - CHANGELOG.md update
  - Any final fixes

- Commit message example:
  release: 0.8.0

---

### Step 5: Tag the Release

Create a Git tag:

git tag v0.8.0  
git push origin v0.8.0

Tag format:
- Always prefix with v
- Examples: v0.7.0, v1.0.0

---

### Step 6: GitHub Release

On GitHub:

1. Go to Releases
2. Click "Draft a new release"
3. Select the tag (for example, v0.8.0)
4. Title: Makelr v0.8.0
5. Description:
   - Copy the relevant section from CHANGELOG.md
6. Publish the release

---

## Hotfix Process

If a critical bug is found after release:

1. Create a fix branch from the release tag
2. Apply the fix
3. Bump PATCH version (for example, 0.8.0 → 0.8.1)
4. Update CHANGELOG.md
5. Tag and release again

---

## Pre-release (Optional)

For experimental versions:

- Use suffixes:
  - -alpha
  - -beta
  - -rc

Examples:
- 0.8.0-alpha.1
- 1.0.0-rc.1

These should:
- Be clearly marked as unstable
- Not be considered production-ready

---

## What a Release Should Contain

Every release should have:

- Updated CHANGELOG.md
- Clear version number
- Passing tests
- No unreviewed critical issues
- Clear description of:
  - What was added
  - What changed
  - What was fixed
  - Any risks or migration notes

---

## Responsibility

- Maintainers are responsible for:
  - Deciding when to release
  - Reviewing changes
  - Tagging and publishing releases

- Contributors help by:
  - Writing good pull request descriptions
  - Updating docs when needed
  - Reporting regressions

---

## Summary

Releases in Makelr are:

- Versioned using Semantic Versioning
- Documented in CHANGELOG.md
- Tagged in Git
- Published via GitHub Releases
- Focused on stability, clarity, and user trust

---

Makelr — Build Your Automation, Your Way.
