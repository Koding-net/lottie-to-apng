# @kodeking/lottie-to-apng

> Convert Lottie JSON animations to **animated PNG (APNG)** — Node.js CLI + programmatic API

[![npm](https://img.shields.io/npm/v/@kodeking/lottie-to-apng)](https://www.npmjs.com/package/@kodeking/lottie-to-apng)
[![license](https://img.shields.io/npm/l/@kodeking/lottie-to-apng)](LICENSE)

Lossless, full RGBA transparency, infinite loop. APNG is natively supported by all modern browsers and renders identically to PNG on platforms that don't support animation. Try it live at [iconking.net/tools/lottie-to-apng](https://iconking.net/tools/lottie-to-apng).

---

## Prerequisites

| Tool | Required | Install |
|---|---|---|
| Node.js ≥ 18 | ✅ | — |
| ffmpeg | ✅ | `brew install ffmpeg` / [ffmpeg.org](https://ffmpeg.org/download.html) |

---

## Install

```bash
npm install -g @kodeking/lottie-to-apng
npx @kodeking/lottie-to-apng input.json output.png
```

---

## CLI

```bash
lottie-to-apng input.json output.png [--fps 24] [--width 480]
```

---

## Programmatic API

```js
const { convertToApng } = require('@kodeking/lottie-to-apng');

await convertToApng({
  input:  'animation.json',
  output: 'animation.png',
  fps:    24,
  width:  480,
});
```

### Options

| Option | Type | Default | Description |
|---|---|---|---|
| `input` | `string` | required | Path to Lottie JSON |
| `output` | `string` | required | Path for output APNG (.png) |
| `fps` | `number` | `24` | Frame rate |
| `width` | `number` | `480` | Width in px |
| `height` | `number` | same as width | Height in px |

---

## Notes

- Output uses `‑plays 0` (infinite loop).
- APNG is lossless — file sizes are larger than WebP/GIF for the same quality. Use for designs where pixel-perfect fidelity matters.
- Falls back gracefully to a static PNG on browsers/platforms that don't support APNG.

---

## License

MIT © [KodeKing](https://github.com/kodeking)

See all tools at [github.com/kodeking/lottie-tools](https://github.com/kodeking/lottie-tools).
