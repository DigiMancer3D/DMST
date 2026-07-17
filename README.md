# DigiMancer Stream

**The unified parent hub for the DigiMancer Streamer Tools ecosystem**

> One console. All your stream tools.  
> Low-resource • Linux-first • OBS-native • VTuber-ready

![DigiMancer Stream](https://raw.githubusercontent.com/DigiMancer3D/DMST/refs/heads/main/Github_group.png)

---

### What is this?

**DigiMancer Stream** is the single entry-point repository that ties together every streamer-focused tool I’ve built.  

This exists so anyone can quickly discover, understand, and launch the full suite without hunting through individual repos.

At the center sits **Streamer-Board-Console**, a lightweight local control hub that can launch, park, monitor, and orchestrate all the companion apps via profiles, hotkeys, and pin boards.

Everything is designed to be:
- Extremely low-resource
- Fully local (no cloud dependency)
- OBS Window Capture friendly
- Easy to extend with new adapters

---

### The Suite

| Tool | Repo | Purpose |
|------|------|---------|
| **Streamer-Board-Console** | [DigiMancer3D/Streamer-Board-Console](https://github.com/DigiMancer3D/Streamer-Board-Console) | The central command center. Launch, close, profile, and monitor every other tool. |
| **Deck-Card-Widget** | [DigiMancer3D/Deck-Card-Widget](https://github.com/DigiMancer3D/Deck-Card-Widget) | Low-resource Tkinter deck-card overlay system for OBS. Editable labels, emoji, PNG layers, and persistent `.buttstore` files. |
| **Bitninja-Mocap-Lite** | [DigiMancer3D/Bitninja-Mocap-Lite](https://github.com/DigiMancer3D/Bitninja-Mocap-Lite) | OBS-focused local VTuber mocap (SysMocap fork) with low-latency VRM tracking, local model loading, and WebSocket/HTTP output. |
| **SWAR** (Script Writer & Reader) | Inside [3DChangesPerspectives](https://github.com/DigiMancer3D/3DChangesPerspectives) | Structured live-script format + reader for shows and presentations. |
| **G502v** | [G502v](https://github.com/DigiMancer3D/G502V) | Mouse overlay visualizer specifically for the Logitech G502. |
| **Sound Card** | [Sound Card](https://github.com/DigiMancer3D/soundcard) | Audio interactive overlay that works with linux. |

---

### Quick Start

1. Clone this meta-repo (optional but recommended):
   ```bash
   git clone https://github.com/DigiMancer3D/DigiMancer-Stream.git
   cd DigiMancer-Stream
   ```

2. Clone the core console:
   ```bash
   git clone https://github.com/DigiMancer3D/Streamer-Board-Console.git
   cd Streamer-Board-Console
   ```

3. Follow the install scripts inside `Streamer-Board-Console`  
   (they can optionally pull the companion apps for you).

4. Launch the console → create a Studio Profile → one-click start your whole stream setup.

Detailed per-tool instructions live in each individual repository.

---

### Visual Identity

The DigiMancer Stream brand uses:
- The green cat-eared VTuber (red spiral eyes)
- The tissue-connected eyeball-avocado pendant
- Double-bar northern Russian Orthodox crosses (no slanted lower bar)
- Heavy green pin-glows and digital nebula aesthetics

All official logos, banners, social images, and the current profile picture can be found in the [`/assets`](./assets) folder of this repo (or generated from the design set).

---

### Philosophy

- Stay local
- Stay lightweight
- Stay modular
- Stay weird (in a good way)

Every tool is built so it can run alone **or** be controlled by the Streamer-Board-Console.  
You are never forced into a monolithic app.

---

### Contributing / Requests

Found a bug? Want a new adapter?  
Open an issue on the relevant tool repo **or** on this meta-repo if it concerns the whole ecosystem.

Pull requests are welcome, especially for:
- New app adapters
- Better install scripts
- Documentation improvements

---

### Links

- GitHub: [DigiMancer3D](https://github.com/DigiMancer3D)
- X / Twitter: [@Z0M8I3D](https://x.com/Z0M8I3D)
- Site: [3Dthe.ninja](https://3Dthe.ninja)

---

### License

Individual tools keep their own licenses (mostly BSD-3-Clause or MPL-2.0).  
This meta-repository is released under **BSD-3-Clause**.

---

* **DigiMancer Stream**, stream tools that talk to each other *  


