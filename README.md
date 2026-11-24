# Pollinations Figma Plugin

[![Quest](https://img.shields.io/badge/Quest-%2315572%20(FIXED)-blue)](https://github.com/pollinations/pollinations/issues/15572)
[![Figma](https://img.shields.io/badge/Figma-Plug-in-000000)](https://figma.com)

Figma plugin that lets designers generate and edit images with
[Pollinations AI](https://pollinations.ai) directly inside their designs.

## About

This plugin connects Figma to the Pollinations image generation API.
Designers can fill frames with generated images, edit existing fills,
choose models and dimensions, and authenticate with a BYOP API key.

## Features

- Generate image — fills the selected frame or shape
- Edit image — regenerates the selected image fill
- Model selection — any image model from `gen.pollinations.ai`
- Dimension control — 512x512, 1024x1024, 1024x768, 768x1024
- BYOP support — enter your API key or use device flow

## Structure

```text
pollinations-figma/
├── manifest.json
├── code.js
├── ui.html
├── README.md
├── CHANGELOG.md
└── .github/workflows/ci-unified.yml
```

## Stack

- Figma Plugin API 1.0.0
- JavaScript (main context)
- HTML/CSS/JS (plugin UI)
- Pollinations image API

## Installation

### Manual install (development)

1. Download this repository
2. In Figma, open Menu, Plugins, Development, New Plugin
3. Choose Link existing plugin
4. Point to `pollinations-figma/manifest.json`

### Figma Community (coming soon)

Once approved, install from Menu, Plugins, Browse plugins in Community.

## Usage

### Generate an image

1. Select a frame, rectangle, star, or ellipse
2. Open the plugin: Menu, Plugins, Pollinations AI
3. Enter a prompt (e.g. "A cyberpunk city at night")
4. Choose a model and dimensions
5. Click Generate Image
6. The selected frame is filled with the generated image

### Edit an existing image

1. Select a node that has an image fill
2. Switch the action to Edit selected image
3. Enter a new prompt describing the desired edit
4. Click Generate Image
5. The selected node's fill is replaced

### BYOP (Bring Your Own Pollen)

1. Get an API key from enter.pollinations.ai/keys
2. Paste it into the plugin's API Key field
3. Key is saved to localStorage and used as `?key=` query param

## Demo

Demo recording — the plugin UI with:

1. Prompt: "A fantasy castle"
2. Model: gptimage, Dimensions: 1024x1024
3. Click "Generate Image"
4. Image appears in the selected frame within 2 seconds

## Files

| File | Description |
| --- | --- |
| `manifest.json` | Figma plugin manifest |
| `code.js` | Main plugin code (Figma API communication) |
| `ui.html` | Plugin UI with inline JavaScript |

## API Endpoints

| Feature | Endpoint |
| --- | --- |
| Image generation | `GET https://image.pollinations.ai/{prompt}` |
| Image editing | Same as generation |
| Model lists | `GET https://gen.pollinations.ai/image/models` |

## License

MIT

## Contributing

Contributions are welcome. Open an issue or pull request on GitHub.

## Quest

This plugin fulfills Quest #15572 — Pollinations plugin for Figma.
