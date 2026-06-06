# Luna AI Platform - AI-Powered Content & Companion Platform

Next-generation AI platform combining chat, image generation, video creation, and voice synthesis — all running on local GPU infrastructure.

![Python](https://img.shields.io/badge/Backend-Python_FastAPI-blue)
![Next.js](https://img.shields.io/badge/Frontend-Next.js-black)
![GPU](https://img.shields.io/badge/GPU-RTX_5090-green)
![License](https://img.shields.io/badge/License-Proprietary-red)

## Vision

A self-hosted AI platform where every AI model runs locally — zero API costs, full privacy, unlimited generation. Built for scale on a GPU farm.

## Features

### AI Chat
- Local LLM integration (Ollama — Qwen, Gemma, LLaMA)
- Character personalities with persistent memory
- Multi-language support
- VISUAL_PROMPT system — LLM generates image prompts inline during conversation

### AI Image Generation
- **SDXL/DreamShaper** — photorealistic portraits and scenes
- **ComfyUI pipeline** — automated workflow execution via API
- Smart routing: SFW → cloud fast model, NSFW → local SDXL
- IP-Adapter for consistent character faces
- FaceDetailer for automatic face fixing
- 30+ costume/scene presets

### AI Video Generation
- **Wan 2.1 I2V** — image-to-video, 480x832 vertical format
- **LTX-Video** — text-to-video
- **AnimateDiff** — animation from static images
- Lightx2v LoRA for 4-step fast generation
- FaceFusion face swap integration

### AI Voice
- XTTS v2 — voice cloning from 30-sec reference
- Multi-language TTS
- Per-character unique voices

### Platform
- JWT authentication
- Token-based economy (photo=5, video=20 tokens)
- Character management system
- Real-time WebSocket chat
- Mobile-responsive UI

## Architecture

```
┌──────────────────────────────────────────────────┐
│                    Frontend                       │
│              Next.js + Tailwind                   │
│         Chat UI / Gallery / Profile               │
└────────────────────┬─────────────────────────────┘
                     │ REST + WebSocket
┌────────────────────▼─────────────────────────────┐
│                   Backend                         │
│              FastAPI + SQLite                     │
│                                                   │
│  ┌──────────┐ ┌──────────┐ ┌──────────────────┐  │
│  │ Chat API │ │ Auth/JWT │ │  Token Economy   │  │
│  └────┬─────┘ └──────────┘ └──────────────────┘  │
│       │                                           │
│  ┌────▼─────────────────────────────────────────┐ │
│  │           AI Generation Router               │ │
│  │                                               │ │
│  │  ┌─────────┐ ┌──────────┐ ┌──────────────┐  │ │
│  │  │ Ollama  │ │ ComfyUI  │ │ XTTS Voice   │  │ │
│  │  │ LLM Chat│ │ SDXL/Wan │ │ Clone        │  │ │
│  │  └─────────┘ └──────────┘ └──────────────┘  │ │
│  └───────────────────────────────────────────────┘ │
└──────────────────────────────────────────────────┘
                     │
              ┌──────▼──────┐
              │  GPU Farm   │
              │  RTX 5090   │
              │  32GB VRAM  │
              └─────────────┘
```

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Frontend | Next.js 14, TypeScript, Tailwind, shadcn/ui |
| Backend | Python FastAPI, SQLAlchemy, SQLite |
| LLM | Ollama (Qwen3, Gemma4, LLaMA) |
| Image Gen | ComfyUI, SDXL, DreamShaper, IP-Adapter |
| Video Gen | Wan 2.1 I2V, LTX-Video, AnimateDiff |
| Voice | XTTS v2, Edge-TTS |
| Face | FaceFusion, FaceDetailer, DWPose |
| GPU | NVIDIA RTX 5090 32GB |

## Performance

| Task | Speed | Hardware |
|------|-------|---------|
| SDXL image (832x1216) | ~6 sec | RTX 5090 |
| Wan 2.1 video (81 frames) | ~3 min | RTX 5090 |
| LLM response (26B) | 143 tok/s | RTX 5090 |
| Voice clone (30 sec) | ~5 sec | RTX 5090 |

## Monetization Model

- **Subscription tiers:** Free / Basic / Pro
- **Token economy:** Purchase tokens for premium content
- **API access:** For developers and integrators
- **White-label:** License the platform for other creators

## Investment Opportunity

Luna AI Platform is seeking **$100K** to scale from a single-server MVP to a production GPU farm.

**Current state:**
- Working MVP with chat, image gen, video gen, voice clone
- Proven tech stack on RTX 5090 (32GB VRAM)
- All AI runs locally — zero API costs at scale
- Live avatar technology: LLM + voice + lip sync + face animation

**What $100K buys:**

| Item | Cost |
|------|------|
| 10x RTX 5090 GPUs | $25,000 |
| 10 server builds (CPU, 64GB RAM, 2TB NVMe) | $35,000 |
| Network infrastructure (10G switch, cabling) | $3,000 |
| Server rack + cooling system | $5,000 |
| Power (PDU, UPS, electrical) | $5,000 |
| Colocation hosting (1 year) | $12,000 |
| CDN, domain, SSL, infrastructure | $3,000 |
| Reserve fund (replacements, contingency) | $12,000 |
| **Total** | **$100,000** |

**What it delivers:**

| Metric | Capacity |
|--------|----------|
| Live AI avatars (hybrid mode) | 50 simultaneous |
| Live AI avatars (full realtime) | 5 simultaneous |
| AI image generation | 18,000/day |
| AI video generation | 400/day |
| LLM chat sessions | 20 concurrent |
| Paying subscribers | 200-400 |

**Revenue projection:**
- Subscription: $10-50/month per user
- 200-400 subscribers = **$2,000-20,000/month**
- **Payback period: 5-12 months**

**Competitive advantage:**
- Zero API costs (everything local = 95%+ gross margin)
- Full data privacy (no cloud dependency)
- Unlimited generation (no per-request charges)
- Scalable: add more GPUs = more users linearly

**Contact:** Available for live demo and technical deep-dive.

## Screenshots

*Screenshots available upon request — contact for a live demo.*

## Status

🟡 **MVP Complete** — Seeking investment for production scaling.

## License

Proprietary. Source code available under NDA for potential investors/partners.
