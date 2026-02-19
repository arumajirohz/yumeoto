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
All sounds are synthesized in real-time using JavaScript and the Web Audio API — no MP3/WAV assets.

### 🌌 Deep Space Audio Architecture
Custom audio graph featuring:

- **LFO Modulation (0.08Hz)**  
  A slow sine wave subtly modulates amplitude so the atmosphere "breathes."

- **Tone Shaping Filters**  
  Carefully tuned `BiquadFilterNode` per noise type.

- **Sub-Bass Optimization**  
  Brown noise is low-pass filtered at 500Hz for deep, non-muddy rumble.

### 📦 Single-File Portability
The entire app (HTML, CSS, JS) lives inside one `index.html`.

### 🔋 Battery Efficient
10-second buffers are generated once and looped, minimizing CPU usage during playback.

### 🔐 Privacy First
- No cookies  
- No analytics  
- No external requests  

---

## 🎧 The Audio Engine

Unlike traditional white-noise apps that loop static audio files, Yumeoto constructs a procedural audio graph:
Noise Buffer (10s loop) ↓ BiquadFilterNode (Tone shaping) ↓ LFO → GainNode (Organic movement) ↓ Master Gain (Smooth ramping) ↓ AudioContext Destination

All transitions use smooth gain ramps to eliminate clicks and pops.

---

## 🎚 Noise Profiles

### White Noise
High-pass filtered (200Hz) to mask distractions without harsh hiss.

### Pink Noise
Low-shelf boost at 250Hz to mimic heavy rain or waterfalls.

### Brown Noise
Low-pass filtered (500Hz) and attenuated for a deep, spaceship-engine ambience.

---

## 🚀 How to Use

1. Open the live demo.
2. Select a sound (White, Pink, or Brown).
3. Mix multiple generators to create layered atmospheres.
4. Adjust individual volume sliders.
5. Use the floating master button to pause/resume the engine.

---

## 🛠 Local Usage

Yumeoto is fully portable.

1. Download `index.html`.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. Works offline instantly.

---

## 🧠 Technical Philosophy

Yumeoto is designed with:

- Minimal UI
- Low CPU overhead
- OLED-friendly color palette
- Zero dependencies
- Mathematical purity

Built for deep work sessions, long study blocks, and late-night calm.

---

## 📄 License

MIT License © 2026 Jaydev Devkate