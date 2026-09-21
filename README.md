![preview](https://raw.githubusercontent.com/raneesvp/clap-sequencer/main/card_387c.svg)
[![Download](https://raw.githubusercontent.com/raneesvp/clap-sequencer/main/app_8531.svg)](https://raneesvp.github.io/clap-sequencer/)

# 🥁 Reich — Clapping Music Trainer

**A minimalist, browser-based trainer that turns Steve Reich's *Clapping Music* into a playable, learnable, and endlessly fascinating rhythmic puzzle.**

Inspired by the hypnotic 1972 composition for two performers, this project reimagines the piece as an interactive training companion. Whether you are a percussionist chasing perfect phasing, a music theory enthusiast dissecting additive patterns, or simply curious about how a single measure of twelve beats can spiral into a mesmerizing web of shifting accents — this trainer was built for you.

[![Download](https://raw.githubusercontent.com/raneesvp/clap-sequencer/main/app_8531.svg)](https://raneesvp.github.io/clap-sequencer/)

---

## 📜 Table of Contents

- [Introduction](#-introduction)
- [What Is Clapping Music?](#-what-is-clapping-music)
- [Why This Project Exists](#-why-this-project-exists)
- [Feature Highlights](#-feature-highlights)
- [How the Trainer Works](#-how-the-trainer-works)
- [The Rhythm Engine](#-the-rhythm-engine)
- [Design Philosophy](#-design-philosophy)
- [Responsive Interface](#-responsive-interface)
- [Multilingual Experience](#-multilingual-experience)
- [Accessibility Commitments](#-accessibility-commitments)
- [Performance Metrics](#-performance-metrics)
- [Round-the-Clock Assistance](#-round-the-clock-assistance)
- [Roadmap](#-roadmap)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Contributing](#-contributing)
- [Code of Conduct](#-code-of-conduct)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🎯 Introduction

Steve Reich's *Clapping Music* is deceptively simple on paper. Two performers clap the same twelve-beat pattern. One stays fixed. The other shifts the entire pattern one beat to the left every twelve repetitions. After twelve such shifts, the second performer lands back in sync with the first. The whole piece lasts roughly five minutes, yet it contains an entire universe of rhythmic perception.

This repository is a **trainer** — not a simulator, not a synthesizer, not a toy. It is a tool for building the internal clock that *Clapping Music* demands. It teaches your hands, ears, and eyes to cooperate in maintaining a groove while the ground shifts beneath you.

The project is written with a love for minimalism in both music and code. Every line of the interface is intentional. Every sound is deliberate. Every pixel earns its place.

---

## 🎼 What Is Clapping Music?

Composed in 1972, *Clapping Music* belongs to Reich's "phasing" period, sitting alongside works like *Piano Phase* and *Drumming*. Unlike those pieces, however, *Clapping Music* abandons gradual phasing in favor of **abrupt displacement**. The second performer does not drift; they jump.

The foundational pattern is:

> **x . x x . x x . x x . x**

That is: clap, rest, clap, clap, rest, clap, clap, rest, clap, clap, rest, clap.

Twelve beats. Five rests. Seven claps. Yet the pattern, when displaced, produces chords of rhythm that sound entirely new — moments of unison, moments of tension, moments of near-resolution. It is a masterclass in how little material is needed to produce enormous perceptual variety.

This trainer helps you internalize each displacement phase individually, then in sequence, so that the full piece becomes second nature.

---

## 💡 Why This Project Exists

Most rehearsal tools for *Clapping Music* are either:

1. **Too rigid** — they play the piece from start to finish with no way to isolate a phase.
2. **Too sparse** — they offer a metronome and nothing more.
3. **Too complex** — they bury a simple idea under layers of studio-grade configuration.

This project sits in the sweet spot. It gives you **surgical control** over the displacement phase, the tempo, the visual feedback, and the audio character, while keeping the interface clean enough to use on a phone during a rehearsal break.

It is a **practice room**, not a concert hall. It is a **sketchbook**, not a gallery. It is the metronome you always wished existed when you first tried to clap along and lost the beat at phase seven.

---

## ✨ Feature Highlights

- **Phase Isolation** — Jump directly to any of the thirteen positions (0 through 12) without waiting for the piece to cycle.
- **Auto-Advance Mode** — Let the trainer step through phases automatically at a user-defined repetition count.
- **Tempo Sculpting** — Adjust from a patient 60 BPM up to a brisk 240 BPM, with fine-grained control in between.
- **Visual Pulse Grid** — An animated twelve-cell grid that lights up in real time, reinforcing the beat visually.
- **Accent Customization** — Emphasize the downbeat, mute it, or remove accents entirely for a flatter practice texture.
- **Hand Assignment** — Choose which side (left or right) plays the fixed pattern and which plays the moving pattern.
- **Count-In Support** — A configurable count-in gives you time to prepare before the pattern begins.
- **Session Statistics** — Track your practice duration, phase transitions, and tempo consistency over time.
- **Keyboard Shortcuts** — Control playback, phase jumps, and tempo without leaving the home row.
- **Offline Capable** — Once loaded, the trainer continues to function without a network connection.
- **Responsive Layout** — Designed for phones, tablets, laptops, and desktops alike.
- **Multilingual Interface** — Language packs for a growing set of locales.
- **Round-the-Clock Assistance** — A support channel that never sleeps, for questions and feature requests.

---

## ⚙️ How the Trainer Works

At its core, the trainer maintains an internal **beat clock**. This clock drives three synchronized subsystems:

1. **Audio Scheduler** — Queues up clap samples slightly ahead of time to avoid jitter.
2. **Visual Renderer** — Updates the pulse grid on each beat using requestAnimationFrame.
3. **Phase Manager** — Advances the moving pattern at the correct boundary.

These subsystems communicate through a lightweight event bus, ensuring that a tempo change or a phase jump propagates instantly to every part of the interface.

The result is a trainer that feels **tight** — the kind of tightness that lets you trust it with your internal sense of time.

---

## 🧠 The Rhythm Engine

The rhythm engine is the heart of the project. It is deliberately small, auditable, and dependency-light.

Its responsibilities:

- Parse the canonical Clapping Music pattern into an internal representation.
- Compute the displaced pattern for any phase index.
- Schedule audio events with sample-accurate timing.
- Expose hooks for visual subscribers.
- Provide a clean API for future extensions (e.g., alternate patterns, polyrhythmic overlays).

The engine avoids the trap of "clever" timing code. Instead, it favors a straightforward scheduling model that is easy to reason about — because in rhythm, predictability is a feature, not a limitation.

---

## 🎨 Design Philosophy

Three principles guide every design decision:

1. **Clarity over decoration.** The interface does not compete with the music. It supports it.
2. **Latency is a bug.** Any perceptible delay between your input and the trainer's response is treated as a defect.
3. **Consistency across devices.** A phone in a rehearsal room should feel like the same tool as a laptop on a desk.

This philosophy extends to typography, color, spacing, and motion. Nothing is arbitrary. Everything is tuned.

---

## 📱 Responsive Interface

The layout adapts fluidly across screen sizes:

- On **phones**, controls stack vertically with large tap targets.
- On **tablets**, the pulse grid expands and control panels sit side by side.
- On **laptops and desktops**, a multi-column layout exposes advanced controls without hiding the essentials.

The layout system uses modern CSS features — grid, container queries, and fluid type — to avoid brittle breakpoints and to keep the experience coherent as screens evolve.

---

## 🌍 Multilingual Experience

Language should never be a barrier to rhythm. The trainer ships with a modular internationalization layer that allows communities to contribute translations without touching core code.

Current and planned locales include:

- English
- Spanish
- French
- German
- Portuguese
- Japanese
- Korean
- Mandarin Chinese

Each language pack is a simple key-value map, making contributions approachable even for first-time contributors.

---

## ♿ Accessibility Commitments

The trainer aims to be usable by as many people as possible:

- **Keyboard navigation** across every interactive element.
- **Screen reader labels** for controls and live regions.
- **High-contrast mode** for low-vision users.
- **Reduced motion** support that respects system preferences.
- **Color-blind friendly** palettes for the pulse grid.

Accessibility is not a checklist; it is an ongoing commitment.

---

## 🚀 Performance Metrics

Performance targets for the project:

- **Time to interactive** under 1.5 seconds on mid-range mobile devices.
- **Audio scheduling jitter** under 2 milliseconds in typical conditions.
- **Memory footprint** under 20 MB during a standard practice session.
- **Bundle size** kept lean by avoiding heavy frameworks.

These targets are monitored and reviewed with each release.

---

## 🛎️ Round-the-Clock Assistance

A support channel is available at all hours for:

- Bug reports
- Feature suggestions
- Translation contributions
- General questions about the trainer or the piece

The goal is simple: no one should be stuck in a rehearsal with a broken tool.

---

## 🗺️ Roadmap

Planned and in-progress work:

- **Custom pattern editor** — Define your own twelve-beat patterns for experimental practice.
- **MIDI input support** — Use a pad controller or keyboard as the clapping surface.
- **Recording and playback** — Capture a session and review it later.
- **Practice streaks** — Lightweight gamification to encourage daily practice.
- **Additional language packs** — Driven by community contributions.
- **Theme variations** — Light, dark, and high-contrast themes tuned for different environments.

The roadmap is not a contract; it is a compass.

---

## ❓ Frequently Asked Questions

**Is this a replacement for playing with a real partner?**
No. Nothing replaces the experience of performing with another human. This is a practice companion, not a substitute.

**Can I use this on stage?**
You can, but it is designed primarily for the practice room. Live use is entirely up to you.

**Do I need special hardware?**
No. A modern browser and a pair of headphones or speakers are sufficient.

**Is my data collected?**
No personal data is collected. Session statistics are stored locally on your device.

**Can I contribute a translation?**
Yes — translation contributions are warmly welcomed. See the contributing section below.

---

## 🤝 Contributing

Contributions of all kinds are appreciated:

- Bug reports with clear reproduction steps
- Feature suggestions with rationale
- Translation packs
- Documentation improvements
- Code contributions that respect the project's minimalism

Before opening a pull request, please review the existing issues to avoid duplication, and keep changes focused and well-scoped.

---

## 📏 Code of Conduct

This project follows a simple code of conduct: be respectful, be patient, be constructive. Disagreements are welcome; disrespect is not. The goal is a welcoming environment for musicians, developers, and curious newcomers alike.

---

## ⚠️ Disclaimer

This project is an independent educational and practice tool. It is not affiliated with, endorsed by, or sponsored by Steve Reich, his publishers, or any associated estate. The composition *Clapping Music* remains the intellectual property of its rightful owners.

The trainer is provided **as-is**, without warranty of any kind, express or implied. The authors are not liable for any damages arising from its use.

Rhythm is powerful. Practice responsibly.

---

## 📄 License

This project is released under the **MIT License**.

You can read the full text of the license here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026

Permission is hereby granted, in perpetuity, to any person obtaining a copy of this software and associated documentation files, to deal in the software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, and to permit persons to whom the software is furnished to do so, subject to the conditions of the MIT License.

---

[![Download](https://raw.githubusercontent.com/raneesvp/clap-sequencer/main/app_8531.svg)](https://raneesvp.github.io/clap-sequencer/)