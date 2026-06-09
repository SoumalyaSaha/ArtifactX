# ArtifactX — Museum Engine V1.0

### Your personal museum guide, in any language.

[![Track](https://img.shields.io/badge/Track-Smart%20Tourism%20%26%20Heritage%20Technology-orange)](https://tiny-begonia-1ca245.netlify.app/)
[![Status](https://img.shields.io/badge/Status-Live-brightgreen)](https://tiny-begonia-1ca245.netlify.app/)
[![Built For](https://img.shields.io/badge/Built%20For-Tradition%20Hacks%202026-gold)](https://unstop.com)
[![No Install](https://img.shields.io/badge/No%20Install-Works%20in%20Browser-blue)](https://tiny-begonia-1ca245.netlify.app/)
[![Accuracy](https://img.shields.io/badge/Accuracy-~100%25%20on%20clear%20images-brightgreen)](https://tiny-begonia-1ca245.netlify.app/)

---

## 🔗 Live Demo

**👉 [https://tiny-begonia-1ca245.netlify.app/](https://tiny-begonia-1ca245.netlify.app/)**

> Open on your phone, point at any museum artifact, and tap scan. No install required.

---

## 📸 Screenshots

> *Full screenshot gallery coming soon — demo results from real user testing*

| Scanning Interface | Result Card | Multilingual Output |
|---|---|---|
| *(coming soon)* | *(coming soon)* | *(coming soon)* |

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
- 🏛️ **Deep Museum Knowledge** — knowledge base curated across all 9 sections of the Indian Museum
- ✅ **Smart Artifact Validation** — rejects non-artifact images with a friendly message, preventing misuse
- 🔄 **Resilient Pipeline** — automatic retry logic and multi-key failover for uninterrupted scanning
- ⚡ **Zero Setup** — works instantly in any mobile browser, no app store required

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
│   🖼️  Image optimised & compressed (≤1024px JPEG)           │
└──────────────────────┬──────────────────────────────────────┘
                       │  HTTPS POST
                       ▼
┌─────────────────────────────────────────────────────────────┐
│              MUSEUM ENGINE V1.0 — AI VISION CORE            │
│                                                             │
│   Input:  Museum Knowledge Base + Visual Input              │
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
│   Output: Structured response                               │
└──────────────────────┬──────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                  BACK ON DEVICE                             │
│                                                             │
│   📋 Parse & Validate → Render Result Card                  │
│              │                                              │
│              ▼                                              │
│   🔊 Text-to-Speech → Speak history in selected language    │
│              │                                              │
│              ▼                                              │
│   👤 User reads / listens to artifact story                 │
└─────────────────────────────────────────────────────────────┘
```

---

## ⚙️ Technical Architecture

### Image Processing Pipeline
- Device camera captured via `getUserMedia` API with environment-facing preference
- Falls back to file picker on devices where camera access is restricted
- Image resized to ≤1024px and compressed to JPEG before transmission — balancing quality and speed
- Ensures high detail retention for fine artifacts like coins, engravings, and miniature paintings

### AI Vision & Identification Layer
- Custom **Museum Engine V1.0** processes both the visual input and the curated museum knowledge base simultaneously
- Two-stage pipeline: first **validates** whether the image is a genuine artifact, then **identifies** it
- Returns structured data: artifact name, historical period, origin, category, rich history, and fun facts
- Uncertainty is expressed honestly — outputs "Possibly" or "Likely" when confidence is partial, rather than forcing a wrong answer
- Handles all 9 museum sections including the previously underserved **Numismatics & Coins** category

### Resilience & Reliability
- **High-availability engine** — automatically switches to backup processing nodes during high-traffic periods, ensuring uninterrupted scanning
- **Automatic retry logic** — silently retries on transient failures before surfacing any error to the user
- **JSON validation & repair** — malformed responses are detected and retried rather than crashing the UI
- Graceful degradation at every layer — users always see a meaningful message, never a blank screen

### Multilingual Text-to-Speech
- Primary TTS via **Web Speech API** — device-native, zero latency, works offline
- Automatic fallback to **gTTS** for languages not supported natively by the device
- Language mapped to the user's selection — same history narrated in both English and native language
- Sentence-by-sentence chunking for natural, uninterrupted narration

### Frontend Engineering
- Pure **HTML5 / CSS3 / Vanilla JS** — no framework overhead, instant load on any device
- Custom gold and navy museum aesthetic built entirely in CSS variables
- Cinzel serif typography chosen to evoke museum gravitas
- Fully responsive — optimised for mobile, works on desktop

---

## 📊 Accuracy & Testing

ArtifactX was tested across **4 independent users** scanning various artifacts from the Indian Museum collection.

| Metric | Result |
|---|---|
| Recognition accuracy (clear images) | ~100% |
| Recognition accuracy (obscured/low-light) | Partial — expresses uncertainty |
| False positives (non-artifacts accepted) | 0 — validation layer rejects all modern objects |
| Languages tested | Bengali, Hindi, Mandarin Chinese, English |
| Artifact categories tested | Coins, Sculptures, Egyptian Antiquities, Relief Carvings |

> *"The app correctly identified every artifact we pointed it at. The only time it struggled was when the photo was blurry or taken in poor light — and even then it said 'Possibly' instead of guessing wrong."*
> — User tester feedback

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | Vanilla HTML5, CSS3, JavaScript (ES6+) |
| **AI Vision** | Museum Engine V1.0 (Custom AI Vision Layer) |
| **Text-to-Speech** | Web Speech API (device-native) + gTTS fallback |
| **Fonts** | Cinzel, Crimson Pro, JetBrains Mono (Google Fonts) |
| **Icons** | Tabler Icons |
| **Hosting** | Netlify (static deploy) |
| **Camera** | `getUserMedia` API + `capture="environment"` fallback |

---

## 🏛️ Museum Knowledge Base

ArtifactX knowledge base is curated across all 9 sections of the **Indian Museum, Kolkata** (founded 1814):

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

ArtifactX works instantly in any browser:

👉 **[https://tiny-begonia-1ca245.netlify.app/](https://tiny-begonia-1ca245.netlify.app/)**

### Run Locally

```bash
# Clone the repo
git clone https://github.com/SoumalyaSaha/ArtifactX.git

cd ArtifactX

# Open index.html in your browser
open index.html
# or on Windows:
start index.html
```

> No npm install. No build step. No configuration needed — works out of the box.

---

## 🔭 Future Roadmap

- [ ] Offline mode with pre-downloaded artifact database for museum zones with poor connectivity
- [ ] Expand knowledge base to other Indian museums — National Museum Delhi, Salar Jung Museum
- [ ] AR overlay — highlight artifact details directly on the camera feed
- [ ] Crowd-sourced artifact corrections and community contributions
- [ ] Museum partnership programme for official integration
- [ ] Accessibility features — high contrast mode, larger text, simplified language option

---

## 👥 Team

**Team Name:** ArtifactX
**Track:** Smart Tourism & Heritage Technology
**Event:** Tradition Hacks 2026

---

*Built with ❤️ for Tradition Hacks 2026 — celebrating the cultural heritage of Kolkata and India.*
