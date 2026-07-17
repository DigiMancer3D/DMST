# DigiMancer Stream

**The unified parent hub for the DigiMancer Streamer Tools ecosystem**

> One console. All your stream tools.  
> Low-resource • Linux-first • OBS-native • VTuber-ready

![DigiMancer Stream](https://raw.githubusercontent.com/DigiMancer3D/DMST/refs/heads/main/Github_group.png)

---

### What is this?

**DigiMancer Stream** is the single entry-point repository that ties together every streamer-focused tool I use.  

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
| **Streamer-Board-Console** | [DigiMancer3D/Streamer-Board-Console](https://github.com/DigiMancer3D/Streamer-Board-Console) | The central command center. Launch, close, profile, monitor, and orchestrate every other tool via Studio Profiles, adapters, hotkeys, and Pin Boards. |
| **Deck-Card-Widget** | [DigiMancer3D/Deck-Card-Widget](https://github.com/DigiMancer3D/Deck-Card-Widget) | Low-resource Tkinter deck-card overlay for OBS. Editable labels, emoji/PNG/text layers, persistent `.buttstore` files, and a clean Output window for capture. |
| **Bitninja-Mocap-Lite** | [DigiMancer3D/Bitninja-Mocap-Lite](https://github.com/DigiMancer3D/Bitninja-Mocap-Lite) | OBS-focused local VTuber mocap (SysMocap fork) with low-latency VRM tracking, local model loading, performance presets, and WebSocket/HTTP output options. |
| **SWAR** (Script Writer & Reader) | [Inside 3DChangesPerspectives](https://github.com/DigiMancer3D/3DChangesPerspectives/tree/main/SWAR) | Structured live-script writer & reader for shows, episodes, and notes. Uses the plain-text `*.script` format (plus `.md`, `.txt`, and `.arcs`). |
| **Sound Card** | [DigiMancer3D/soundcard](https://github.com/DigiMancer3D/soundcard) | Real-time microphone visualizer with a living physics blob + vocal EQ bars. Fun Super Saiyan power-up mode included. Perfect OBS overlay. |
| **G502v** | [DigiMancer3D/G502V](https://github.com/DigiMancer3D/G502V) | Mouse overlay visualizer built specifically for the Logitech G502. Real-time button lighting, scroll, tilt, and Yew Icon tracking. |

---

### Installation & Setup

> Recommended order, install the console first so it can help manage the rest.

#### 1. Streamer-Board-Console (the hub)

```bash
git clone https://github.com/DigiMancer3D/Streamer-Board-Console.git
cd Streamer-Board-Console

# Make scripts executable
chmod +x install_kubuntu.sh launch_streamer_board_console.sh launch_streamer_board_console_rescue.sh tools/*.sh tools/*.py

# Install (creates local .venv + dependencies)
./install_kubuntu.sh

# Optional: pull all companion apps into ~/SBC_Streamer_Apps/
chmod +x install_optional_streamer_apps.sh
./install_optional_streamer_apps.sh

# Self-test + launch
./tools/sbc_selftest.sh
./launch_streamer_board_console.sh
```

Desktop entries and a rescue launcher (for off-screen windows) are also available.

#### 2. Deck-Card-Widget

```bash
git clone https://github.com/DigiMancer3D/Deck-Card-Widget.git
cd Deck-Card-Widget

# Linux (Ubuntu/Debian example)
sudo apt install python3-tk   # if needed
chmod +x setup_venv_3dcp_console.sh launch_deck_card_widget_venv.sh
./setup_venv_3dcp_console.sh
./launch_deck_card_widget_venv.sh
```

Manual alternative: create a venv, `pip install -r requirements.txt`, then run `3dcp_perspective_console.py`.

#### 3. Bitninja-Mocap-Lite

```bash
git clone https://github.com/DigiMancer3D/Bitninja-Mocap-Lite.git
cd Bitninja-Mocap-Lite
npm install

# Recommended launcher (Kubuntu/KDE)
./run_bitninja_lite_standard.sh

# Or NVIDIA / Mesa variants as needed
```

Place `.vrm` models in the `models/` folder (optional thumbnails in `models/img/`).

#### 4. SWAR (Script Writer & Reader)

```bash
git clone https://github.com/DigiMancer3D/3DChangesPerspectives.git
cd 3DChangesPerspectives/SWAR

chmod +x install_kubuntu.sh launch_standard.sh launch_reader.sh
./install_kubuntu.sh
./launch_standard.sh          # editor mode
# or
./launch_reader.sh examples/example.script
```

SWAR works with the plain-text `*.script` format (also supports `.md`, `.txt`, and `.arcs` Story Arc files).

#### 5. Sound Card

```bash
git clone https://github.com/DigiMancer3D/soundcard.git
cd soundcard
python3 -m venv venv
source venv/bin/activate
pip install sounddevice numpy
python soundcard.py
```

Settings auto-save to `soundcard.crumbs`.

#### 6. G502v

```bash
git clone https://github.com/DigiMancer3D/G502V.git
cd G502V
python3 -m venv venv
source venv/bin/activate
pip install pynput
# Ubuntu/Debian: sudo apt install python3-tk
python3 g502viz.py
```

Settings live in `settings.crumbs` and `mappings.json`.

> **Tip:** After installing the console’s optional companion apps script, most of these can be pointed to via **Apps → Adapter Templates** inside Streamer-Board-Console for one-click launch/close.

---

### Conceptual Workflow, Getting on Stream

Here’s the intended “happy path” once everything is installed:

1. **Launch the Console**  
   `./launch_streamer_board_console.sh`

2. **Create a Studio Profile**  
   Open the **Studio Profiles** tab → make a new profile (e.g. “Talk Show”, “Gaming”, “VTuber Session”).  
   For each adapter set the desired action: *Launch*, *Keep*, *Close*, *Restart*, etc.

3. **Launch & Arrange Apps**  
   One-click the profile (or launch apps individually).  
   - Use **Pin Boards** inside the console for reusable image boards (OBS Window Capture friendly).  
   - Capture each tool’s dedicated output window in OBS.

4. **Per-App Setup**  
   - **Deck-Card-Widget** → edit cards, add emoji/PNG layers, save a `.buttstore`. Capture the *Deck Card Widget - Output* window.  
   - **Pin Boards** (from the console) → create reusable reference boards.  
   - **Bitninja-Mocap-Lite** → load your VRM, choose an OBS Fast / OBS Smooth preset, frame the model.  
   - **Sound Card** → poke the blob, adjust gain & colors, set chroma key background.  
   - **G502v** → map buttons, set chroma key, position the Yew Icon.

5. **Write Episodes & Notes with SWAR**  
   Open SWAR in editor or split mode.  
   Author your show scripts, spoken cues, research notes, and Story Arcs using the `*.script` format.  
   Export HTML or outlines as needed. Keep private links masked.

Everything stays local, lightweight, and modular, you can always run any tool standalone if you prefer.

---

![DigiMancer Stream group](https://raw.githubusercontent.com/DigiMancer3D/DMST/refs/heads/main/DM3D_group_2.png)

---

### Philosophy

- Stay local  
- Stay lightweight  
- Stay modular  
- Stay weird (in a good way)  

Every tool is built so it can run alone **or** be controlled by the Streamer-Board-Console.  
You are never forced into a monolithic app.

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

***DigiMancer Stream**, stream tools that talk to each other*
