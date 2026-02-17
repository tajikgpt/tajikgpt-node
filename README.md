# TajikGPT Node.js SDK

Official JavaScript/TypeScript SDK for the [TajikGPT API](https://tajikgpt.com) — Multilingual AI Platform by SoulLab.

## Installation

```bash
npm install tajikgpt
```

## Quick Start

```javascript
const { TajikGPT } = require("tajikgpt");

const client = new TajikGPT({ apiKey: "sk-tj-your-key" });

async function main() {
  const response = await client.chat.completions.create({
    model: "tj-1.0",
    messages: [{ role: "user", content: "Hello!" }],
  });
  console.log(response.choices[0].message.content);
}

main();
```

## TypeScript

```typescript
import { TajikGPT } from "tajikgpt";

const client = new TajikGPT({ apiKey: "sk-tj-your-key" });

const response = await client.chat.completions.create({
  model: "tj-1.0",
  messages: [{ role: "user", content: "Привет!" }],
  temperature: 0.7,
  max_tokens: 4096,
});

console.log(response.choices[0].message.content);
```

## Image Generation

```javascript
const image = await client.images.generate({
  model: "tj-image-1.0",
  prompt: "A sunset over mountains",
});

console.log(image.data[0].url);
```

## List Models

```javascript
const models = await client.models.list();
models.data.forEach((m) => console.log(m.id));
```

## Available Models

| Model | Description |
|-------|-------------|
| `tj-1.0-mini` | Fast & lightweight |
| `tj-1.0` | Balanced quality & speed |
| `tj-1.0-pro` | Advanced reasoning + Vision |
| `tj-1.0-ultra` | Maximum performance |
| `tj-coder` | Code specialist |
| `tj-image-1.0` | HD image generation |
| `tj-image-0.5` | Fast image generation |

## Configuration

```javascript
const client = new TajikGPT({
  apiKey: "sk-tj-your-key",
  baseURL: "https://tajikgpt.com/api", // default
  timeout: 120000, // ms, default 120s
});
```

## Links

- [TajikGPT Platform](https://tajikgpt.com)
- [API Documentation](https://tajikgpt.com/docs)
- [Python SDK](https://pypi.org/project/tajikgpt/)
- [Hugging Face](https://huggingface.co/TajikGPT-Team)

## License

MIT
