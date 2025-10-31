# 🤖 Neo-Humanoid Project

### *An open-source, human-sized AI-driven robot built from the ground up — brain first.*

---

## 🧠 Overview

**Neo-Humanoid** is a 1.67 m tall, semi-autonomous humanoid robot designed to **learn, move, and react like a living creature**.
It combines **Rust-based real-time reflexes**, **distributed limb control**, and **multi-tier AI orchestration** (small and large language models) to bridge physical robotics and intelligent reasoning.

Inspired by **octopus neural systems** — each limb acts semi-independently while staying synchronized with a central brain.

---

## 🦾 Key Features

| Layer                                   | Role                                                  | Technology                                                                    |
| --------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------------------------------- |
| 🦵 **Tier 0 – Reflex & Balance**        | Real-time motion, fall recovery, stair climbing       | **Rust**, CAN/RS-485, local IMU/foot sensors                                  |
| 🧩 **Tier 1 – Orchestrator / Composer** | Fast reasoning, pattern calling, command routing      | **Rust + Tokio + gRPC + ROS 2 bridge**                                        |
| 🧠 **Tier 2 – Deep Reasoning Models**   | Scene understanding, planning, language               | **Qwen 2.5 (7B)** for mid-level, **Qwen 3 / DeepSeek v3.1** for deep planning |
| 🗣 **Speech & Hearing**                 | Whisper speech recognition, emotion-adaptive TTS      | **Whisper.cpp / Faster-Whisper**, **Coqui-TTS / Piper**                       |
| 🎮 **Distributed Limb Control**         | Each limb MCU handles local reflexes and torque loops | **ESP32 / STM32**, `no_std` Rust firmware                                     |
| 🔋 **Body & Power Core**                | Battery bay + Jetson / RK3588 AI compute              | Smart power manager + safety cut-off                                          |
| 🌈 **Face & Emotion System**            | LED eyes, head servos, mouth sync                     | Expression mapped to emotion tags                                             |
| ☁️ **Cloud Extension (optional)**       | Telepresence, memory, big VLMs                        | MQTT / WebRTC / REST                                                          |

---

## 🧬 Biological Inspiration

Neo's control architecture mimics **animal nervous systems**:

* **Reflex Layer:** Acts instantly (balance, avoid fall)
* **Muscle Memory:** Stores frequently used patterns for instant replay
* **Orchestrator Layer:** Decides *what* to do next
* **Deep Thought Layer:** Uses large AI models to analyze scenes and plan
* **Sensory Fusion:** Vision, sound, and touch combined for context-aware movement

Like a goldfish or octopus, Neo reuses learned motion sequences for fast, zero-latency reaction.

---

## 🛠 Tech Stack

* **Languages:** Rust 🦀 (core, control, orchestrator), Python (AI tools)
* **Frameworks:** ROS 2 (communication), gRPC, Tokio async runtime
* **AI Models:**

  * Whisper (speech recognition)
  * Qwen 2.5 7B → fast reasoning
  * Qwen 3 / DeepSeek v3.1 → deep reasoning
  * Coqui-TTS / Piper (speech synthesis)
* **Hardware:**

  * Jetson Orin Nano / RK3588 Pro (main AI board)
  * ESP32 / STM32 for limbs
  * Aluminum + flexible TPU frame, cotton padding
  * RGB + IR cameras, ToF sensors, IMUs, mic array
  * 24–48 V Li-ion battery system

---

## 🧩 System Architecture (high-level)

```
[User Voice] 
   ↓
[Whisper] → [Orchestrator AI (Rust)]
                ↓
   ┌──────────────────────────────────────────┐
   │ Tier 0: Reflex Layer (MCUs, Rust no_std) │
   │ Tier 1: Orchestrator / Pattern Engine    │
   │ Tier 2: Deep Models (Qwen / DeepSeek)    │
   └──────────────────────────────────────────┘
                ↓
        [Motors / Servos / Sensors]
```

---

## 💡 Development Roadmap

| Phase | Months | Goal                                                               |
| ----- | ------ | ------------------------------------------------------------------ |
| 🧩 1  | 1–2    | Build **brain simulation**: Whisper + Orchestrator + TTS (no body) |
| ⚙️ 2  | 3–4    | Prototype **limb control boards**, reflex motion in Rust           |
| 👁 3  | 5–6    | Add **head**: RGB/IR cameras, mic array, IMU                       |
| 🔋 4  | 7–8    | Build **torso**: battery + AI board + power manager                |
| 🦿 5  | 9–10   | Assemble full **1.67 m frame**, walking & balance                  |
| 🚀 6  | 11–12  | Integrate, polish, and **open-source release**                     |

---

## 🧠 Behavior Examples

* React to "Hey Neo" (wake-word)
* Walk to user and wave
* Look toward a voice source
* Pick up a recognized object (e.g., *"C++ Tutorial"* book)
* Repeat learned tasks from pattern memory
* Auto-recover from back-tilt or stair misstep in < 100 ms

---

## 🔓 Open Source Vision

Neo-Humanoid will be released under a permissive license (likely **Apache 2.0** or **MIT**) so developers and makers can:

* Build their own units
* Improve hardware designs
* Train and share new behavior patterns
* Connect to alternative AI models or cloud services

Community goal: **make humanoid robotics affordable, ethical, and developer-friendly**.

---

## 🧭 Future Ideas

* On-device learning (reinforce good motion sequences)
* Vision-language grounding (see → understand → act)
* Human emotion mirroring
* Home and lab assistant skills
* Optional solar charging dock

---

## 📦 Repository Layout

```
neo-humanoid/
├── orchestrator/          # Rust orchestration engine
├── reflex/                # Real-time limb & balance control
├── llm_client/            # Qwen / DeepSeek connectors
├── whisper_tts/           # Speech I/O (Whisper + Coqui)
├── patterns/              # Motion JSON / DSL files
├── hardware/              # CAD + wiring + MCU firmware
│   ├── cad/               # 3D models and mechanical designs
│   ├── wiring/            # Electrical schematics
│   └── firmware/          # MCU firmware for limbs
├── docs/                  # Hardware + software docs
└── LICENSE
```

---

## ❤️ Credits

* Concept & architecture: **Ehsan Tork**
* AI assistance: **GPT-5** (OpenAI)
* Inspired by: **octopus neural systems** and **goldfish pattern memory**

---

## 🚀 Getting Started

Coming soon! Check the `docs/` folder for installation and setup guides as the project develops.

---

**Status:** 🚧 Early development — contributions and ideas welcome!
