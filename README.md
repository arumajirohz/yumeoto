# 🌌 YUMEOTO — Web Audio Synthesis Engine & Developer Playground

> Open-source, browser-native procedural audio engine built with vanilla JavaScript and the Web Audio API.

**YUMEOTO (夢音 — Dream Sound)** is a single-file web application and technical demonstration of real-time Web Audio programming. It generates ambient textures procedurally while demonstrating browser audio architecture, signal processing, modulation, filtering, gain staging, responsive UI engineering, and an offline-first approach.

No audio files.  
No libraries.  
No tracking.  
Just code and sound.

## 🔗 Live Demo

👉 https://arumajirohz.github.io/yumeoto/

## 🧑‍💻 For Developers

YUMEOTO is also a small reference project and playground for developers experimenting with browser audio and the Web Audio API.

The implementation demonstrates:

- **Web Audio API programming** with `AudioContext`, `AudioBufferSourceNode`, `GainNode`, and `BiquadFilterNode`.
- **Procedural signal generation** using JavaScript rather than bundled audio assets.
- **Audio graph construction** by connecting sources through filters, modulation, and output stages.
- **LFO modulation** for controlled amplitude movement.
- **Gain staging and smooth ramps** for clean start/stop transitions.
- **Responsive frontend engineering** with a mobile-first, dependency-free interface.
- **Offline-first web development** with no backend, analytics, cookies, or runtime libraries.

The source is intentionally compact so developers can inspect the implementation, modify parameters, add generators, and experiment with alternative audio graphs.

## 🏗 Audio Architecture

```text
Procedural Noise Buffer
        ↓
BiquadFilterNode — tone shaping
        ↓
LFO → GainNode — modulation
        ↓
Master Gain — output control
        ↓
AudioContext.destination
```

Each stage is implemented with standard browser APIs and can be inspected or modified directly in `index.html`.

## 🎛 Procedural Audio Generation

All sounds are synthesized in real time using JavaScript and the Web Audio API — no MP3/WAV assets are required.

### Noise Profiles

- **White Noise** — high-pass filtered for distraction masking.
- **Pink Noise** — warmer tonal balance for ambient coverage.
- **Brown Noise** — low-pass filtered for deep, low-frequency ambience.

### Audio Techniques

- LFO-based amplitude modulation
- Biquad filter tone shaping
- Master gain control
- Smooth gain ramps to reduce clicks and pops
- Layering of independent procedural generators
- Reusable JavaScript functions for creating and controlling audio nodes

## 📦 Single-File Web Engineering

The complete application lives in one `index.html` containing HTML, CSS, and JavaScript.

There is no build step and no runtime dependency installation. This makes the code easy to inspect, fork, modify, test locally, and deploy as a static site.

## 🛠 Installation & Local Development

### Option 1: Download

Download `index.html` and open it in a modern browser.

### Option 2: Clone and serve locally

```bash
git clone https://github.com/arumajirohz/yumeoto.git
cd yumeoto
python -m http.server 8000
```

Then open `http://localhost:8000`.

## 🧪 Experimenting With the Engine

The project is intentionally easy to modify. Developers can experiment with:

- New noise-generation algorithms
- Additional filter types and frequencies
- Different oscillator/LFO modulation rates
- Gain curves and envelope behavior
- New `AudioNode` routing graphs
- Additional sound generators
- UI controls that expose audio parameters

A minimal Web Audio pattern used by the project can be reduced to:

```javascript
const ctx = new AudioContext();
const osc = ctx.createOscillator();
const gain = ctx.createGain();

osc.connect(gain).connect(ctx.destination);
osc.start();
```

## 🧠 Technical Philosophy

YUMEOTO focuses on readable browser-native engineering:

- **Zero dependencies** — vanilla JavaScript and platform Web APIs.
- **Small architecture** — audio processing remains visible and inspectable.
- **Offline-first** — the application does not depend on a backend service.
- **Privacy-first** — no analytics, cookies, or tracking.
- **Developer-friendly** — source code and technical behavior are easy to inspect and extend.
- **Responsive UI** — controls work across desktop and mobile browsers.

## 📝 File Structure

```text
yumeoto/
├── index.html          # Complete app (HTML + CSS + JS)
├── README.md           # Project and technical documentation
└── LICENSE             # GPLv3 License
```

## 🤝 Contributing

Improvements, bug reports, technical experiments, and feature requests are welcome.

When contributing:

- Keep the single-file architecture unless there is a strong reason to change it.
- Test on desktop and mobile browsers.
- Preserve low CPU and battery overhead.
- Keep the project dependency-free where practical.
- Maintain the privacy-first design.

## 🎨 Customization

The source is intentionally easy to customize:

- **Colors:** edit the CSS variables in `:root`.
- **Noise types:** extend `createNoiseBuffer()` and related generator logic.
- **Audio parameters:** adjust filter frequencies, gain values, and modulation rates.
- **UI controls:** add inputs that map directly to Web Audio parameters.
- **Audio routing:** experiment with additional `AudioNode` connections.

## 📚 Resources

- [Web Audio API — MDN](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [AudioContext — MDN](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext)
- [BiquadFilterNode — MDN](https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode)
- [GainNode — MDN](https://developer.mozilla.org/en-US/docs/Web/API/GainNode)
- [Colors of noise — Wikipedia](https://en.wikipedia.org/wiki/Colors_of_noise)

## 📄 License

GNU General Public License v3 (GPLv3) © 2026 Jaydev Mahesh Devkate

YUMEOTO is free and open-source software. You may use, modify, and distribute it under the terms of the GPLv3 license.

For the complete license, see [`LICENSE`](LICENSE).

## 🌐 Links

- 🎧 **Live application:** https://arumajirohz.github.io/yumeoto/
- 💻 **Source code:** https://github.com/arumajirohz/yumeoto
- 🐛 **Bug reports:** GitHub Issues
- 💡 **Feature discussions:** GitHub Discussions

**Made with ❤️ for developers experimenting with code, sound, and the Web Audio API.**
