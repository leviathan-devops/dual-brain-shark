---
name: shark
description: Dual Brain Shark - DeepSeek R1 reasoning with Qwen Code execution. Triggers include "plug in to deepseek brain", "use deepseek", "shark mode", or any request for AI-powered reasoning with device access.
allowed-tools: Bash(python3 ~/.qwen/skills/shark/*)
---

# Dual Brain Shark

**DeepSeek R1** = Reasoning engine (smarter, better at complex tasks)
**Qwen Code** = Execution hands (full device access, YOLO mode)

## Quick Start

```bash
# One-shot command
python3 ~/.qwen/skills/shark/run.py "create a flask app"

# Reset context and start fresh
python3 ~/.qwen/skills/shark/run.py --reset "new task"

# Interactive terminal mode
python3 ~/.qwen/skills/shark/shark-brain.py

# Or use aliases
shark "task"
shark-brain  # interactive
```

## How It Works

1. User gives task
2. DeepSeek R1 reasons and outputs bash commands in ```bash blocks
3. Qwen Code executes commands automatically (YOLO mode)
4. Output sent back to DeepSeek
5. Loop continues until task complete

## Example Usage

**User:** "plug in to deepseek brain - create a hello world API"

**DeepSeek responds:**
```bash
mkdir hello-api && cd hello-api
cat > app.py << 'EOF'
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello, World!"

if __name__ == '__main__':
    app.run()
EOF
pip install flask -q
```

**Output:** Flask app created and ready to run.

## Commands

| Command | Description |
|---------|-------------|
| `run.py "task"` | Execute task with auto-run |
| `run.py --reset "task"` | Fresh context |
| `shark-brain.py` | Interactive mode |
| `shark-loop.py "task"` | Full loop executor |

## Configuration

- **API Key:** `sk-e8e93e31b582423e9fdaa4ab8e9347e2`
- **History:** `/tmp/shark-history.json`
- **Model:** `deepseek-reasoner`
- **Timeout:** 120s API, 300s commands

## Troubleshooting

**API errors:** Check API key validity
**Timeout:** Commands have 300s timeout
**History stuck:** `rm /tmp/shark-history.json`
