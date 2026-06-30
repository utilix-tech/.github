<div align="center">

**The tool layer for developers and AI agents.**

[![Web App](https://img.shields.io/badge/utilix.tech-6d28d9?style=flat-square&logo=vercel&logoColor=white)](https://utilix.tech)
[![SDK](https://img.shields.io/npm/v/@utilix-tech/sdk?style=flat-square&label=SDK&color=22c55e)](https://www.npmjs.com/package/@utilix-tech/sdk)
[![Python](https://img.shields.io/pypi/v/utilix-sdk?style=flat-square&label=Python&color=3b82f6)](https://pypi.org/project/utilix-sdk/)
[![MCP](https://img.shields.io/npm/v/@utilix-tech/mcp?style=flat-square&label=MCP&color=a855f7)](https://www.npmjs.com/package/@utilix-tech/mcp)
[![License: MIT](https://img.shields.io/badge/license-MIT-gray?style=flat-square)](https://opensource.org/licenses/MIT)

</div>

---

100+ deterministic developer tools — JSON, encoding, hashing, text, color, CSS, regex, and a 28-tool AI agent toolkit for LLM pipelines. No LLM calls for the core tools. No side effects. Runs locally or over HTTP.

| Surface | Install | Auth |
|---------|---------|------|
| 🌐 **Browser** | [utilix.tech/tools](https://utilix.tech/tools) — instant, no install | — |
| 📦 **Node.js SDK** | `npm install @utilix-tech/sdk` | — |
| 🐍 **Python SDK** | `pip install utilix-sdk` | — |
| 🤖 **MCP Server** | `npx @utilix-tech/mcp` (Claude / Cursor / VS Code) | — |
| 🔗 **REST API** | `api.utilix.tech/v1/...` | API key |

---

## Quick Start

**Node.js**

```bash
npm install @utilix-tech/sdk
```

```typescript
import { formatJson } from '@utilix-tech/sdk/json'
import { estimateTokens, detectPii, chunkText } from '@utilix-tech/sdk/ai_agent'

const pretty   = formatJson('{"name":"Alice","age":30}')
const { tokens } = estimateTokens('Your document...')
const { findings } = detectPii('alice@example.com, SSN 123-45-6789')
const chunks   = chunkText(text, 256, 32)   // chunkSize=256, overlap=32
```

**Python**

```bash
pip install utilix-sdk
```

```python
from utilix.tools.ai_agent import estimate_tokens, detect_pii, chunk_text, rerank_chunks

est  = estimate_tokens("Your document...")
pii  = detect_pii("alice@example.com, call 555-123-4567")
chunks = chunk_text(text, chunk_size=256, overlap=32)
ranked = rerank_chunks("machine learning", [c["text"] for c in chunks])
```

**MCP — Claude Desktop / Cursor / VS Code**

```json
{
  "mcpServers": {
    "utilix": { "command": "npx", "args": ["-y", "@utilix-tech/mcp"] }
  }
}
```

*"Trim this to 4000 tokens"* · *"Detect PII in this text"* · *"Diff these two JSON configs"* · *"Rerank these chunks by my query"*

---

## Tool Categories

| Category | Tools |
|----------|-------|
| **AI Agent** | Token estimate & cost · Trim / chunk text · Compress HTML/MD/JSON · Summarize · Extract URLs/JSON/tables/entities · Rerank · PII detect/redact · Secret scan · Prompt injection detect |
| **JSON** | Format · Minify · Diff · Validate · JSONPath · CSV↔JSON · YAML↔JSON · TS types |
| **Encoding** | Base64 · URL · HTML entities · Base32 |
| **Hashing** | MD5 · SHA-1/256/512 · bcrypt · HMAC |
| **Text** | Case convert · Slugify · Word count · Line diff · HTML→Markdown |
| **Generators** | UUID · ULID · Passwords · QR codes · Mock data |
| **Time** | Unix timestamp · Cron parse · Date diff · Timezone convert |
| **Color** | Hex/RGB/HSL convert · Palette · Shades · WCAG contrast |
| **Code** | SQL/HTML/JS format · Regex tester · GraphQL · Docker · .env |
| **Data** | CSV · YAML · TOML · XML parse and convert |
| **CSS · Network · Units · Misc** | Gradient · HTTP codes · IP lookup · Byte convert · SVG optimize |

---

## Repositories

| | |
|-|-|
| [`utilix-sdk`](https://github.com/utilix-tech/utilix-sdk) | Node.js + Python SDK — examples and quickstarts |
| [`utilix-mcp`](https://github.com/utilix-tech/utilix-mcp) | MCP server config + 60+ example prompts |
| [`utilix-api`](https://github.com/utilix-tech/utilix-api) | REST API — examples in curl, Python, Node.js, Go |
| [`utilix-embed`](https://github.com/utilix-tech/utilix-embed) | Embed SDK — drop any tool into your own site |

---

<div align="center">

[utilix.tech](https://utilix.tech) · [Docs](https://utilix.tech/docs) · [npm](https://www.npmjs.com/package/@utilix-tech/sdk) · [PyPI](https://pypi.org/project/utilix-sdk/) · MIT

</div>
