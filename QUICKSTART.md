# DeepSeek Brain Skill - Quick Reference

## One-Line Install

```bash
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/main/scripts/install.sh | bash
```

## Usage

```bash
# In Qwen Code chat
"plug in to deepseek brain"

# Terminal commands
deepseek "create a flask app"
deepseek-brain              # interactive mode
ds "quick task"             # short alias
deepseek --reset "new task" # fresh context
```

## Repo Structure

```
deepseek-brain-skill/
├── skills/deepseek-brain/   # Core skill files
│   ├── run.py              # Main entry point
│   ├── deepseek-brain.py   # Interactive mode
│   ├── deepseek-loop.py    # Auto-execute loop
│   ├── SKILL.md            # Skill definition
│   └── skill.json          # Manifest
├── scripts/
│   ├── install.sh          # One-line installer
│   ├── uninstall.sh        # Clean removal
│   └── test.sh             # Test suite
├── docs/
│   ├── ARCHITECTURE.md     # Technical deep dive
│   ├── SAAS-GUIDE.md       # Monetization guide
│   └── DEPLOYMENT.md       # Release process
├── examples/
│   └── 01-basic-usage.md   # Usage examples
├── README.md
├── LICENSE
└── CHANGELOG.md
```

## Key Features

✅ DeepSeek R1 reasoning + Qwen Code execution
✅ YOLO mode (auto-execute, no confirmations)
✅ Conversation history persistence
✅ One-line install/uninstall
✅ Complete documentation
✅ SaaS-ready architecture

## Pricing Tiers (SaaS)

| Tier | Price | Features |
|------|-------|----------|
| Free | $0 | Basic skill, community support |
| Pro | $9/mo | Priority support, analytics, templates |
| Team | $29/mo | Team management, shared history |
| Enterprise | $49/mo | Custom integrations, SLA, on-prem |

## API Configuration

- **Endpoint:** `https://api.deepseek.com/v1/chat/completions`
- **Model:** `deepseek-reasoner`
- **API Key:** User-provided (DeepSeek account required)
- **Timeout:** 120s API, 300s commands

## Support

- 📖 Docs: `/docs/` folder
- 🐛 Issues: GitHub Issues
- 💬 Community: Discord/Slack (future)
- 📧 Email: support@deepseek-brain.dev (future)

## Quick Reset

```bash
# Clear conversation history
rm /tmp/deepseek-qwen-history.json

# Reinstall skill
./scripts/uninstall.sh && ./scripts/install.sh
```

---

**Built with ❤️ for the AI-powered future**
