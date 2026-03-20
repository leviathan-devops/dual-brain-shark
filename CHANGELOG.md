# Changelog

All notable changes to DeepSeek Brain Skill will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2024-03-20

### Added

🧠 **Initial Release**

- Double-brain architecture (DeepSeek R1 + Qwen Code)
- YOLO mode for automatic command execution
- Interactive terminal mode (`deepseek-brain`)
- One-line installer (`curl ... | bash`)
- Complete documentation suite:
  - `ARCHITECTURE.md` - Technical deep dive
  - `SAAS-GUIDE.md` - Productization guide
  - `DEPLOYMENT.md` - Release process
- Example usage guide (`examples/01-basic-usage.md`)
- Test suite (`scripts/test.sh`)
- Uninstall script (`scripts/uninstall.sh`)
- Bash aliases (`deepseek`, `ds`, `deepseek-brain`)

### Files

- `skills/deepseek-brain/run.py` - Main entry point
- `skills/deepseek-brain/deepseek-brain.py` - Interactive mode
- `skills/deepseek-brain/deepseek-loop.py` - Full loop executor
- `skills/deepseek-brain/deepseek-client.py` - API client
- `skills/deepseek-brain/qwen-integration.py` - Qwen Code integration
- `skills/deepseek-brain/SKILL.md` - Skill definition
- `skills/deepseek-brain/skill.json` - Manifest
- `scripts/install.sh` - One-line installer
- `scripts/test.sh` - Test suite
- `scripts/uninstall.sh` - Clean removal

### Configuration

- API key: `sk-e8e93e31b582423e9fdaa4ab8e9347e2` (hardcoded for convenience)
- History file: `/tmp/deepseek-qwen-history.json`
- Model: `deepseek-reasoner`
- Timeout: 120s API, 300s commands

### Known Issues

- Skill tool in Qwen Code may not auto-discover the skill (use direct Python call)
- Conversation history persists until manually reset

---

## [Unreleased]

### Planned

- Multi-model support (Claude, GPT-4)
- Streaming responses
- Command preview mode
- Undo system for executed commands
- Sandbox mode (container execution)
- Team collaboration features
- Analytics dashboard
- Custom command templates
- Plugin system

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2024-03-20 | Initial release |

---

## Migration Guide

### From v1.0.0 to v1.1.0 (Future)

```bash
# Update installation
cd ~/.qwen/skills/deepseek-brain
git pull origin main
```

---

**Breaking Changes:** None in v1.0.0

**Deprecations:** None in v1.0.0
