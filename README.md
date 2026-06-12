# cocoon-llm-guard

A wrapper layer for LLM APIs that intercepts and flags age-inappropriate
generation attempts before they reach a child user.

## Status
RFC Stage — architecture input welcome

## How It Works
Sits between your application and any LLM provider (OpenAI, Anthropic, etc.).
Intercepts requests and responses, applies age-profile filters,
and blocks or sanitizes content that fails the check.

## Supported Providers (planned)
- OpenAI
- Anthropic
- Google Gemini
- Open-source models via Ollama

## Quick Start (draft)
```
pip install cocoon-llm-guard
from cocoon_llm_guard import GuardedClient
client = GuardedClient(provider="openai", profile="under-13")
```

## License
MIT
