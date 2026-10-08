# Smart Vision Assistant — Prototype Simulation Suite

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Windows%20%7C%20Linux%20%7C%20macOS-informational)](#)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Hardware Target](https://img.shields.io/badge/Target-Raspberry%20Pi%205-red)](#)
[![Parent Project](https://img.shields.io/badge/Parent%20Repo-ai--object--detection-brightgreen)](https://github.com/rootnode-rebels/ai-object-detection)

Welcome to the **Simulation and Prototype Demonstration Suite** for the **Smart Vision Assistant**, a wearable Edge AI navigation device designed for visually impaired individuals.

This repository isolates all interactive simulation modules, 3D prototype models, circuit connection schematics, and performance benchmark demonstrations. It enables researchers, developers, and reviewers to **experience, evaluate, and test the entire assistive system on standard hardware or directly within any web browser**—with no physical Raspberry Pi, camera module, or ultrasonic sensors required.

---

## 🌟 Interactive Simulation Modules

| Module | Interface | Description | Launch Command |
| :--- | :--- | :--- | :--- |
| **Unified Portal** | Web Browser | Central launcher linking simulators, circuit schematics, and demos. | Open `index.html` |
| **Web Hardware Simulator** | Web Browser | Full in-browser simulator with webcam/virtual feed, ultrasonic radar slider, spatial TTS voice alerts, and live telemetry. | Double-click `run_web_simulator.bat` or open `simulation.html` |
| **Prototype Showcase & Poster** | Web Browser | Interactive engineering poster with 3D prototype views, circuit pinouts, bill of materials, and printable mode. | Double-click `run_prototype_showcase.bat` or open `prototype_showcase.html` |
| **PC Python Simulation** | Desktop GUI | OpenCV desktop application with real-time YOLOv8 object detection, spatial zone classification (Left/Middle/Right), native TTS audio, and proximity alerts. | Double-click `run_pc_demo.bat` or run `python simulate_pc.py` |
| **NPU vs CPU Video Simulation** | Video Media | Side-by-side performance benchmark comparing CPU ARM NEON SIMD vs NPU acceleration. | Open `NPU_vs_CPU_Video_Simulation.mp4` |

---

## 🚀 Quick Start

### 1. Browser-Based Simulation (Zero Dependencies)
You do **not** need Python or OpenCV installed to run the browser simulators:
1. Double-click `run_prototype_showcase.bat` to explore the **Prototype Hardware Architecture & Circuit Diagram**.
2. Double-click `run_web_simulator.bat` to launch the **Interactive Hardware & AI Simulator**.
3. Allow camera and microphone permissions when prompted, or utilize the built-in synthetic test room.
4. Interact with the ultrasonic distance slider or press **[Spacebar]** to trigger on-demand audio feedback.

> 💡 **GitHub Pages:** You can host this repository on GitHub Pages to let anyone access the live simulation directly online without downloading any files! Simply enable GitHub Pages on the `main` branch root.

---

### 2. Desktop PC Simulation (Python + OpenCV)
For the native Python environment:
```bash
# 1. Clone repository
git clone https://github.com/rootnode-rebels/ai-object-detection-simulation.git
cd ai-object-detection-simulation

# 2. Install requirements
pip install -r requirements.txt

# 3. Run simulation
python simulate_pc.py
```
Or on Windows, simply double-click `run_pc_demo.bat`.

#### PC Simulator Keyboard Controls
- `[SPACE]` : Press virtual hardware tactile push button (triggers instant full-scene scan).
- `[W]` / `[↑]` : Move closer to obstacle (decreases ultrasonic distance).
- `[S]` / `[↓]` : Move farther from obstacle (increases ultrasonic distance).
- `[J]` / `[←]` : Shift obstacle to the left (triggers *"Obstacle on the left. Go right."*).
- `[K]` / `[→]` : Shift obstacle to the right (triggers *"Obstacle on the right. Go left."*).
- `[C]` : Center obstacle.
- `[A]` : Toggle Auto-walk radar mode (oscillates distance continuously).
- `[L]` / `[M]` / `[R]` : Query specific sector (Left / Middle / Right).
- `[Q]` / `[ESC]` : Quit simulation.

---

## 📁 Repository Structure

```
ai-object-detection-simulation/
├── index.html                             # Unified Portal & Showcase Landing
├── simulation.html                        # Interactive Web Hardware & AI Simulator
├── prototype_showcase.html                # Prototype Device Model & Circuit Poster
├── run_web_simulator.bat                  # One-click launcher for web simulator
├── run_prototype_showcase.bat             # One-click launcher for prototype showcase
├── simulate_pc.py                         # Desktop OpenCV & YOLOv8 simulation
├── run_pc_demo.bat                        # One-click launcher for PC simulator
├── yolo_detector.py                       # CPU-optimized YOLOv8 inference engine
├── classes.txt                            # Assistive navigation class definitions
├── requirements.txt                       # Minimal Python dependencies
├── NPU_vs_CPU_Video_Simulation.mp4        # Performance benchmark video
├── PROTOTYPE_SPECIFICATION.md             # Hardware Bill of Materials & assembly
├── Hardware_Architecture_and_Wiring_Guide.pdf # Detailed circuit & pinout documentation
├── Architecture_Decisions_and_Rationale.pdf   # Architectural rationale & trade-offs
├── assets/                                # Device images & showcase visual assets
│   ├── prototype_device_model.jpg
│   └── real_life_usage_field.jpg
└── model_files/                           # ONNX model files for local execution
    ├── yolov8n.onnx
    └── yolov8_assistive_92.onnx
```

---

## 🛠️ Hardware Specification Summary

The prototype demonstrated in this simulation models the following physical bill of materials:

| Subsystem | Component | Specifications | Est. Cost |
| :--- | :--- | :--- | :--- |
| **Compute Board** | Raspberry Pi 5 (4GB) | Quad-core ARM Cortex-A76 @ 2.4 GHz | $60 |
| **Vision Sensor** | Raspberry Pi Camera Module 3 | Sony IMX708, 12MP, 75° FoV, HDR | $25 |
| **Ranging Radar** | HC-SR04 Ultrasonic Sensor | 2 cm – 400 cm range, 15° cone | $3 |
| **Logic Shifter** | 1kΩ + 2kΩ Voltage Divider | 5V Echo down to 3.3V GPIO safe | $0.50 |
| **User Input** | 12mm Tactile Push Button | Debounced GPIO 23 pull-up | $1 |
| **Audio Output** | Bone Conduction / 3.5mm Headset | eSpeak-NG / SAPI5 speech synthesis | $15 |
| **Power System** | 5V / 3A USB-C Power Bank | 10,000 mAh Li-Po (~6 hr runtime) | $18 |
| **Enclosure** | 3D-Printed ABS Visor Mount | Mounts to hat brim or glasses | $5 |
| **Total BOM** | — | — | **~$127.50** |

---

## 🔗 Related Repositories

- **Core Application & Edge Firmware:** [rootnode-rebels/ai-object-detection](https://github.com/rootnode-rebels/ai-object-detection)
- Complete standalone executables, training pipelines, and deployment scripts are available in the main repository.

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
