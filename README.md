# Kujo OpenRouter Provider

[![Version](https://img.shields.io/badge/version-0.1.2-black)](https://github.com/kujolang/openrouter/releases/tag/v0.1.2)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)
[![built with Kujo](https://img.shields.io/badge/built%20with-Kujo-white.svg)](https://github.com/kujolang/kujo)

OpenRouter routing and model-catalog support for Kujo, using its OpenAI-compatible inference API.

## Install

```bash
kujo run /path/to/kennel/kennel.kujo \
  --interpreter \
  -- add github:kujolang/openrouter@v0.1.2 \
  --alias openrouter
kujo run /path/to/kennel/kennel.kujo --interpreter -- install
export OPENROUTER_API_KEY=your-key
```

## 30-second quick start

```kujo
from openrouter import create_client, client_chat

client := create_client({})
request := {
    "model": "openai/gpt-5.5",
    "messages": [
        {
            "role": "user",
            "content": "Hello from Kujo!"
        }
    ]
}

result := client_chat(client, request)

print(result["data"]["choices"][0]["message"]["content"])
```

## Native API

The native client preserves model discovery, provider routing and preferences, fallbacks, privacy controls, usage/cost metadata, and OpenRouter response fields.

## AI SDK integration

`openrouter_provider({"model": "openai/gpt-5.5"})` supplies normalized chat and streaming semantics through the reusable compatible driver. Existing AI SDK compatibility remains intact.

## Authentication and security

Set `OPENROUTER_API_KEY`. Remote endpoints require HTTPS; credentials are redacted and never included in provider metadata or fixtures.

## Testing and documentation

```bash
bash scripts/release_quality_gate.sh
bash scripts/verify_installed_package.sh
```

The default gate is deterministic and offline. See [docs/](docs/) for implementation and Contract v1 evidence.
