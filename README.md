# David C. Cavalcante

I build the infrastructure that production AI agents run on.

Zero-dependency, spec-driven TypeScript libraries for the agent stack —
routing, observability, runtime tuning, prompt-cache economics, key
resilience — plus a fine-tuned model on Hugging Face and a governed-agent
framework with cryptographic audit trails. 25 years across software, design,
and marketing; the last five in hands-on LLM systems R&D. Based in Tarragona,
Spain. I work in English, Spanish, and Portuguese.

**Open to AI / ML / LLM Engineer roles** — remote (EU/global) or relocation.
Reach me: [davcavalcante@proton.me](mailto:davcavalcante@proton.me) ·
[LinkedIn](https://linkedin.com/in/hellodav) ·
[Hugging Face](https://huggingface.co/TeleologyHI) ·
[npm](https://www.npmjs.com/~davcavalcante)

---

## Start here

If you have ten minutes, read **[modelchain](https://github.com/davccavalcante/modelchain)**.
It normalizes three providers' native streaming formats — OpenAI SSE,
Anthropic `content_block_delta`, Gemini `streamGenerateContent` — into one
typed `AsyncIterable`, translates tool-calling shapes in both directions, and
routes across models by cost, latency, and measured quality, under hard USD
budget ceilings. The core is 5.6 KB gzipped. The compatibility matrix is the
hard part; the 182 tests include golden and live suites against real provider
responses.

If you have one minute, run:

```bash
npx @takk/racs simulate   # deterministic, seeded — same output every run
```

## The @takk suite — production agent infrastructure

[![modelchain](https://img.shields.io/npm/v/%40takk%2Fmodelchain?label=%40takk%2Fmodelchain)](https://www.npmjs.com/package/@takk/modelchain)
[![behavioralai](https://img.shields.io/npm/v/%40takk%2Fbehavioralai?label=%40takk%2Fbehavioralai)](https://www.npmjs.com/package/@takk/behavioralai)
[![noeticos](https://img.shields.io/npm/v/%40takk%2Fnoeticos?label=%40takk%2Fnoeticos)](https://www.npmjs.com/package/@takk/noeticos)
[![racs](https://img.shields.io/npm/v/%40takk%2Fracs?label=%40takk%2Fracs)](https://www.npmjs.com/package/@takk/racs)
[![keymesh](https://img.shields.io/npm/v/%40takk%2Fkeymesh?label=%40takk%2Fkeymesh)](https://www.npmjs.com/package/@takk/keymesh)

| Library | One job, done precisely |
|---|---|
| **[modelchain](https://github.com/davccavalcante/modelchain)** | LLM router: normalized streaming + tool calling across OpenAI/Anthropic/Gemini, 7 routing strategies, budget ceilings, per-model circuit breakers. Node, edge, and browser entry points; Vercel AI SDK adapter |
| **[behavioralai](https://github.com/davccavalcante/behavioralai)** | Behavioral drift detection for agents: a synchronous, I/O-free `observe()` learns per-agent fingerprints (Welford/EWMA), attributes drift to features, forecasts trends, and alerts on 13 channels built on bare `fetch`/WebCrypto — including a from-scratch SMTP client and RS256 JWT signing. Ingests OpenTelemetry GenAI spans |
| **[noeticos](https://github.com/davccavalcante/noeticos)** | Bandit-based runtime tuning: discounted UCB1, Welch exact tails, Bonferroni alpha spending, Wilson floors — implemented from scratch. Exploration confined to a deterministic canary cohort; every decision lands in an append-only audit log |
| **[racs](https://github.com/davccavalcante/racs)** | Prompt prefix-cache planning: the real cache semantics of 16 provider profiles, break-even math so it never emits an unprofitable cache write, nine cache-killer lint rules. Zero credentials, zero network — the worst failure mode is a suboptimal plan |
| **[keymesh](https://github.com/davccavalcante/keymesh)** | API-key pool resilience: rotation strategies, per-key circuit breakers honoring `Retry-After`, full-jitter backoff, 401 quarantine. A deep Proxy mirrors the wrapped SDK, so client code doesn't change |

One discipline across all five: **zero runtime dependencies, strict
TypeScript, dual ESM+CJS with full type definitions, a SPEC.md in every repo,
~870 tests combined, CI on every push, SLSA provenance on every release.**

## Models

**[him-distilled-3b](https://huggingface.co/TeleologyHI/him-distilled-3b)** —
a LoRA fine-tune of Qwen-2.5-3B (6.18 GB), built with an MLflow-instrumented
distillation pipeline and an eval runner as the release gate. Dataset
curation, training, experiment tracking, evaluation, and public release —
end to end.

## Governed agents — TeleologyHI

**[TeleologyHI](https://github.com/davccavalcante/TeleologyHI)** is my
research monorepo (TypeScript, 7 workspaces, 749 tests), published to npm as
`@teleologyhi-sdk`. Three layers:

- **MAIC** — governance: Ed25519-signed axiom administration (pinned signing
  key, nonce replay protection), a seven-tier severity-ranked verdict
  pipeline, tamper-evident SHA-256-chained audit logs
- **HIM** — identity: deterministic persona projection (stable 256-dim
  embedding, byte-level determinism unit-tested) so an agent keeps its
  character across LLM model swaps
- **NHE** — runtime: a six-step supervised response pipeline, seven streaming
  LLM adapters (Anthropic, Gemini, Mistral, DeepSeek, xAI Grok, Ollama, Mock)
  behind one contract, and a built-in MCP stdio server for Claude
  Desktop/Code and Cursor

Release engineering to match: two-step human-gated releases, a rollback
workflow, Dependabot, provenance publishing.

## A language for agent skills — .ah

**[.ah (Teleological Semantic Format)](https://github.com/davccavalcante/supreme-coding-guidelines-skill.ah)**
is a declarative DSL for LLM prompts and agent skills: a formal spec with a
full EBNF grammar and checksum validation, a Python linter (`ah-lint`), and
eight coding-agent skills packaged as a Claude Code plugin with rule mirrors
for Cursor, Zed, Kiro, and Trae.

## Retrieval, from primitives

I think you understand a system better when you build it without the
framework: **[iUrbanCicerone](https://github.com/davccavalcante/iUrbanCicerone)**
is RAG with a hand-rolled BM25 fused with embedding cosine similarity and
source-cited answers — no LangChain, no vector DB.
**[TheArchivistLens](https://github.com/davccavalcante/TheArchivistLens)**
implements the Reinert method of Descending Hierarchical Classification from
scikit-learn/scipy primitives, applied to a real ten-book literary corpus.

## Writing

Essays on AI ethics and the philosophy of technology, self-archived at
[PhilPapers](https://philpapers.org/s/David%20C%C3%B4rtes%20Cavalcante)
(2024–2025), and trilingual technical writing on
[Medium](https://davidccavalcante.medium.com). The philosophical questions —
what agents are, what we owe them, what they owe us — are where the
engineering above started.

---

Founder of [Takk Innovate Studio](https://takk.ag) — a one-person studio that
has run on a team of AI agents since 2022. Everything on this page is
verifiable in public code; if you check one claim, check them all.
