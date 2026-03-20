# DeepSeek Brain Skill 🧠

**Qwen Code + DeepSeek R1 = Double-Brain Architecture**

DeepSeek R1 provides the reasoning. Qwen Code provides the execution. Together, they form a powerful AI agent with full device access.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Python](https://img.shields.io/badge/python-3.8+-blue)

---

## 🚀 Quick Start

### One-Line Install

```bash
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/main/scripts/install.sh | bash
```

### Manual Install

```bash
git clone https://github.com/YOUR_USERNAME/deepseek-brain-skill.git
cd deepseek-brain-skill
./scripts/install.sh
```

### Usage

```bash
# In Qwen Code chat, say:
"plug in to deepseek brain"

# Or run directly:
deepseek "create a flask API"
deepseek-brain  # interactive mode
```

---

## 🧠 What Is This?

This is a **skill** for Qwen Code (the AI coding assistant) that connects to DeepSeek R1's API for enhanced reasoning capabilities.

### The Problem
- Qwen Code has device access but limited reasoning
- DeepSeek R1 has superior reasoning but no device access

### The Solution
- **DeepSeek R1** = The BRAIN (reasoning, planning, complex tasks)
- **Qwen Code** = The HANDS (execution, file access, command execution)

### Architecture

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│   You       │ ──→ │  Qwen Code   │ ──→ │ DeepSeek R1 │
│  (input)    │     │  (executor)  │     │  (brain)    │
└─────────────┘     └──────────────┘     └─────────────┘
                           ↓
                    ┌──────────────┐
                    │   bash cmd   │
                    │   execution  │
                    └──────────────┘
```

---

## 📦 What's Included

```
deepseek-brain-skill/
├── skills/deepseek-brain/    # The skill files (installed to ~/.qwen/skills/)
│   ├── SKILL.md              # Skill definition & documentation
│   ├── skill.json            # Skill manifest
│   ├── run.py                # Main entry point
│   ├── deepseek-brain.py     # Interactive terminal mode
│   ├── deepseek-loop.py      # Full auto-execute loop
│   └── deepseek-client.py    # API client library
├── scripts/
│   ├── install.sh            # One-line installer
│   └── uninstall.sh          # Clean removal
├── examples/
│   ├── 01-basic-usage.md     # Simple examples
│   ├── 02-web-development.md # Flask, React, Next.js
│   ├── 03-system-admin.md    # Server management
│   └── 04-data-processing.md # CSV, JSON, analysis
├── docs/
│   ├── ARCHITECTURE.md       # Technical deep dive
│   ├── CONFIGURATION.md      # Advanced settings
│   └── TROUBLESHOOTING.md    # Common issues
├── tests/
│   └── test-skill.py         # Automated tests
├── README.md                 # This file
├── LICENSE                   # MIT License
└── .env.example              # Environment template
```

---

## 🎯 Use Cases

### 1. Web Development
```bash
deepseek "create a Next.js app with Tailwind CSS and user authentication"
```

### 2. Data Processing
```bash
deepseek "analyze this CSV and create visualizations for the top 10 trends"
```

### 3. System Administration
```bash
deepseek "set up nginx with SSL, configure firewall, and deploy my app"
```

### 4. Code Refactoring
```bash
deepseek "refactor this Python codebase to use async/await and add type hints"
```

### 5. Debugging
```bash
deepseek "find why my Flask app is crashing and fix it"
```

---

## ⚙️ Configuration

### Environment Variables

```bash
# Required: Your DeepSeek API key
export DEEPSEEK_API_KEY="sk-your-key-here"

# Optional: Custom settings
export DEEPSEEK_HISTORY_FILE="/tmp/deepseek-history.json"
export DEEPSEEK_MODEL="deepseek-reasoner"
export DEEPSEEK_TIMEOUT="120"
export DEEPSEEK_MAX_LOOPS="10"
```

### Configuration File

Create `~/.deepseek-brain/config.json`:

```json
{
  "api_key": "sk-your-key-here",
  "model": "deepseek-reasoner",
  "timeout": 120,
  "max_loops": 10,
  "yolo_mode": true,
  "verbose": false
}
```

---

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | Technical deep dive |
| [docs/CONFIGURATION.md](docs/CONFIGURATION.md) | Advanced settings |
| [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md) | Common issues |
| [examples/](examples/) | Usage examples |

---

## 🧪 Testing

```bash
# Run automated tests
./scripts/test.sh

# Test specific functionality
python3 tests/test-skill.py
```

---

## 🔧 Development

### Building from Source

```bash
git clone https://github.com/YOUR_USERNAME/deepseek-brain-skill.git
cd deepseek-brain-skill
pip install -r requirements.txt
./scripts/install.sh --dev
```

### Running Tests

```bash
pytest tests/
./scripts/test.sh
```

### Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

## 🙋 Support

### Common Issues

**Skill not loading:**
```bash
# Reset and reinstall
./scripts/uninstall.sh
./scripts/install.sh
```

**API errors:**
```bash
# Check your API key
curl -H "Authorization: Bearer $DEEPSEEK_API_KEY" \
  https://api.deepseek.com/v1/models
```

**Commands timing out:**
```bash
# Increase timeout
export DEEPSEEK_TIMEOUT=300
```

### Getting Help

- 📖 Read the [documentation](docs/)
- 🐛 Open an [issue](https://github.com/YOUR_USERNAME/deepseek-brain-skill/issues)
- 💬 Start a [discussion](https://github.com/YOUR_USERNAME/deepseek-brain-skill/discussions)

---

## 🚀 SaaS Potential

This skill is designed to be productized:

### Tier 1: Free
- Basic skill installation
- Community support
- Standard examples

### Tier 2: Pro ($9/mo)
- Priority support
- Advanced examples
- Custom triggers
- Analytics dashboard

### Tier 3: Enterprise ($49/mo)
- Custom integrations
- SLA support
- Team management
- Audit logs
- Private models

### Monetization Features

```bash
# Premium features (example)
deepseek-pro "advanced task"  # Faster responses
deepseek-team "collaborate"   # Team features
deepseek-enterprise "scale"   # Enterprise features
```

---

## 📈 Roadmap

- [ ] Multi-model support (Claude, GPT-4, etc.)
- [ ] Conversation history sync across sessions
- [ ] Web UI for monitoring
- [ ] Plugin system for extensions
- [ ] Team collaboration features
- [ ] Analytics and usage tracking
- [ ] Custom command templates
- [ ] Integration with other AI tools

---

## 🎉 Acknowledgments

- [Qwen Code](https://github.com/QwenLM/qwen-code) - The execution layer
- [DeepSeek](https://deepseek.com) - The reasoning brain
- Community contributors and testers

---

**Built with ❤️ by YOUR_NAME**

```bash
# Ready to start?
curl -fsSL https://raw.githubusercontent.com/YOUR_USERNAME/deepseek-brain-skill/main/scripts/install.sh | bash
```
