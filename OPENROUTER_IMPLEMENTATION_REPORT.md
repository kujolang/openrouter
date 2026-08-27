# OpenRouter Implementation Report

## Executive Summary

Initial Kujo OpenRouter package using the provider's OpenAI-compatible chat protocol while preserving OpenRouter routing and model-catalog semantics.

## Official API Evidence / Evidence Date

OpenRouter's official SDK and API documentation describe `OPENROUTER_API_KEY`, `/api/v1/chat/completions`, `/api/v1/models`, SSE streaming, provider routing preferences, structured outputs, and model-dependent parameters. Evidence date: 2026-08-27.

## Protocol Classification

OPENAI-COMPATIBLE WITH PROVIDER EXTENSIONS.

## Architecture / Native API Coverage

Native client: `src/openrouter.kujo`; AI SDK adapter: `src/provider.kujo`; root exports: `openrouter.kujo`. Chat, model listing, SSE parsing, routing/provider preferences, usage, and native response preservation are covered.

## Public Exports

`create_client`, `chat`, `client_chat`, `client_models`, `parse_stream`, `openrouter_provider`, `openrouter_driver`.

## Kujo Requirement / AI SDK Dependency

Kujo >= 1.0.2; `github:kujolang/ai-sdk@v1.1.0`.

## Authentication / Native Semantics / Streaming

Bearer `OPENROUTER_API_KEY`, optional protected `HTTP-Referer` and `X-Title`, HTTPS enforcement, URL credential rejection, redaction, and OpenAI-compatible SSE parsing. Routing remains in the native request body.

## Tools / Structured Output / Reasoning / Multimodal / Embeddings

Provider-supported options are preserved in native requests. Model-dependent capabilities are not fabricated in normalized metadata. Embeddings and non-chat tasks are outside this initial package.

## Usage / Finish Reasons / Errors

Prompt/completion/total usage maps where supplied; native error payloads and provider codes are retained subject to redaction.

## AI SDK Driver / Security / Tests

Pure descriptor/decoder hooks with no network I/O or policy bypass. Two deterministic offline files plus installed consumer smoke are included.

## Clean-Room Install / Installed Consumer Smoke

Passed with Kujo v1.0.2, including immutable Kennel add/install/reinstall/validate and installed consumer smoke with `KUJO_MODULE_PATH` unset.

## Live Validation

SKIPPED — credentials/environment unavailable.

## AI SDK Changes / Kujo Changes / Kennel Changes

None.

## Contract Conformance / Limitations

See `OPENROUTER_PROVIDER_PACKAGE_CONFORMANCE.md`. File uploads, credits, analytics, OAuth, and agent orchestration are outside this initial package.
