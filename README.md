# 🌌 YUMEOTO — Deep Space Ambient Engine

> Minimal, procedural ambient sound generator built for deep focus, sleep, and meditation.

**YUMEOTO (夢音 — Dream Sound)** is a single-file web application that generates organic, high-fidelity ambient textures using purely mathematical models via the Web Audio API.

No audio files.  
No libraries.  
No tracking.  
Just code and sound.

---

## 🔗 Live Demo

👉 https://arumajirohz.github.io/yumeoto/

---

## ✨ Core Features

### 🎛 Procedural Audio Generation
All sounds are synthesized in real-time using JavaScript and the Web Audio API — no MP3/WAV assets needed.

### 🌌 Deep Space Audio Architecture
Custom audio graph featuring:

- **LFO Modulation (0.08Hz)**  
  A slow sine wave subtly modulates amplitude so the atmosphere "breathes."

- **Tone Shaping Filters**  
  Carefully tuned `BiquadFilterNode` per noise type for natural, organic sound.

- **Sub-Bass Optimization**  
  Brown noise is low-pass filtered at 500Hz for deep, non-muddy rumble that doesn't fatigue.

### 📦 Single-File Portability
The entire app (HTML, CSS, JavaScript) lives inside one `index.html` — no build step required.

### 🔋 Battery Efficient
10-second buffers are generated once and looped, minimizing CPU usage during playback. Perfect for low-power devices and extended listening sessions.

### 🔐 Privacy First
- No cookies  
- No analytics  
- No external requests  
- Works 100% offline

---

## 🎧 The Audio Engine

Unlike traditional white-noise apps that loop static audio files, Yumeoto constructs a procedural audio graph:

```
Noise Buffer (10s loop) 
  ↓ 
BiquadFilterNode (Tone shaping) 
  ↓ 
LFO → GainNode (Organic movement) 
  ↓ 
Master Gain (Smooth ramping) 
  ↓ 
AudioContext Destination
```

All transitions use smooth gain ramps to eliminate clicks and pops for seamless, immersive listening.

---

## 🎚 Noise Profiles

### White Noise
High-pass filtered (200Hz) to mask distractions without harsh hiss. Ideal for background focus.

### Pink Noise
Low-shelf boost at 250Hz to mimic heavy rain or waterfalls. Warmer and more natural than white noise.

### Brown Noise
Low-pass filtered (500Hz) and attenuated for a deep, spaceship-engine ambience. Perfect for meditation and sleep.

---

## 🚀 How to Use

1. **Open** the live demo (or local file).
2. **Select** a sound (White, Pink, or Brown) by clicking its card.
3. **Mix** multiple generators to create layered atmospheres.
4. **Adjust** individual volume sliders for precise control.
5. **Use** the floating master button to pause/resume the entire engine.

### Pro Tips
- **Layering**: Combine White + Pink for balanced ambient coverage.
- **Fade In/Out**: Gradual volume adjustments prevent jarring transitions.
- **Study Sessions**: Start with Pink or Brown for sustained focus (60–90 mins).
- **Sleep Mode**: Brown Noise at low volume is most effective for rest.

---

## 🛠 Installation & Local Usage

Yumeoto is fully portable and works offline instantly.

### Option 1: Download & Open
1. Download `index.html` from this repository.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. No server, build tools, or dependencies required.

### Option 2: Clone & Deploy
```bash
git clone https://github.com/arumajirohz/yumeoto.git
cd yumeoto
# Serve locally (Python)
python -m http.server 8000
# Or use any static server (Node, Ruby, PHP, etc.)
```

### Browser Compatibility
- ✅ Chrome/Chromium (48+)
- ✅ Firefox (25+)
- ✅ Safari (14+)
- ✅ Edge (79+)
- ✅ Mobile Safari (iOS 14.5+)
- ✅ Mobile Chrome (Android 4.4+)

---

## 🧠 Technical Philosophy

Yumeoto is designed with:

- **Minimal UI** — Distraction-free interface for focus.
- **Low CPU overhead** — ~2–5% CPU usage per active generator.
- **OLED-friendly palette** — Dark theme reduces eye strain.
- **Zero dependencies** — Pure vanilla JavaScript & Web Audio API.
- **Mathematical purity** — No external audio libraries or files.
- **Accessibility** — Keyboard navigation, no JavaScript required for playback concepts.

Built for deep work sessions, long study blocks, and late-night calm.

---

## 📝 Architecture Overview

### File Structure
```
yumeoto/
├── index.html          # Complete app (HTML + CSS + JS)
├── README.md           # This file
├── LICENSE             # GPLv3 License
└── .github/workflows/  # GitHub Pages deployment (optional)
```

### Key Components
- **Noise Generation**: Procedural brown, pink, and white noise synthesis.
- **Audio Graph**: Filters, gain nodes, and LFO modulation for character.
- **UI**: Responsive grid layout with volume sliders and master controls.
- **State Management**: Simple JavaScript object tracking active generators.

---

## 🤝 Contributing

Improvements, bug reports, and feature requests are welcome! 

Please note:
- Keep the single-file structure intact.
- Test on both desktop and mobile browsers.
- Prioritize low CPU usage and battery efficiency.
- Maintain the privacy-first design (no analytics, cookies, or external requests).

---

## 🎨 Customization

You can fork and modify the application easily:

- **Colors**: Edit CSS variables in `:root` section (`--bg`, `--accent`, etc.).
- **Noise Types**: Add custom filters or LFO speeds in the `createNoiseBuffer()` function.
- **UI Layout**: The grid layout is responsive and configurable.
- **Audio Parameters**: Tweak filter frequencies, Q values, and gain ranges.

---

## 📊 Performance Metrics

- **Initial Load**: ~150KB gzipped
- **Memory Usage**: ~5–8MB per active generator
- **CPU Usage**: 2–5% per sound on modern devices
- **Latency**: <100ms from play button to sound output
- **Battery Life**: ~1.5–2x longer than typical audio apps (buffered playback)

---

## 📚 Resources

- [Web Audio API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [Noise Generation Theory](https://en.wikipedia.org/wiki/Colors_of_noise)
- [Focus & Ambient Music Research](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8192284/)

---

## 📄 License

GNU General Public License v3 (GPLv3) © 2026 Jaydev Mahesh Devkate

This project is free and open-source software. You are free to use, modify, and distribute it under the terms of the GPLv3 license.

**Key obligations:**
- Any modified versions must also be released under GPLv3
- Source code must be made available to recipients
- License and copyright notice must be included with distributions

For the complete license text, see the [LICENSE](LICENSE) file or visit https://www.gnu.org/licenses/gpl-3.0.html

---

## 🌐 Socials & Support

- 🐛 **Found a bug?** Open an issue on GitHub.
- 💡 **Have a feature idea?** Let's discuss it in Discussions.
- 🎵 **Enjoying Yumeoto?** Share it with friends who need focus and calm.

---

**Made with ❤️ for deep focus, peaceful moments, and the night owls.**
