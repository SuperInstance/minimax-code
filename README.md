<div align="center">

<img src="https://filecdn.minimax.chat/public/c3ebbd2e-f55b-48d7-adff-030abb63e06d.png" alt="MiniMax Code" width="100%" />

# MiniMax Code — SuperInstance Fork

**Remembers your habits, builds Agent teams, automates the repetitive work.**

> **🏷️ SuperInstance Fork** — This is the [SuperInstance](https://github.com/SuperInstance) fork of [MiniMax Code](https://github.com/MiniMax-AI/MiniMax-Code), reconfigured with **z.ai GLM-5.1** as the primary code generation backend and **DeepInfra** as fallback. See [SUPERINSTANCE_CHANGES.md](./SUPERINSTANCE_CHANGES.md) for details.

[简体中文](./README.zh-CN.md)

</div>

---

## 🧬 SuperInstance Provider Configuration

This fork replaces MiniMax's default providers with our own stack:

| Role | Provider | Model | Best For |
|------|----------|-------|----------|
| **Primary** | z.ai | GLM-5.1 | All code tasks |
| **Fallback** | DeepInfra | seed-2.0-mini | Quick completions |
| **Fallback** | DeepInfra | gemma-4 | General generation |
| **Fallback** | DeepInfra | nemotron-120b | Complex algorithms |
| **Fallback** | DeepInfra | qwen-3.6 | Multilingual code |
| **Fallback** | DeepInfra | hermes-405b | Large refactoring |

### Setup

```bash
# Set your API keys
export SIA_ZAI_API_KEY=your-zai-key
export SIA_DEEPINFRA_API_KEY=your-deepinfra-key

# Provider config is in config/superinstance-providers.json
# Load it in your MiniMax Code configuration
```

See [SUPERINSTANCE_CHANGES.md](./SUPERINSTANCE_CHANGES.md) for the full changelog and [config/superinstance-providers.json](./config/superinstance-providers.json) for the provider configuration.

---

## Report an Issue

This repository collects issue reports for the SuperInstance fork of MiniMax Code.

> For bug reports, please include: version, platform, steps to reproduce, and expected vs actual behavior.

### How to submit

1. Tap **Issues** → **New issue** at the top right
2. Pick a template (Bug / Feature / Question)
3. Fill in the requested details:
   - **Version** — found in Settings
   - **Platform** — macOS / Windows
   - **Steps to reproduce** — short and reproducible
   - **Expected behavior** — what should happen
   - **Actual behavior** — what actually happens

### Before you submit

- Search to see if the issue already exists
- Make sure you are on the latest version
- Strip out any sensitive information (API keys, tokens, etc.)

---

<div align="center">

© 2026 MiniMax. SuperInstance modifications © 2026 SuperInstance. All rights reserved.

</div>
