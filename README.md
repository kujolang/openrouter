# Kujo OpenRouter Provider

Native OpenRouter OpenAI-compatible chat client with provider routing metadata and an AI SDK adapter.

```bash
kujo package-add github:kujolang/openrouter@v0.1.0
export OPENROUTER_API_KEY=your-key
```

```kujo
from openrouter import create_client, client_chat
c := create_client({})
r := client_chat(c, {"model":"openai/gpt-5.5","messages":[{"role":"user","content":"Hello"}],"provider":{"sort":"price"}})
```

Native use preserves routing, provider preferences, model catalog, usage/cost metadata, and OpenRouter response fields. `openrouter_provider()` supplies normalized AI SDK chat and streaming semantics. Tests are offline and credential-free.
