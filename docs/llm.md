# Qwen Auth plugin quick setup

## Install

```bash
# Using Bun (recommended)
bun add opencode-qwen-auth

# Using npm
npm install opencode-qwen-auth
```

Add to `opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "plugin": ["opencode-qwen-auth"],
  "provider": {
    "qwen": {
      "npm": "@ai-sdk/openai",
      "options": {
        "baseURL": "https://portal.qwen.ai/v1",
        "compatibility": "strict"
      },
      "models": {
        "coder-model": {
          "name": "Qwen Coder",
          "attachment": true,
          "limit": { "context": 131072, "output": 16384 }
        }
      }
    }
  }
}
```

## Authenticate

```bash
/auth
```

Select **Qwen OAuth** and follow the device login instructions.

## Choose a model

OAuth models:

- `coder-model`

OpenAI-compatible examples:

- `qwen-plus`
- `qwen3-max`
- `qwen-flash`
- `qwen-turbo`

## Optional overrides

Create `.opencode/qwen.json`:

```json
{
  "base_url": "https://portal.qwen.ai/v1",
  "rotation_strategy": "round-robin",
  "proactive_refresh": true,
  "refresh_window_seconds": 300
}
```
