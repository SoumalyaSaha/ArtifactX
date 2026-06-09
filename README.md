# ArtifactX — Museum Engine V1.0

### Your personal museum guide, in any language.

[![Track](https://img.shields.io/badge/Track-Smart%20Tourism%20%26%20Heritage%20Technology-orange)](https://tiny-begonia-1ca245.netlify.app/)
[![Status](https://img.shields.io/badge/Status-Live-brightgreen)](https://tiny-begonia-1ca245.netlify.app/)
[![Built For](https://img.shields.io/badge/Built%20For-Tradition%20Hacks%202026-gold)](https://unstop.com)
[![No Install](https://img.shields.io/badge/No%20Install-Works%20in%20Browser-blue)](https://tiny-begonia-1ca245.netlify.app/)

---

## 🔗 Live Demo

**👉 [https://tiny-begonia-1ca245.netlify.app/](https://tiny-begonia-1ca245.netlify.app/)**

> Open on your phone, point at any museum artifact, and tap scan. No install required.

---

## 📌 Problem Statement

Museums are among the most important repositories of human history and culture — yet they remain inaccessible to a large portion of visitors.

- International tourists and non-native speakers struggle to engage with exhibits due to **language barriers**
- Traditional audio guides are **expensive, limited in language support**, and require separate hardware
- QR-code systems create **friction** and depend on museum infrastructure
- As a result, the cultural significance of thousands of artifacts goes **unexplored every day**

The Indian Museum, Kolkata — founded in 1814 and the largest museum in Asia-Pacific — houses over 60 galleries and 100,000+ artifacts, yet most visitors leave without truly understanding what they saw.

---

## 💡 What is ArtifactX?

ArtifactX is a **zero-install, mobile-first web app** that lets museum visitors instantly learn about any artifact by simply photographing it. Using AI-powered visual recognition, the app identifies the artifact and delivers its full history, origins, cultural significance, and fun facts — spoken aloud in the visitor's native language.

No QR codes. No downloads. No setup. Just point and scan.

---

## ✨ Key Features

- 📷 **Visual Artifact Scanning** — photograph any artifact using your phone camera
- 🧠 **AI-Powered Identification** — powered by Museum Engine V1.0
- 🌐 **Multilingual Output** — history delivered in 13+ languages including Bengali, Hindi, Tamil, Arabic, Mandarin, Japanese, and more
- 🔊 **Text-to-Speech Narration** — hear the artifact's story read aloud in your language
- 🏛️ **Deep Museum Knowledge** — trained on all 9 sections of the Indian Museum: Archaeology, Numismatics & Coins, Art, Anthropology, Geology, Zoology, Egyptian Antiquities, Economic Botany, and Inscriptions & Manuscripts
- ✅ **Artifact Validation** — rejects non-artifact images with a friendly message
- ⚡ **Zero Setup** — pure HTML/JS, works instantly in any mobile browser

---

## 🏗️ Architecture & Flow

```
┌─────────────────────────────────────────────────────────────┐
│                     USER'S PHONE                            │
│                                                             │
│   📱 Open browser → tiny-begonia-1ca245.netlify.app         │
│              │                                              │
│              ▼                                              │
│   📷 Camera / Gallery → Capture Artifact Image              │
│              │                                              │
│              ▼                                              │
│   🖼️  Image compressed & encoded to Base64 (≤1024px JPEG)   │
└──────────────────────┬──────────────────────────────────────┘
                       │  HTTPS POST
                       ▼
┌─────────────────────────────────────────────────────────────┐
│              MUSEUM ENGINE V1.0 — AI VISION CORE            │
│                                                             │
│   Input:  Museum Knowledge Base + Visual Input        │
│                                                             │
│   Step 1: VALIDATE — is this a real artifact?               │
│              │                                              │
│      ┌───────┴────────┐                                     │
│      ▼                ▼                                     │
│   ❌ Not artifact   ✅ Is artifact                           │
│   → Reject msg      → Identify                              │
│                        │                                    │
│                        ▼                                    │
│   Step 2: IDENTIFY — name, period, origin, category         │
│                        │                                    │
│                        ▼                                    │
│   Step 3: GENERATE — history (EN + native), fun facts       │
│                                                             │
│   Output: Structured JSON response                          │
└──────────────────────┬──────────────────────────────────────┘
                       │  JSON
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                  BACK ON DEVICE                             │
│                                                             │
│   📋 Parse JSON → Render Result Card                        │
│              │                                              │
│              ▼                                              │
│   🔊 Text-to-Speech → Speak history in selected language    │
│              │                                              │
│              ▼                                              │
│   👤 User reads / listens to artifact story                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | Vanilla HTML5, CSS3, JavaScript (ES6+) |
| **AI Vision** | Museum Engine V1.0 (Proprietary AI Vision) |
| **Text-to-Speech** | Web Speech API (device-native) + gTTS fallback |
| **Fonts** | Cinzel, Crimson Pro, JetBrains Mono (Google Fonts) |
| **Icons** | Tabler Icons |
| **Hosting** | Netlify (static deploy) |
| **Camera** | `getUserMedia` API + `capture="environment"` fallback |



---

## 🏛️ Museum Knowledge Base

ArtifactX is specifically trained on the **Indian Museum, Kolkata** (founded 1814) across all 9 sections:

| # | Section | Key Artifacts |
|---|---|---|
| 1 | Archaeology | Bharhut Stupa, Gandhara sculptures, Didarganj Yakshi |
| 2 | Numismatics & Coins | 50,000+ coins — Gupta gold, Kushana, Mughal |
| 3 | Art | Mughal miniatures, Kalighat paintings, Chola bronzes |
| 4 | Anthropology | Tribal objects, Andaman & Nicobar artifacts |
| 5 | Geology | Dinosaur bones, meteorites, Gondwana fossils |
| 6 | Zoology | Blue whale skeleton, taxidermy, bird collections |
| 7 | Egyptian Antiquities | 4,000-year-old mummy, canopic jars, papyrus |
| 8 | Economic Botany | Herbarium specimens, medicinal plants |
| 9 | Inscriptions & Manuscripts | Sanskrit, Prakrit, Arabic, Persian, Bengali |

---

## 🌐 Supported Languages

Bengali · Hindi · Tamil · Telugu · Marathi · Urdu · Arabic · French · Spanish · Mandarin Chinese · Japanese · German · Portuguese · Russian

---

## 🚀 Installation

**No installation required.**

ArtifactX is a pure static web app. Just open the link in any browser:

👉 **[https://tiny-begonia-1ca245.netlify.app/](https://tiny-begonia-1ca245.netlify.app/)**

### Run Locally

If you want to run it on your own machine:

```bash
# Clone the repo
git clone https://github.com/SoumalyaSaha/ArtifactX.git

# Navigate into the folder
cd ArtifactX

# Just open index.html in your browser
open index.html
# or on Windows:
start index.html
```

> No npm install. No build step. No configuration needed — works out of the box.

---

## 👥 Team

**Team Name:** ArtifactX
**Track:** Smart Tourism & Heritage Technology
**Event:** Tradition Hacks 2026

---

*Built with ❤️ for Tradition Hacks 2026 — celebrating the cultural heritage of Kolkata and India.*
