# 🏛️ ArtifactX — Museum Engine V1.0

> **Point. Scan. Discover.** Bringing ancient artifacts to life through AI.

ArtifactX is an AI-powered museum artifact recognition web app built for **Tradition Hacks 2026**. Visitors simply photograph any museum artifact and instantly receive detailed historical information, cultural context, and fascinating facts — narrated aloud in both **English and Bengali**.

---

## ✨ Features

- 📸 **Instant Artifact Recognition** — photograph any artifact and get results in seconds
- 🏺 **Deep Historical Context** — period, origin, cultural significance, and detailed history
- 💡 **Did You Know Facts** — 2 to 4 curated fascinating facts per artifact
- 🔊 **Bilingual Audio Narration** — full text-to-speech in English and Bengali
- 📱 **Mobile First Design** — works entirely in the browser, no app install needed
- ♿ **Accessible & Inclusive** — breaking language barriers for regional visitors

---

## 🖼️ Demo

🔗 **Live App:** [comforting-biscuit-f6ba8e.netlify.app](https://comforting-biscuit-f6ba8e.netlify.app)

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| AI Vision | Multimodal Large Language Model API |
| Text-to-Speech | Web Speech API (built-in browser) |
| Hosting | Netlify (static deployment) |
| Camera Access | Browser MediaDevices API |

---

## 🚀 How It Works

```
User photographs artifact
        ↓
Image converted to Base64
        ↓
Sent to AI vision model with detailed museum prompt
        ↓
Returns: name, period, origin, history, facts (JSON)
        ↓
Displayed with bilingual audio narration
```

---

## 📁 Project Structure

```
ArtifactX/
├── index.html       # Complete single-file web application
└── README.md        # Project documentation
```

---

## 🏃 Running Locally

No setup needed. Just open `index.html` in any modern browser:

```bash
# Clone the repo
git clone https://github.com/SoumalyaSaha/ArtifactX.git

# Open in browser
open index.html
```

---

## 📸 Scan Tips for Best Results

- Fill **at least 70%** of the frame with the artifact
- Use **ambient light** — avoid flash on shiny surfaces
- Keep the shot **close, steady and in focus**

---

## 🎯 Problem We're Solving

Museums across India house thousands of priceless artifacts, yet most visitors walk past them with little understanding of their historical significance. Traditional museum guides are expensive, unavailable in regional languages, and cannot scale to serve every visitor.

ArtifactX makes heritage education **accessible, engaging, and inclusive for everyone** — turning any smartphone into an intelligent artifact guide.

---

## 👨‍💻 Built At

**Tradition Hacks 2026** — Heritage & Culture Track

---

## 📄 License

MIT License — free to use and build upon.

