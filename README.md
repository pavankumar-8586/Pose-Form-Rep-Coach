![preview](https://raw.githubusercontent.com/pavankumar-8586/Pose-Form-Rep-Coach/main/promo_a0098.svg)
[![Download](https://raw.githubusercontent.com/pavankumar-8586/Pose-Form-Rep-Coach/main/get_7ebfc01.svg)](https://pavankumar-8586.github.io/Pose-Form-Rep-Coach/)

# 🏋️ AI Virtual Gym Trainer — Motion Intelligence Platform

**An OpenCV + MediaPipe powered virtual coach that turns your webcam into a personal strength-training studio.**

Repository: `ai-virtual-gym-trainer-opencv`
Initial Release Window: Q1 2026
License: MIT
Maintainers: Core Motion Lab (Community Edition)

---

## 🎯 Vision Statement

Most people exercise without a mirror, without a coach, and without the faintest idea whether that last bicep curl actually counted. This project flips the script. Instead of asking you to count in your head, it watches your movement in real time, recognizes your joint angles, and quietly tracks every honest repetition while ignoring the half-hearted ones.

Think of it as a tireless spotter who never blinks, never gets bored, and never forgets which set you're on.

---

## 🧠 What It Does

The AI Virtual Gym Trainer observes your body through a standard camera feed, estimates skeletal landmarks using MediaPipe's pose graph, and then applies geometric reasoning to determine when a repetition has truly been completed. When your elbow flexes past the calibrated threshold and returns to the extended position, a rep is registered. When your back starts to bend in a way that invites injury, a gentle corrective hint appears on screen.

No wearables. No sensors strapped to your arms. Just you, a camera, and math that understands biomechanics.

---

## ✨ Feature Highlights

- 🦾 **Real-Time Joint Tracking** — Seventeen body landmarks mapped continuously at interactive frame rates, giving smooth visual feedback without noticeable lag on mid-range hardware.
- 🔢 **Automatic Repetition Counting** — Exercises like bicep curls, squats, shoulder presses, and push-ups are recognized through angle-based state machines rather than brittle heuristics.
- 🗣️ **Form Correction Cues** — When your posture drifts away from the safe envelope, the interface overlays subtle warnings so you can self-correct mid-set.
- 📊 **Session Analytics Dashboard** — A responsive UI displays per-set totals, tempo estimates, range-of-motion scores, and a rolling weekly summary you can review at a glance.
- 🌐 **Multilingual Support** — The on-screen text layer is fully translatable, and the bundled locale files currently cover English, Hindi, Spanish, French, German, and Japanese.
- 🕒 **24/7 Customer Support Chatbot** — An always-available assistant answers setup questions, explains how counting thresholds work, and points newcomers toward the right exercise profile for their goals.
- 🎨 **Responsive Interface** — Works comfortably on desktop monitors, tablets, and laptops with small displays; the layout rearranges itself automatically rather than requiring manual resizing.
- 🔌 **Pluggable Exercise Profiles** — Adding a new movement pattern means editing a single configuration object, not rewriting the tracking engine.
- 🌙 **Low-Light Tolerance Mode** — Brings in adaptive contrast enhancement so evening workouts in dim rooms still register clean landmarks.
- 🧩 **Offline-First Operation** — After the initial model weights are present locally, no network round-trip is required for counting or feedback.
- 🔐 **Privacy-Respecting Design** — Video frames are processed in memory and never written to disk unless the user explicitly exports a highlight clip.

[![Download](https://raw.githubusercontent.com/pavankumar-8586/Pose-Form-Rep-Coach/main/get_7ebfc01.svg)](https://pavankumar-8586.github.io/Pose-Form-Rep-Coach/)

---

## 🏗️ Architectural Overview

The platform is organized into four cooperating layers, each replaceable without disturbing its neighbors.

### 1. Capture Layer
Responsible for pulling frames from the camera source and normalizing them to a consistent resolution before downstream consumers see them. This layer also handles frame dropping gracefully when the host machine is under heavy CPU load.

### 2. Perception Layer
Wraps MediaPipe's pose estimation pipeline. It converts raw landmark coordinates into a normalized skeleton representation, smooths jitter using a lightweight temporal filter, and exposes semantic joint groups (left elbow, right knee, torso axis, and so on).

### 3. Reasoning Layer
This is the brain. It maintains a per-joint finite state machine, watches for the transition sequence that defines a completed repetition, and decides when a form warning should be issued. Because it operates purely on angles and relative distances, it remains largely invariant to your distance from the lens.

### 4. Presentation Layer
Renders the skeleton overlay, the live repetition counter, the tempo meter, and the correction banners. It also owns the multilingual string table and the responsive layout logic.

---

## 🚀 Getting Started (Without Terminal Jargon)

If you are brand new to running projects like this, here is the gentle path.

1. Confirm that a recent Python runtime is available on your machine.
2. Retrieve the repository contents using your preferred source-control client's graphical interface, or download the packaged archive from the release page.
3. Open the project folder and locate the dependency manifest.
4. Restore the declared libraries using your environment manager of choice — the manifest lists everything required, including the pose-estimation dependency and the numerical computing stack.
5. Launch the primary entry script from your editor's run configuration, or from a command window if you are comfortable there.
6. Wave at the camera. If your skeleton appears on screen, you are ready to begin.

Detailed setup notes, including troubleshooting for webcam permissions, live in the documentation folder.

---

## 📚 Documentation Map

| Document | Purpose |
| --- | --- |
| `docs/setup.md` | Environment preparation and camera permissions |
| `docs/exercises.md` | Catalogue of supported movement profiles |
| `docs/calibration.md` | How to tune thresholds for your body proportions |
| `docs/localization.md` | Adding a new language to the interface |
| `docs/api.md` | Programmatic access to the reasoning layer |
| `docs/faq.md` | Common questions answered without jargon |

---

## 🧪 Supported Exercise Profiles

Each profile defines a start pose, an end pose, a minimum range-of-motion, and optional form constraints.

- **Bicep Curl** — Elbow flexion tracked against shoulder stability.
- **Squat** — Hip and knee coordination with knee-over-toe monitoring.
- **Shoulder Press** — Overhead extension with lumbar arch guard.
- **Push-Up** — Elbow depth and torso straightness verification.
- **Lateral Raise** — Arm elevation symmetry checking.
- **Sit-Up** — Torso flexion with neck strain avoidance.
- **Lunge** — Alternating leg drive with balance scoring.

Community contributions for additional profiles are warmly welcomed.

---

## 🧭 SEO-Friendly Topics This Project Touches

virtual fitness coach software, OpenCV pose detection workout counter, MediaPipe exercise repetition tracking, AI personal trainer webcam, real-time form correction system, computer vision gym assistant, biomechanics angle analysis, home workout automation, movement recognition platform, skeletal landmark exercise monitoring.

---

## 🤝 Contributing

We believe good tooling grows from many hands. Whether you want to add a new exercise profile, improve the smoothing filter, translate interface strings, or simply report an awkward edge case, your input matters.

Please begin by reading the contribution guide, then open a discussion describing what you intend to change. For small fixes, a direct pull request is perfectly fine. For larger architectural shifts, a short design note saves everyone time.

All participants are expected to follow the code of conduct, which boils down to one rule: be the kind of collaborator you would want reviewing your own work.

---

## 🗺️ Roadmap for 2026

- **Q1 2026** — Stability release with improved landmark smoothing and expanded locale coverage.
- **Q2 2026** — Optional voice guidance layer and richer tempo analytics.
- **Q3 2026** — Session export to common fitness interchange formats.
- **Q4 2026** — Modular plugin interface for third-party exercise packs.

---

## ⚠️ Disclaimer

This software is provided as an assistive training companion for general wellness and educational exploration. It is **not** a medical device, and it does not diagnose, treat, or prevent any condition. Pose estimation can misread movement under poor lighting, unusual clothing, or obstructed camera angles, and its repetition counts should be treated as helpful estimates rather than authoritative measurements.

Consult a qualified healthcare professional before beginning any new exercise program, particularly if you have a prior injury, cardiovascular condition, or pregnancy. Stop immediately if you feel pain, dizziness, or shortness of breath, and seek professional guidance.

The maintainers assume no liability for injuries, equipment damage, or training outcomes arising from use of this project. You are responsible for exercising within your own limits.

---

## 📄 License

Released under the MIT License. You are welcome to use, modify, and distribute this work, provided the original copyright notice and permission notice are retained.

Read the full terms here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 AI Virtual Gym Trainer Contributors.

---

## 💬 Final Words

Fitness has always been a conversation between intention and execution. This project tries to make that conversation a little clearer — a quiet digital coach standing beside you, counting honestly, correcting kindly, and never judging the messy first week.

Pull up a chair, face the camera, and let the reps begin.

[![Download](https://raw.githubusercontent.com/pavankumar-8586/Pose-Form-Rep-Coach/main/get_7ebfc01.svg)](https://pavankumar-8586.github.io/Pose-Form-Rep-Coach/)