# VR Fitness Trainer (Unity + Meta Quest 3): Interactive Robot-Guided Workouts

> **Demo video:**  
> https://drive.google.com/file/d/1vfT-xH2_dNSjfL3gj2sG6v6xcZ2-IoVd/view?usp=drive_link

<!-- HERO IMAGE -->
<!-- Add a banner/hero screenshot of the gym scene -->
<p align="center">
  <img width="900" alt="VR gym overview — hero banner" src="https://github.com/user-attachments/assets/1f468386-be36-43de-a02a-1a93056d0225" />
</p>

## Overview
A Unity-based VR fitness experience with animated robot trainers, a diegetic workout menu, and support for controller rays and hand tracking on Meta Quest.

**Highlights**
- Two robot trainers with idle and workout animations
- Exercise menu with **Easy / Medium / Hard** tiers
- Exercise logging (sets/reps) and between-set countdown
- Teleport + direct locomotion; controller and (optional) hand tracking
- Lightweight, standalone Quest build

## Scenario
Simulated indoor gym where users select a difficulty, choose an exercise, and watch the robots demonstrate the routine while following along.

<!-- FIGURE: Scenario mock 1 -->
<p align="center">
  <img width="800" alt="Scenario mock — wide view of gym and menu" src="https://github.com/user-attachments/assets/9a29f02b-a550-4666-a2b4-37576b2f1c2e" />
  <br><em>Fig. 1 — Scenario mock: two robot trainers with a central exercise menu.</em>
</p>

<!-- FIGURE: Scenario mock 2 -->
<p align="center">
  <img width="800" alt="Scenario mock — menu close-up" src="https://github.com/user-attachments/assets/56987240-4923-45e0-86dc-867db76801f7" />
  <br><em>Fig. 2 — Menu close-up for exercise selection.</em>
</p>

## Features
- **Robot Trainers:** Idle, workout, and rest states with smooth transitions  
- **Workout Menu:** World-space UI for difficulty + exercise selection  
- **Interaction:** XR Ray Interactors; optional hand tracking (pinch/select)  
- **Feedback:** On-screen set/reps status; countdown timer between sets  
- **Performance:** Mobile-friendly assets, baked lighting, mesh compression

<!-- FIGURE: Example workout 1 -->
<p align="center">
  <img width="800" alt="Pushup routine in progress" src="https://github.com/user-attachments/assets/fd7dc1d9-62c9-471a-8c41-b5011434fc91" />
  <br><em>Fig. 3 — Pushup routine in progress.</em>
</p>

<!-- FIGURE: Example workout 2 -->
<p align="center">
  <img width="800" alt="Jumping jacks with synchronized robots" src="https://github.com/user-attachments/assets/1d7eb0c7-5f70-49b9-ad53-42e2a7845c31" />
  <br><em>Fig. 4 — Jumping jacks with synchronized robots.</em>
</p>

## Architecture
Unity project using **XR Interaction Toolkit** + **OpenXR**. An XR Origin handles HMD and controllers; event-driven UI triggers animation state changes on the robots.

<!-- FIGURE: Architecture diagram -->
<p align="center">
  <img width="800" alt="System architecture diagram: XR Origin, UI canvas, Animator controllers" src="https://github.com/user-attachments/assets/2f70369a-af05-4629-8b38-dcb4a6895c35" />
  <br><em>Fig. 5 — Core components: XR Origin, world-space UI, and Animator controllers.</em>
</p>

<!-- FIGURE: Architecture detail / reference -->
<p align="center">
  <img width="800" alt="Reference setup screenshot — components and inspector" src="https://github.com/user-attachments/assets/8c45e046-763d-4fd0-91c3-60dfed2a8318" />
  <br><em>Fig. 6 — Reference setup (components/inspector view).</em>
</p>

**Core objects**
- **XR Origin** (HMD + Left/Right controllers, ray interactors)  
- **Robots** (Humanoid rigs with Animator controllers)  
- **World-Space UI** (exercise & difficulty menus)  
- **Managers** (Animation, Menu, Session/Log)



<!-- FIGURE: Session log -->
<p align="center">
  <img width="800" alt="In-game session log — completed sets and reps" src="https://github.com/user-attachments/assets/e96e2158-0109-4f89-97fd-f7ff39ae2bb4" />
  <br><em>Fig. 8 — Session log with completed sets and reps.</em>
</p>

