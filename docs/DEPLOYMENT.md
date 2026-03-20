# Deployment Checklist

Use this checklist when deploying updates to DeepSeek Brain Skill.

---

## Pre-Deployment

### Code Quality

- [ ] All tests pass (`./scripts/test.sh`)
- [ ] No syntax errors (`python3 -m py_compile skills/deepseek-brain/*.py`)
- [ ] Code formatted consistently
- [ ] No hardcoded secrets (except example API key)
- [ ] `.gitignore` is up to date

### Documentation

- [ ] README.md updated with new features
- [ ] CHANGELOG.md entry added
- [ ] Version number incremented
- [ ] Examples updated if needed

### Testing

- [ ] Fresh install tested
- [ ] Upgrade from previous version tested
- [ ] All commands work (`deepseek`, `deepseek-brain`, `ds`)
- [ ] API connection verified
- [ ] Error handling tested

---

## Version Bump

### Update Version Files

```bash
# 1. Update version in README.md
# Change: ![Version](https://img.shields.io/badge/version-1.0.0-blue)
# To:     ![Version](https://img.shields.io/badge/version-1.1.0-blue)

# 2. Update skill.json
# Change: "version": "1.0.0"
# To:     "version": "1.1.0"

# 3. Create CHANGELOG entry
```

### Changelog Format

```markdown
## [1.1.0] - 2024-03-20

### Added
- New feature description

### Changed
- Improved existing feature

### Fixed
- Bug fix description

### Removed
- Deprecated feature
```

---

## Git Workflow

### Create Release Branch

```bash
git checkout -b release/v1.1.0
# Make version changes
git add -A
git commit -m "Bump version to 1.1.0"
git push origin release/v1.1.0
```

### Pull Request

- [ ] PR created from `release/v1.1.0` to `main`
- [ ] PR reviewed and approved
- [ ] All CI checks pass
- [ ] PR merged

### Tag Release

```bash
git checkout main
git pull origin main
git tag -a v1.1.0 -m "Release v1.1.0"
git push origin v1.1.0
```

---

## GitHub Release

### Create Release Notes

```markdown
## DeepSeek Brain Skill v1.1.0

### What's New

🧠 **New Features**
- Feature 1 description
- Feature 2 description

🐛 **Bug Fixes**
- Fix 1 description
- Fix 2 description

### Installation

```bash
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/v1.1.0/scripts/install.sh | bash
```

### Full Changelog

https://github.com/YOUR_USERNAME/deepseek-brain-skill/compare/v1.0.0...v1.1.0
```

### GitHub Release Steps

1. Go to GitHub repo → Releases → Create Release
2. Tag: `v1.1.0`
3. Title: "DeepSeek Brain Skill v1.1.0"
4. Paste release notes
5. Click "Publish Release"

---

## Post-Deployment

### Verify Installation

```bash
# Test fresh install
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/v1.1.0/scripts/install.sh | bash

# Verify version
deepseek --version  # (if implemented)

# Test basic command
deepseek "say hello"
```

### Update Documentation

- [ ] Landing page updated
- [ ] npm package updated (if applicable)
- [ ] Discord/Slack announced
- [ ] Email newsletter sent (for major releases)

### Monitor

- [ ] Watch for error reports
- [ ] Check GitHub issues
- [ ] Monitor Discord/Slack for problems
- [ ] Track usage metrics

---

## Emergency Rollback

If something goes wrong:

```bash
# 1. Tag current broken state
git tag -a v1.1.0-broken -m "Broken release"

# 2. Reset to previous release
git checkout main
git reset --hard v1.0.0
git push origin main --force

# 3. Delete broken tag
git tag -d v1.1.0
git push origin :refs/tags/v1.1.0

# 4. Announce rollback
# Post in Discord/Slack/GitHub about the issue
```

---

## Automated Deployment (Future)

### GitHub Actions Workflow

```yaml
# .github/workflows/release.yml

name: Release

on:
  push:
    tags:
      - 'v*'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Test
        run: ./scripts/test.sh
      
      - name: Create Release
        uses: softprops/action-gh-release@v1
        with:
          generate_release_notes: true
```

### NPM Package (Future)

```bash
# If distributing via npm
npm publish

# Users install with:
npx deepseek-brain-skill
```

---

## Communication Templates

### Discord/Slack Announcement

```
🎉 **DeepSeek Brain Skill v1.1.0 is here!**

What's new:
✨ New feature 1
✨ New feature 2
🐛 Bug fixes

Install/Update:
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/v1.1.0/scripts/install.sh | bash

Full changelog: https://github.com/YOUR_USERNAME/deepseek-brain-skill/releases/tag/v1.1.0
```

### Email Newsletter

```
Subject: DeepSeek Brain Skill v1.1.0 - [Exciting Feature]

Hi [Name],

We're excited to announce DeepSeek Brain Skill v1.1.0!

🎯 What's New

[Feature description]

🚀 How to Update

curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/v1.1.0/scripts/install.sh | bash

Thanks for being a valued user!

- The DeepSeek Brain Team
```

---

**Remember:** Always test in a staging environment before deploying to production!
