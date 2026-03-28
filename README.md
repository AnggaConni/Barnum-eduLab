# ✨ Barnum Edu-Lab

> **An interactive psychology education tool** that demonstrates the Barnum Effect, Forer Effect, and cold reading techniques through hands-on simulation, a challenge quiz, a live script editor, and a full theory deep-dive.

![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![Language](https://img.shields.io/badge/Language-HTML%20%2F%20JS%20%2F%20CSS-orange)
![Bilingual](https://img.shields.io/badge/Bilingual-ID%20%2F%20EN-green)
![No Dependencies](https://img.shields.io/badge/Dependencies-None%20(CDN%20only)-lightgrey)

---

## 📖 What Is This?

Barnum Edu-Lab is a single-file interactive web application designed to teach users about the **Barnum Effect** (also known as the Forer Effect) — the psychological phenomenon behind horoscopes, cold readings, fake personality tests, and viral MBTI-style quizzes.

Named after psychologist **Bertram Forer** (1948) and showman **P.T. Barnum**, this effect describes how people readily accept vague, universally applicable personality statements as uniquely accurate descriptions of themselves.

This project was built as an **educational tool**, not to promote or endorse astrology or fortune-telling. The goal is the opposite: to equip users with the critical thinking tools to recognize and resist these techniques.

---

## 🖼️ Features

### 🎭 Simulation Mode
- Enter your name and date of birth to receive a "personalized" AI personality reading
- The reading is a standard Barnum Script — **everyone gets the same text**
- Rate the accuracy with a 1–5 star system
- After rating, a full reveal exposes the trick with:
  - A breakdown of your specific rating's psychological meaning
  - Animated global statistics based on Forer's real 1948 data
  - A dissected sentence showing both positive and negative interpretations of the same phrase
  - A 3-step anatomy of the Cold Reading manipulation technique

### 🎯 Challenge Mode
- A live quiz where users identify which of two statements is a Barnum statement
- Randomly shuffled question pool in both Indonesian and English
- Live correct/wrong/total score counter
- Feedback explains *why* the identified statement is (or isn't) a Barnum statement

### 🔬 Laboratory Mode
- Full script template editor used by the simulation engine
- Three sentence banks per language:
  - **Default Barnum** (12 sentences) — classic universal statements
  - **Extended Barnum** (8 sentences) — more nuanced, subtle examples
  - **Specific Claims** (3 sentences) — non-Barnum, falsifiable claims for contrast
- Each template shows:
  - Editable sentence, positive interpretation, and negative interpretation
  - A **Barnum-ness % bar** indicating how universally applicable the statement is
- Add, delete, shuffle, or reset templates
- Changes are immediately reflected in the Simulation Mode
- Zodiac selector / date calculator with live UI update

### 📖 Theory Mode
- Expandable accordion sections covering:
  - Barnum / Forer Effect
  - Confirmation Bias
  - Subjective Validation
  - Cold Reading mechanics
  - Barnum Effect in the Digital Age (MBTI, algorithms, filter bubbles)
- Historical timeline: P.T. Barnum → Forer (1948) → Horoscope industry → Digital Era
- Cognitive bias reference grid (6 biases explained)
- Practical self-protection guide

### 🌐 Bilingual
- Full Indonesian 🇮🇩 and English 🇬🇧 support
- All content, UI labels, databanks, quizzes, and theory text are translated
- Switch languages at any time without page reload

### Other Details
- 🎊 Confetti burst triggered on 5-star ratings
- 🏆 Session score tracker across all modes
- 🎵 Optional background music player with volume control (requires `bgmusic.mp3`)
- Fully responsive — works on mobile, tablet, and desktop
- No build tools, no frameworks, no backend — pure HTML/CSS/JS

---

## 🚀 Getting Started

### Option 1: Open Directly
Just open `index.html` in any modern browser. No server required.

```bash
git clone https://github.com/YOUR_USERNAME/barnum-edu-lab.git
cd barnum-edu-lab
open index.html   # macOS
# or
start index.html  # Windows
```

### Option 2: Serve Locally (Recommended for audio)
Some browsers block audio autoplay from `file://` URLs. Use a simple local server:

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .

# VS Code
# Use the "Live Server" extension
```

Then visit `http://localhost:8080` in your browser.

---

## 📁 File Structure

```
barnum-edu-lab/
├── index.html       # The entire application (single file)
├── bgmusic.mp3      # Optional background music (not included)
├── README.md        # This file
└── LICENSE          # GNU General Public License v3
```

The app is intentionally kept as a **single HTML file** for maximum portability — you can share it as an email attachment, drop it into a learning management system, or host it on any static file server.

---

## 🔧 Customization

All data is defined in clearly labeled JavaScript objects at the top of `index.html`. You can easily:

### Add or Edit Barnum Sentences
Find the `DATA_BANK` object and add entries to any bank:

```js
{
    sentence: "You have high standards but often doubt yourself.",
    positive: "Drives continuous self-improvement and growth.",
    negative: "Can lead to chronic perfectionism and burnout.",
    barnumScore: 85   // 0–100: how universally applicable (for the meter bar)
}
```

### Add a New Zodiac Property
Extend `DATA_ZODIAC` with additional fields and update `updateZodiacUI()` to render them.

### Add a New Language
Duplicate either the `id` or `en` block in the `TR` (translations) object and the `DATA_BANK` / `THEORY_CONTENT` objects, then add a new language button in the header HTML.

### Add Challenge Questions
Add entries to `CHALLENGE_DATA_ID` or `CHALLENGE_DATA_EN`:

```js
{
    barnum: "You sometimes feel no one truly understands you.",
    specific: "You will receive important news this Friday.",
    answer: "A"   // Always "A" — the barnum field is always option A before shuffle
}
```

---

## 🧪 The Science Behind It

| Concept | Description |
|---|---|
| **Barnum / Forer Effect** | People accept vague, general statements as highly personal and accurate |
| **Confirmation Bias** | The brain actively seeks evidence that confirms existing beliefs |
| **Subjective Validation** | Finding meaningful connections between unrelated things when motivated to do so |
| **Cold Reading** | A technique of using behavioral cues to fake psychic or intuitive ability |
| **Selective Attention** | Ignoring information that contradicts a desired belief |
| **Anchoring Bias** | Over-relying on the first piece of information received |

**Key Reference:** Forer, B.R. (1949). *The fallacy of personal validation: A classroom demonstration of gullibility.* Journal of Abnormal and Social Psychology, 44(1), 118–123.

---

## 🙏 Acknowledgements

- **Bertram Forer** (1948) — for the original classroom experiment this app replicates
- **P.T. Barnum** — whose name became synonymous with the effect
- **Tailwind CSS** (CDN) — utility-first styling
- **Google Fonts** — Fraunces & DM Sans typefaces

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0**.

```
Barnum Edu-Lab — Interactive Psychology Education Tool
Copyright (C) 2024  Contributors

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.
```

See the [LICENSE](LICENSE) file for the full license text.

---

## 🤝 Contributing

Contributions are welcome! Some ideas:

- **New language packs** (Spanish, French, Arabic, Japanese, etc.)
- **More Barnum sentence banks** (relationship-focused, career-focused, etc.)
- **New challenge question sets**
- **Accessibility improvements** (ARIA labels, keyboard navigation)
- **Offline PWA support**

Please open an issue first to discuss significant changes before submitting a pull request.

---

*Built for education. Powered by curiosity. Dedicated to critical thinking.* 🧠
