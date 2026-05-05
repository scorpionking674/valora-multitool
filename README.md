# Valora-Multitool

An AI-powered desktop application for generating, cleaning, and auditing image captions for Stable Diffusion, LoRA, FLUX, and other image training datasets.

Valora-Multitool supports local LLM servers such as LM Studio and Ollama-compatible endpoints, plus cloud providers including Moonshot, OpenAI, xAI, Anthropic, and Google Gemini.

> This repository distributes the portable Windows build only. No source code is published here.

## Table of Contents

- [What Is This?](#what-is-this)
- [Key Features](#key-features)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [The Four Tabs](#the-four-tabs)
- [Settings](#settings)
- [Logging and Debugging](#logging-and-debugging)
- [Architecture](#architecture)
- [Supported LLM Providers](#supported-llm-providers)
- [Tips for Best Results](#tips-for-best-results)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## What Is This?

Valora-Multitool automates the repetitive process of writing captions for image datasets used in AI image generation workflows.

Typical workflow:

1. Drag and drop images.
2. Select an AI model.
3. Generate captions.
4. Run an audit pass.
5. Export the dataset.

This removes the need to manually write hundreds of caption files.

## Key Features

### AI-Powered Captioning

- Batch caption generation
- Vision-capable LLM support
- Adjustable concurrency from 1 to 8 jobs
- Auto-retry on failures
- Real-time progress and ETA

### Two-Pass Audit System

- Factual verification to reduce hallucinations
- Full quality and formatting audit
- Per-image review UI
- One-click fixes

### Prompt Generator

- Generate prompts from ideas
- RAG-based guide integration
- SFW / NSFW toggle
- Multiple generation styles

### Prompt Cleaner

Remove unwanted tags and formatting, including:

- Appearance tags
- Quality tokens
- NSFW markers
- Token weights
- Negations

Additional cleaner features:

- Batch processing support
- Natural sentence flow preservation

### File Management

- Drag and drop import
- Auto-save `.txt` captions
- Export ZIP datasets
- Persistent logs per session

### Privacy Mode

- Instantly blur all images
- Useful in public or shared work environments

### Multi-Provider Support

- Local and cloud LLM support
- Separate vision and text model selection

## System Requirements

| Component | Requirement |
| --- | --- |
| OS | Windows 10/11 |
| RAM | 8 GB minimum, 16 GB recommended |
| GPU | Optional, required for local GPU models |
| Disk | Approximately 20 MB |
| Internet | Required for cloud LLM providers |

## Installation

1. Download `Valora-Multitool_0.1.0_x64-portable.exe` from `release-files/`.
2. Run the executable. No installation is required.
3. Optional: create a shortcut.

Windows SmartScreen may warn on first launch. Choose **More Info**, then **Run Anyway**.

## Getting Started

### Step 1: Configure an LLM

#### Option A: Local

1. Install LM Studio or another OpenAI-compatible local server.
2. Download a vision-capable model.
3. Start the local server.
4. Set the base URL to:

```text
http://localhost:1234/v1
```

5. Refresh models.

#### Option B: Cloud

1. Open **Settings > LLM Providers**.
2. Select a provider.
3. Paste your API key.
4. Refresh models.

### Step 2: Load Guides

| Folder | Purpose |
| --- | --- |
| `master/` | Global rules |
| `model_guide/` | Model-specific rules |
| `Critical_Rules/` | Custom enforcement |
| `Prompt_Guides/` | Prompt generator guides |

### Step 3: Add Images

- Drag and drop a folder, or
- Use **Add Files** / **Add Folder**.

### Step 4: Generate Captions

1. Select images.
2. Choose a vision model.
3. Click **Generate**.

### Step 5: Audit Captions

Recommended after generation:

1. Run **Check Facts** or **Full Audit**.
2. Review results.
3. Apply fixes where needed.

### Step 6: Export

Use **Export ZIP** to export images and caption files together.

## The Four Tabs

### Captioner

- Image grid
- Editable captions
- Status tracking

Toolbar actions:

| Action | Description |
| --- | --- |
| Generate | Batch captioning |
| Stop | Cancel current run |
| Audit | Run checks |
| Export | Save ZIP |

### Prompt Generator

Turn ideas into prompts:

1. Select a guide.
2. Enter an idea.
3. Generate.

### Prompt Cleaner

1. Paste prompts.
2. Select filters.
3. Clean.

### Settings

Configure providers, API keys, local endpoints, token limits, general behavior, and visual preferences.

## Settings

### LLM Providers

| Setting | Description |
| --- | --- |
| Provider | Local or cloud provider |
| Base URL | Local endpoint |
| API Keys | Cloud provider access |
| Token Limits | Model output controls |

### General

| Setting | Description |
| --- | --- |
| Trigger Word | Caption prefix |
| Concurrency | Parallel jobs |
| Strategy | Prompt style |
| Base Model | SDXL, FLUX, or custom target |

## Logging and Debugging

Logs are stored at:

```text
%LOCALAPPDATA%\com.valora.multitool\logs\
```

Logs include:

- Session logs
- Per-job logs
- Folder-level logs

## Architecture

```text
Frontend: SvelteKit
  - Caption UI
  - Audit UI
  - Prompt tools

Backend: Rust + Tauri
  - File I/O
  - Logging
  - ZIP export

LLM Layer
  - Local APIs
  - Cloud APIs
```

## Supported LLM Providers

| Provider | Vision | Notes |
| --- | --- | --- |
| LM Studio | Yes | Private, GPU recommended |
| Ollama-compatible endpoints | Depends on model | Local workflow |
| OpenAI | Yes | GPT-4o recommended |
| Moonshot | Yes | Strong multilingual support |
| xAI | Yes | Fast reasoning models |
| Anthropic | Yes | Strong rule-following |
| Gemini | Yes | Strong vision models |

## Tips for Best Results

- Use a strong master guide.
- Always select a vision-capable model.
- Lower concurrency if your GPU is weak.
- Run audits after generation.
- Check logs when errors occur.

## Troubleshooting

| Issue | Fix |
| --- | --- |
| No vision model | Select a vision-capable model |
| Cannot fetch models | Check API key or local base URL |
| Empty captions | Increase token limits |
| App does not load | Re-download the portable executable |

## License

MIT - free to use, modify, and distribute.
