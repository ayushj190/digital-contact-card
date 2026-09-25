# 🪪 High-Fidelity Personal Digital Business Card

A zero-dependency, single-file, hyper-optimized personal digital business card and link hub. Engineered with 100% native web standards (HTML5, CSS3, vanilla ES6+ JavaScript), responsive line-budget typography, 3D spring-physics tilt, spatial-hash Canvas2D particles, and micro-animated SVG state machines.

---

## 🚀 Get Your Own Card Live (In Minutes)

You can build, customize, and globally deploy your own version of this card completely free (or for just the yearly cost of a custom domain). 

**The Setup Process at a Glance:**
1. Fork or upload this code to a free GitHub repository.
2. Customize the data, links, and colors to your liking using AI.
3. Connect your GitHub repository to Cloudflare Pages for instant, edge-distributed hosting.

### 🤖 How to Build It Using AI

I've have provided an AI Agent Skill (`SKILL.md`) in the digital-info-card-designer that knows exactly how this codebase works. It will guide you step-by-step through customizing the code and getting it hosted on the web.

* **The Easy Path (For Non-Technical Users):** 
  You don't need any coding software. Just open up your favorite AI chat (like **ChatGPT**, **Gemini**, or **Claude**), copy all the text inside the `SKILL.md` file, paste it into the chat, and say: 
  > *"Act as this agent and guide me step-by-step to build, customize, and publish my digital business card."* 
  Copy the contents of index.html into the chat as well. The AI will hold your hand through the entire process.

* **For Developers & Pro Users:** 
  Feed `SKILL.md` directly into your AI coding environment (Cursor, Windsurf, Claude Code, GitHub Copilot). The agent will seamlessly execute the required Git commands, configure your personal data, and set up your deployment pipeline.

---

## ⚡ Technical Architecture & Deep Dive

### 1. Zero-Dependency & Config-Driven Design
The entire application resides within a single file, eliminating build pipelines, bundlers, and package vulnerability scans. All personalized data is configured in the centralized `CONFIG` literal at the start of the script block, keeping data separate from DOM structure.

### 2. Layout Stability & Strict Line Budgets
To completely prevent Cumulative Layout Shift (CLS) and dynamic jumping:
- **Name (`<h1>`)**: Clamped to 1 single line with strict overflow handling.
- **Title (`<h2>`)**: Clamped to 1 single line using viewport-scaled typography (`clamp()`).
- **Bio (`<p>`)**: Restricted to exactly 2 lines via WebKit line clamping backed by a fixed `min-height`.

### 3. Typography & Cryptographic Decryption Reveal
On initial page load, the profile bio and link URLs run through an asynchronous decryption shuffle. Characters randomly shift through binary and cipher glyphs (`01#$<>%&*+?@~`) before locking into plain text.

---

## 🎨 Interactive Mechanics & Micro-Animations

### 3D Elastic Physics & Magnetic Tethering
- **Viewport Cursor Parallax**: Tracks cursor offsets from the center of the card and converts them into rotational degrees, dropping sensitivity when hovering directly over the card to preserve readability.
- **Tactical Impact Punch**: Clicking any non-interactive surface executes an inverse spring shake calculated from the exact click coordinates relative to the card's center.
- **Magnetic Action Buttons**: Copy buttons compute cursor proximity on hover, elastically pulling the button toward the cursor using a damped sub-pixel offset vector.

### 3D Avatar Flipper & Pre-Rendered QR Handoff
- Tapping the avatar triggers a smooth 3D `rotateY(180deg)` flip transition.
- **Pre-Rendered Dual QR System**: Both light and dark SVG/PNG QR matrices are pre-mounted in the DOM. Changing themes fades their opacities seamlessly, avoiding the layout jitter of dynamic network requests.
- **Persistence & Inactivity Engine**: Flipping to the QR view locks a "Continue on mobile" indicator. After 120 seconds of inactivity, the card automatically flips back to the photo avatar to keep the layout fresh for subsequent viewers.

### Custom SVG Micro-Interactions
1. **Email**: 3D letter flap that scales and slides nested paper upward while typewriter strokes animate.
2. **LinkedIn**: A deterministic state machine coordinates a bouncing dot along the letter stems of the logo.
3. **GitHub**: A nonlinear rotational jitter state machine cycles between active shaking and rest phases using randomized intervals.
4. **Google Calendar**: A discrete SVG stepping block traverses a 6-cell day grid, directly integrated with the native Google Calendar overlay script.

---

## 🌌 Canvas2D Rendering Engines

### 1. Antigravity Particle Field (`#gravity-canvas`)
- **820 Anchored Nodes**: Each node computes an orbital equilibrium around a randomized anchor point.
- **Spatial Hash Grid Partitioning**: To maintain 60 FPS without massive distance checks, the canvas is indexed into spatial bins. Proximity checks only execute against immediate neighbors.
- **Dynamic Proximity Linking**: Inter-node mesh lines default to invisible. Approaching the cursor energizes adjacent nodes, dynamically fading in connecting lines based on distance.

### 2. Telemetry Radar HUD (`#info-canvas`)
- Features a harmonic breathing solid center core, a counter-rotating satellite orbital node, and a sweeping radar ping indicator.
- **Performance Guard**: Canvas color metrics are cached on theme initialization, avoiding expensive `getComputedStyle()` DOM calls during the 60FPS animation frames.

---

## ⚡ Easter Egg Overdrive Mode

Clicking any empty space on the card **8 times in rapid succession** unlocks Easter Egg Mode for 20 seconds:
- **Autonomous Animation Overdrive**: Envelope flaps flap continuously, the LinkedIn dot hops at $3\times$ speed, the GitHub Octocat jitters without pausing, and radar telemetry accelerates.
- **Avatar Strobe**: Rapidly toggles between light and dark portrait renders.
- **Dynamic Magnetic Repulsion**: The entire card actively flees from the user's cursor within a 280px radius. As it nears viewport edges, progressive border resistance increases its rotational vibration.
- **Haptic Sequence**: Triggers a vibrational pulse train on supported mobile devices.

---

## 📄 License
MIT License. Free to use, fork, and modify for personal or commercial portfolios.