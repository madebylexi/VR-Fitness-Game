# VR Fitness Trainer (Unity + Meta Quest 3): Interactive Robot-Guided Workouts

> **Demo video:** _Paste your link here_  
> Example: https://drive.google.com/...

<!-- HERO IMAGE -->
<!-- Add a banner/hero screenshot of the gym scene -->
<p align="center">
  <img src="docs/images/hero.png" width="900" alt="VR gym overview — add your screenshot">
</p>

## Overview
A Unity-based VR fitness experience with animated robot trainers, a diegetic workout menu, and support for controller rays and hand tracking on Meta Quest.

**Highlights**
- Two robot trainers with idle and workout animations
- Exercise menu with **Easy / Medium / Hard** tiers
- Exercise logging (sets/reps) and between-set countdown
- Teleport + direct locomotion; controller and (optional) hand tracking
- Lightweight, standalone Quest build

## Table of Contents
- [Overview](#overview)
- [Scenario](#scenario)
- [Features](#features)
- [Architecture](#architecture)
- [Scene & UI](#scene--ui)
- [Controls](#controls)
- [How to Run](#how-to-run)
- [Add a New Exercise](#add-a-new-exercise)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [Citing & Acknowledgments](#citing--acknowledgments)
- [License](#license)

## Scenario
Simulated indoor gym where users select a difficulty, choose an exercise, and watch the robots demonstrate the routine while following along.

<!-- FIGURE: Scenario mock -->
<p align="center">
  <img src="docs/images/scenario-mock.png" width="800" alt="Scenario mock — add your screenshot">
  <br><em>Fig. 1 — Scenario mock: two robot trainers with a central exercise menu.</em>
</p>

## Features
- **Robot Trainers:** Idle, workout, and rest states with smooth transitions
- **Workout Menu:** World-space UI for difficulty + exercise selection
- **Interaction:** XR Ray Interactors; optional hand tracking (pinch/select)
- **Feedback:** On-screen set/reps status; countdown timer between sets
- **Performance:** Mobile-friendly assets, baked lighting, mesh compression

<!-- FIGURE: Example workouts -->
<p align="center">
  <img src="docs/images/workout-pushups.png" width="800" alt="Pushups — add your screenshot">
  <br><em>Fig. 2 — Pushup routine in progress.</em>
</p>

<p align="center">
  <img src="docs/images/workout-jumpingjacks.png" width="800" alt="Jumping jacks — add your screenshot">
  <br><em>Fig. 3 — Jumping jacks with synchronized robots.</em>
</p>

## Architecture
Unity project using **XR Interaction Toolkit** + **OpenXR**. An XR Origin handles HMD and controllers; event-driven UI triggers animation state changes on the robots.

<!-- FIGURE: Architecture diagram -->
<p align="center">
  <img src="docs/images/architecture.png" width="900" alt="System architecture — add your diagram/screenshot">
  <br><em>Fig. 4 — Core components: XR Origin, UI canvas, Animator controllers.</em>
</p>

**Core objects**
- **XR Origin** (HMD + Left/Right controllers, ray interactors)
- **Robots** (Humanoid rigs with Animator controllers)
- **World-Space UI** (exercise & difficulty menus)
- **Managers** (Animation, Menu, Session/Log)

## Scene & UI
World-space canvas between robots; large tap targets; session HUD shows current set/rep and rest timers.

<!-- FIGURE: Scene overview -->
<p align="center">
  <img src="docs/images/scene-overview.png" width="900" alt="Scene overview — add your screenshot">
  <br><em>Fig. 5 — Scene overview: layout, lighting, mirror walls, mats.</em>
</p>

<!-- FIGURE: UI -->
<p align="center">
  <img src="docs/images/ui-menu.png" width="800" alt="Exercise menu — add your screenshot">
  <br><em>Fig. 6 — Exercise selection menu by difficulty.</em>
</p>

## Controls
- **Select / Activate:** Controller ray + trigger (or hand-tracking pinch)
- **Teleport:** Primary teleport input (left/right)
- **Reset / Back to Menu:** Mapped in UI buttons

<!-- FIGURE: Controls map -->
<p align="center">
  <img src="docs/images/controls-map.png" width="800" alt="Controls mapping — add your diagram/screenshot">
  <br><em>Fig. 7 — Control scheme for controllers and hand tracking.</em>
</p>

## How to Run
> _Fill in the exact versions you used (Unity LTS, XR Interaction Toolkit, OpenXR, Input System)._

1. **Clone & Open**
   - Unity **20xx.x LTS** (tested on: _your version_)
   - Packages: OpenXR, XR Interaction Toolkit, XR Plugin Management, Input System

2. **Project Settings**
   - **XR Plugin Management:** Enable **OpenXR** for **Android** (and Standalone if testing in Editor)
   - **OpenXR Features (Android):** Meta/Oculus Touch Controller Profile, Hand Tracking (optional)
   - **Input System:** New Input System (or both), restart when prompted

3. **Build Settings (Quest)**
   - Platform: **Android**; Architecture: **ARM64**; Scripting Backend: **IL2CPP**
   - Minimum API Level: **Android 10+** (Quest-compatible)
   - Texture compression: ASTC (recommended)

4. **Deploy**
   - Enable Developer Mode on Quest; connect via USB
   - **Build & Run** from Unity or use `adb install -r your.apk`

## Add a New Exercise
1. **Animation**
   - Import/author FBX with humanoid rig
   - Create an **Animation Clip** (e.g., `Squat_Loop`)
2. **Animator**
   - Add state for the new clip
   - Define parameters (e.g., `ExerciseType`, `IsPlaying`); add transition rules
3. **UI Hookup**
   - Add a button in the world-space menu
   - Wire the button’s `onClick` to your **AnimationManager** method
4. **Session Log (optional)**
   - Update set/rep counters and timer if needed

<!-- FIGURE: Animator controller -->
<p align="center">
  <img src="docs/images/animator-controller.png" width="900" alt="Animator state machine — add your screenshot">
  <br><em>Fig. 8 — Animator with idle, active, and rest transitions.</em>
</p>

## Troubleshooting
- **Player height feels off:** Recenter XR Origin or adjust **Camera Offset**
- **UI not clickable:** Ensure Canvas **World Space**, proper layer, and **XR Ray Interactable** setup
- **Physics API warnings:** Use `rb.velocity` etc. (avoid deprecated `rigidbody` alias)
- **Hand tracking unresponsive:** Confirm OpenXR hand-tracking feature is enabled (Android)

## Roadmap
- AI-based form feedback (pose estimation + real-time coaching)
- Personalized workout plans and progress tracking
- Expanded exercise library and difficulty scaling

<!-- FIGURE: Session log -->
<p align="center">
  <img src="docs/images/session-log.png" width="900" alt="In-game session log — add your screenshot">
  <br><em>Fig. 9 — Session log with completed sets and reps.</em>
</p>

## Citing & Acknowledgments
If you reference this project academically, please cite the associated report (FAU, Dept. of CS).  
_Replace with full citation block once finalized._

- Primary authorship & guidance: _Your name_; _Advisor / Lab_
- Built with Unity, XR Interaction Toolkit, and OpenXR

## License
_Choose a license (e.g., MIT) and place it here._
