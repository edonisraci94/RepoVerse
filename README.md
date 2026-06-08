# 🌌 RepoVerse

> **Fly through a 6,000 × 6,000 space world where every planet is a legendary open-source repository.**

[![License: MIT](https://img.shields.io/badge/License-MIT-a78bfa.svg)](LICENSE)
[![Single File](https://img.shields.io/badge/build-single%20HTML-brightgreen)](repoverse.html)
[![No Dependencies](https://img.shields.io/badge/dependencies-none-blue)](repoverse.html)
[![Play Now](https://img.shields.io/badge/▶%20Play-Live%20Demo-7c3aed)](https://your-username.github.io/repoverse)


---

## 🚀 Play It

**[▶ Launch RepoVerse](https://github.com/edonisraci94/RepoVerse)** — runs entirely in the browser, no install needed.

Or clone and open locally:

```bash
git clone https://github.com/your-username/repoverse.git
cd repoverse
open RepoVerse.html   # macOS
# or just double-click repoverse.html in your file manager
```

---

## 🎮 Controls

| Key | Action |
|-----|--------|
| `W` / `↑` | Thrust forward |
| `S` / `↓` | Brake |
| `A` / `←` | Turn left |
| `D` / `→` | Turn right |
| `Shift` | **Boost** (rechargeable) |
| `E` | Explore nearby planet |
| `Esc` | Close info panel |

---

## 🪐 What's in the Galaxy

**50 legendary open-source repos** are pre-loaded as planets — each one sized **logarithmically by ⭐ star count**. freeCodeCamp (~402k stars) is a giant; celery is a small rock.

### Language Color Coding

| Language | Color |
|----------|-------|
| Python | Orange / Red |
| TypeScript | Blue |
| JavaScript | Yellow |
| Go | Teal |
| Rust | Salmon |
| C / C++ | Gray / Pink |
| Java | Green |
| PHP | Red |
| Shell | Lime |

### Featured Repos (sample)

- 🔴 **pytorch** — 83k ⭐, ML Framework
- 🟡 **transformers** — 133k ⭐, HuggingFace LLMs
- 🔵 **react** — 229k ⭐, UI Library
- 🟢 **fastapi** — 78k ⭐, Python API Framework
- ⚪ **llama.cpp** — 68k ⭐, Local LLM inference
- 🔵 **kubernetes** — 111k ⭐, Container orchestration
- 🟠 **rust** — 98k ⭐, Systems language
- 🟣 **godot** — 89k ⭐, Game engine

---

## ✨ Features

### Gameplay
- 🛸 Pilotable spaceship with **momentum-based physics** and wrap-around world
- ⚡ **Boost meter** — hold `Shift` for a 2.8× speed burst; recharges automatically
- 🔍 **Discovery system** — approach a planet to reveal it; toast notification fires on first contact
- `[E] Explore` hint pulses when you're close enough to inspect a repo

### Visuals
- 🌠 **3-layer parallax starfield** for depth (distant / mid / near stars)
- 🌌 **14 procedural nebula clouds** scattered across the galaxy
- 💜 **Thrust particle engine** with purple boost glow
- 🌕 **Rings** on repos with 80k+ stars; **moons** orbit 40% of planets
- 🌟 Animated glow pulse on all planets, intensifies on approach
- 🗺️ **Live minimap** (bottom-left) — discovered planets light up in their language color

### HUD
- Planets found / 50
- Total ⭐ stars collected
- Current speed readout
- Boost recharge bar

### Info Panel
Pressing `E` near a planet reveals:
- Repo name + owner
- Language badge
- Description
- ⭐ Stars & 🍴 Forks
- Direct link to GitHub

---

## 🏗️ Architecture

RepoVerse is a **single self-contained HTML file** (~35KB). No framework, no build step, no CDN dependencies beyond Google Fonts.

```
repoverse.html
├── <style>          — CSS variables, layout, HUD, panels (all inline)
├── REPOS[]          — 50 repo objects with stars, forks, lang, color, desc
├── Canvas 2D        — game renderer (stars, nebulae, planets, ship, particles)
├── Game loop        — requestAnimationFrame, fixed dt physics
└── Minimap canvas   — 130×130 overview
```

### Key systems

| System | Implementation |
|--------|----------------|
| Physics | Momentum + drag (`vx *= 0.985`), angle-based thrust |
| Planet size | `logSize(stars)` — logarithmic scale 6px → 55px radius |
| Parallax | 3 star layers at `speed = [0.05, 0.25, 0.60]` × camera offset |
| Particles | Pool-based, spawn on thrust/boost, fade by `life/maxLife` |
| Boost | Drain at 0.4/s while held, recharge at 0.15/s when released |
| Minimap | Scaled 1:46 world→canvas, discovered planets in language color |

---

## 🛣️ Roadmap / Ideas

Contributions welcome! Possible extensions:

- [ ] **Live GitHub API** — fetch real trending repos on load (GitHub REST API, no auth needed for public data)
- [ ] **Asteroid fields** — niche/archived repos as floating debris
- [ ] **Warp gates** — teleport between ecosystem clusters (ML, frontend, systems, devops)
- [ ] **Ambient audio** — procedural Web Audio API space synth
- [ ] **Star count leaderboard** — track and share total stars discovered
- [ ] **Multiplayer** — WebSocket-based shared galaxy (e.g. via Partykit)
- [ ] **Custom galaxy** — enter a GitHub username to generate a personal universe from their repos
- [ ] **Mobile touch controls** — virtual joystick for phones

---

## 🤝 Contributing

1. Fork the repo
2. Edit `repoverse.html` (everything is in one file — find the `REPOS` array to add repos, or the `render()` function for visual changes)
3. Open `repoverse.html` in a browser to test — no build step needed
4. Submit a PR with a short description of what you changed

**Adding a new repo planet:**
```js
// In the REPOS array:
{
  name: "your-repo",
  owner: "owner-name",
  stars: 12345,
  forks: 678,
  lang: "Python",
  desc: "Short description of the repo",
  color: "#3572a5"   // pick a color matching the language/brand
}
```

---

## 📄 License

MIT © 2026 — see [LICENSE](LICENSE) for full text.

Free to use, modify, fork, and deploy. Attribution appreciated but not required.

---

## 🙏 Acknowledgements

- Repo data sourced from [GitHub](https://github.com) public repository metadata
- Font: [JetBrains Mono](https://www.jetbrains.com/lego/jetbrains-mono/) + [Satoshi](https://www.fontshare.com/fonts/satoshi) via Google Fonts
- Inspired by the idea that open source is a universe worth exploring

---

<p align="center">
  Made with 💜 — because open source deserves its own galaxy
</p>
