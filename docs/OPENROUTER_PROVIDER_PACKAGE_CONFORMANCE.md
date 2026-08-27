# OpenRouter Provider Package Contract v1 Conformance

Evidence date: 2026-08-27. Contract: v1.0.1.

| Area | Result | Evidence |
|---|---|---|
| Native and compatible driver layers | PASS | `src/openrouter.kujo`, `src/provider.kujo` |
| Auth, endpoint, redaction | PASS | `tests/native_tests.kujo` |
| Deterministic tests | PASS | release gate |
| Immutable AI SDK dependency | PASS | Kennel pins `v1.1.0` |
| Streaming/routing | PASS | SSE parser and provider routing request tests |
| Clean-room distribution | PASS | Kujo v1.0.2 add/install/reinstall/validate and installed consumer smoke passed |
| Remote release | PASS | `kujolang/openrouter` tag `v0.1.0` and commit verified |
