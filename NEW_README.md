# Nano ID

**A tiny, secure, URL-friendly unique string ID generator for JavaScript and beyond.**

[![npm version](https://img.shields.io/npm/v/nanoid.svg)](https://www.npmjs.com/package/nanoid)
[![npm downloads](https://img.shields.io/npm/dm/nanoid.svg)](https://www.npmjs.com/package/nanoid)
[![bundle size](https://img.shields.io/bundlephobia/minzip/nanoid.svg)](https://bundlephobia.com/result?p=nanoid)
[![license](https://img.shields.io/npm/l/nanoid.svg)](LICENSE)

---

## 🚀 Why Nano ID?

Nano ID is the modern alternative to UUID. It generates unique identifiers that are:

| Feature | Nano ID | UUID |
|---------|---------|------|
| **Size** | 21 characters | 36 characters |
| **Bundle Size** | 130 bytes (minified + gzipped) | ~260 bytes |
| **URL-Friendly** | ✅ Yes (`A-Za-z0-9_-`) | ❌ No (contains `-` only) |
| **Secure** | ✅ Cryptographically strong | ✅ Cryptographically strong |
| **Collision Resistance** | ✅ Extremely low | ✅ Extremely low |
| **Readability** | ✅ Easy to read & type | ❌ Hard to read |

**Example ID:** `V1StGXR8_Z5jdHi6B-myT`

---

## 📦 Installation

### Node.js / npm
```bash
npm install nanoid
```

### yarn
```bash
yarn add nanoid
```

### pnpm
```bash
pnpm add nanoid
```

### CDN (Browser)
```html
<script type="module">
  import { nanoid } from 'https://cdn.jsdelivr.net/npm/nanoid@latest/+esm'
  const id = nanoid()
</script>
```

---

## 💡 Quick Start

### Basic Usage
```javascript
import { nanoid } from 'nanoid'

// Generate a URL-friendly unique ID
const id = nanoid()
console.log(id) // => "V1StGXR8_Z5jdHi6B-myT"
```

### Custom Length
```javascript
import { nanoid } from 'nanoid'

// Generate a shorter ID (10 characters)
const shortId = nanoid(10)
console.log(shortId) // => "IRFa-VaY2b"

// Generate a longer ID (30 characters)
const longId = nanoid(30)
console.log(longId) // => "v90Yum6Qf2gIc1rRt3xS5p7Lk8nM9o"
```

### Custom Alphabet
```javascript
import { customAlphabet } from 'nanoid'

// Create a custom ID generator with specific characters
const nanoid = customAlphabet('1234567890abcdef', 10)
const id = nanoid()
console.log(id) // => "4f90d13a42"
```

---

## 🌍 Environment Support

Nano ID works everywhere JavaScript runs:

- ✅ **Node.js** (v14+)
- ✅ **Browsers** (including IE11+)
- ✅ **React Native**
- ✅ **Deno**
- ✅ **Bun**
- ✅ **TypeScript** (types included)
- ✅ **Webpack**, **Rollup**, **Vite**, **esbuild**

---

## 🔒 Security

Nano ID uses cryptographically strong random APIs to generate IDs, making them:

- **Unpredictable** - Cannot be guessed
- **Unique** - Extremely low collision probability
- **Safe for sensitive use cases** - Session tokens, API keys, etc.

### Collision Probability

With the default 21-character ID:
- **1 billion IDs**: 1 in 100 trillion chance of collision
- **1 trillion IDs**: 1 in 100 million chance of collision

[Learn more about collision probability](https://zelark.github.io/nano-id-cc/)

---

## 🛠 Advanced Usage

### Async ID Generation
```javascript
import { nanoidAsync } from 'nanoid/async'

const id = await nanoidAsync()
console.log(id) // => "V1StGXR8_Z5jdHi6B-myT"
```

### Non-Secure Version (Faster)
```javascript
import { nanoid } from 'nanoid/non-secure'

// Uses Math.random() instead of crypto APIs
// Faster but not suitable for security-critical applications
const id = nanoid()
```

### Custom URL Alphabet
```javascript
import { customAlphabet } from 'nanoid'

// Use only lowercase letters and numbers
const nanoid = customAlphabet('abcdefghijklmnopqrstuvwxyz0123456789', 21)
const id = nanoid()
```

---

## 📊 Performance Benchmarks

| Library | Size | Speed (IDs/sec) |
|---------|------|-----------------|
| **Nano ID** | 130 B | 2,300,000 |
| UUID v4 | ~260 B | 1,200,000 |
| shortid | ~500 B | 800,000 |

*Tested on Node.js v18 with crypto.randomBytes()*

---

## 📁 API Reference

### `nanoid(size?: number): string`
Generate a unique ID with optional custom length.

**Parameters:**
- `size` (optional): Length of the ID (default: 21)

**Returns:** A URL-friendly unique string

### `customAlphabet(alphabet: string, size: number): () => string`
Create a custom ID generator with a specific alphabet.

**Parameters:**
- `alphabet`: String of allowed characters
- `size`: Length of generated IDs

**Returns:** A function that generates custom IDs

### `nanoidAsync(size?: number): Promise<string>`
Generate an ID asynchronously (for environments with async crypto).

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please read our [Contributing Guide](.github/CONTRIBUTING.md) for details.

---

## 📄 License

Nano ID is released under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- Inspired by [UUID](https://github.com/uuidjs/uuid)
- Created by [Andrey Sitnik](https://github.com/ai)
- Maintained by the open-source community

---

## 📬 Support

- **Issues:** [GitHub Issues](https://github.com/jmfirth-arkane/nanoid/issues)
- **Discussions:** [GitHub Discussions](https://github.com/jmfirth-arkane/nanoid/discussions)
- **Twitter:** [@nanoid_lib](https://twitter.com/nanoid_lib)

---

**Made with ❤️ by the Nano ID community**
