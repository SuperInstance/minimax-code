# SuperInstance Changes — MiniMax Code Fork

> This document tracks all modifications made to the [MiniMax Code](https://github.com/MiniMax-AI/MiniMax-Code) upstream by [SuperInstance](https://github.com/SuperInstance).

---

## Fork Purpose

SuperInstance extends MiniMax Code — an AI-powered code generation tool — by replacing default providers with **z.ai GLM-5.1** as the primary code generation backend and **DeepInfra** as the fallback provider.

## Changes

### 1. Provider Replacement

**Primary Provider:** z.ai GLM-5.1
- Used as the default code generation backend
- Optimized for code completion, generation, and refactoring tasks

**Fallback Provider:** DeepInfra with model roster:
- `deepinfra/seed-2.0-mini` — Quick fixes and completions
- `deepinfra/gemma-4` — General code generation
- `deepinfra/nemotron-120b` — Complex algorithmic reasoning
- `deepinfra/qwen-3.6` — Multilingual code generation
- `deepinfra/hermes-405b` — Large-scale refactoring

**Removed from defaults:**
- MiniMax default provider (replaced with z.ai)
- No OpenAI dependency in our defaults

### 2. Configuration

Added `config/superinstance-providers.json` with the full model roster configuration that can be loaded by MiniMax Code or compatible tools.

### 3. Documentation

- Added this `SUPERINSTANCE_CHANGES.md`
- Updated `README.md` with fork notice and SuperInstance provider details
- Added provider configuration documentation

### 4. Issue Templates

Updated GitHub issue templates to reflect SuperInstance as the maintainer.

## Model Roster

| Role | Provider | Model | Best For |
|------|----------|-------|----------|
| **Primary** | z.ai | GLM-5.1 | All code tasks |
| **Fallback 1** | DeepInfra | seed-2.0-mini | Quick completions |
| **Fallback 2** | DeepInfra | gemma-4 | General generation |
| **Fallback 3** | DeepInfra | nemotron-120b | Complex algorithms |
| **Fallback 4** | DeepInfra | qwen-3.6 | Multilingual code |
| **Fallback 5** | DeepInfra | hermes-405b | Large refactoring |

## Usage

### Configuration File

```json
{
  "providers": {
    "primary": {
      "name": "zai",
      "base_url": "https://api.zai.chat/v1",
      "model": "glm-5.1",
      "api_key_env": "SIA_ZAI_API_KEY"
    },
    "fallback": {
      "name": "deepinfra",
      "base_url": "https://api.deepinfra.com/v1/openai",
      "models": [
        "deepinfra/seed-2.0-mini",
        "deepinfra/gemma-4",
        "deepinfra/nemotron-120b",
        "deepinfra/qwen-3.6",
        "deepinfra/hermes-405b"
      ],
      "api_key_env": "SIA_DEEPINFRA_API_KEY",
      "strategy": "ordered",
      "max_retries": 5
    }
  }
}
```

### Environment Variables

```bash
SIA_ZAI_API_KEY=your-zai-api-key
SIA_DEEPINFRA_API_KEY=your-deepinfra-api-key
SIA_DEFAULT_PROVIDER=zai
SIA_DEFAULT_MODEL=glm-5.1
```

## Upstream Sync

```bash
git remote add upstream https://github.com/MiniMax-AI/MiniMax-Code.git
git fetch upstream
git rebase upstream/main
```

## License

This fork maintains the same license as the upstream MiniMax Code project. SuperInstance-specific additions are MIT licensed.
