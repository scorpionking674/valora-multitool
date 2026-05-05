Valora-Multitool

An AI-powered desktop application for generating, cleaning, and auditing image captions for Stable Diffusion / LoRA training datasets.

Supports both local LLMs (LM Studio, Ollama) and cloud providers (Moonshot, OpenAI, xAI, Anthropic, Google Gemini).

📚 Table of Contents
What is this?
Key Features
System Requirements
Installation
Getting Started
The Four Tabs
Settings
Logging & Debugging
Architecture
Supported LLM Providers
Tips for Best Results
Troubleshooting
License
❓ What is this?

Valora-Multitool automates the tedious process of writing captions for image datasets used in AI image generation (Stable Diffusion, LoRA, FLUX, etc.).

Workflow
1. Drag & drop images
2. Select AI model
3. Generate captions
4. Run audit pass
5. Export dataset

No more manually writing hundreds of captions.

✨ Key Features
🔮 AI-Powered Captioning
Batch caption generation
Vision-capable LLM support
Adjustable concurrency (1–8)
Auto-retry on failures
Real-time progress + ETA
🧪 Two-Pass Audit System
Factual verification (anti-hallucination)
Full quality + formatting audit
Per-image review UI
One-click fixes
🛠️ Prompt Generator
Generate prompts from ideas
RAG-based guide integration
SFW / NSFW toggle
Multiple generation styles
🧹 Prompt Cleaner
Remove unwanted tags:
Appearance
Quality tokens
NSFW markers
Token weights
Negations
Batch processing support
Maintains natural sentence flow
📁 File Management
Drag & drop import
Auto-save .txt captions
Export ZIP datasets
Persistent logs per session
🔒 Privacy Mode
Blur all images instantly
Ideal for public environments
🔌 Multi-Provider Support
Local + cloud LLMs
Separate vision/text model selection
🖥️ System Requirements
Component	Requirement
OS	Windows 10/11
RAM	8GB minimum (16GB recommended)
GPU	Optional (needed for local models)
Disk	~20MB
Internet	Required for cloud LLMs
📦 Installation
1. Download valora-multitool.exe
2. Run (no install required)
3. Optional: create shortcut

⚠️ Windows SmartScreen: Click More Info → Run Anyway

🚀 Getting Started
Step 1: Configure LLM
Option A — Local
1. Install LM Studio
2. Download vision model
3. Start server (localhost:1234)
4. Set Base URL: http://localhost:1234/v1
5. Refresh models
Option B — Cloud
1. Open Settings → LLM Providers
2. Select provider
3. Paste API key
4. Refresh models
Step 2: Load Guides
Folder	Purpose
master/	Global rules
model_guide/	Model-specific rules
Critical_Rules/	Custom enforcement
Prompt_Guides/	Prompt generator guides
Step 3: Add Images
Drag & drop folder
OR use Add Files / Add Folder
Step 4: Generate Captions
1. Select images
2. Choose vision model
3. Click Generate
Step 5: Audit (Recommended)
1. Run Check Facts or Full Audit
2. Review results
3. Apply fixes
Step 6: Export
Export ZIP → images + captions
🧩 The Four Tabs
🖼️ Captioner
Image grid
Editable captions
Status tracking

Toolbar Actions

Action	Description
Generate	Batch captioning
Stop	Cancel run
Audit	Run checks
Export	Save ZIP
✍️ Prompt Generator

Turn ideas into prompts:

1. Select guide
2. Enter idea
3. Generate
🧹 Prompt Cleaner
1. Paste prompts
2. Select filters
3. Clean
⚙️ Settings
LLM Providers
Setting	Description
Provider	Local / Cloud
Base URL	Local endpoint
API Keys	Cloud access
Token Limits	Model control
General
Setting	Description
Trigger Word	Caption prefix
Concurrency	Parallel jobs
Strategy	Prompt style
Base Model	SDXL / FLUX
🧾 Logging & Debugging
Logs Location
%LOCALAPPDATA%\com.valora.multitool\logs\
Includes
Session logs
Per-job logs
Folder-level logs
🏗️ Architecture
Frontend (SvelteKit)
 ├── Caption UI
 ├── Audit UI
 ├── Prompt Tools

Backend (Rust + Tauri)
 ├── File I/O
 ├── Logging
 ├── ZIP export

LLM Layer
 ├── Local APIs
 └── Cloud APIs
🤖 Supported LLM Providers
Provider	Vision	Notes
LM Studio	✅	Private, GPU needed
OpenAI	✅	GPT-4o recommended
Moonshot	✅	Strong multilingual
xAI	✅	Fast reasoning
Anthropic	✅	Rule-following
Gemini	✅	Strong vision
💡 Tips for Best Results
Use a strong Master Guide
Always pick a vision model
Lower concurrency if GPU is weak
Run audits after generation
Check logs when errors occur
🛠️ Troubleshooting
Issue	Fix
No vision model	Select one
Can't fetch models	Check API/URL
Empty captions	Increase tokens
App not loading	Rebuild project
📄 License

MIT — free to use, modify, and distribute.
