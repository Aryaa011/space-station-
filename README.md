# 🚀 Space Station Explorer

An immersive, browser-based 3D space station experience built entirely in a single HTML file — no frameworks, no build tools, no server required. Just open and explore.


live demo: https://spacestation0.netlify.app

---

## ✨ Features

### 🌌 Exterior
- Animated 3D space station orbiting in a star field
- Auto-rotating with drag-to-orbit and scroll/pinch to zoom
- Cinematic dark metallic PBR materials with correct normal maps

### 🏠 Interior Exploration
- First-person walkthrough of a detailed sci-fi station interior
- Full WASD + mouse-look controls on desktop
- Virtual joystick + swipe-to-look on mobile
- 100+ animated nodes — drones, fans, panels all moving

### 🎵 Ambient Sound
- Procedurally synthesised space music — no audio files
- Crystal bell arpeggios in D major pentatonic on the exterior
- C Lydian ascending melody inside the station
- Airlock whoosh sound effect on entry
- Algorithmic 6-second reverb tail on all sounds
- Crossfades smoothly between exterior and interior

### 💡 Interactive Hotspots
- 4 glowing pulsing markers at key locations inside
- Click any to reveal an info panel with module name and lore
- ⚡ Energy Core · 🛸 Command Deck · 🌿 Life Support · 🚀 Docking Bay

### 🌫️ Atmosphere
- 600 floating dust particles drifting through the interior
- Pulsing opacity for a living, breathing feel

### 📱 Mobile Ready
- Fully responsive layout for all screen sizes
- Touch joystick (left thumb) + swipe look (right thumb)
- Info panels slide from bottom on mobile
- Pixel ratio capped for smooth mobile performance

---

## 🗂️ File Structure

```
space_station_explorer.html   ← The entire project (single file, ~19MB)
README.md
```

## 🎮 Controls

### Desktop
| Action | Control |
|---|---|
| Look around | Click screen to lock cursor, then move mouse |
| Move forward / back | W / S |
| Strafe left / right | A / D |
| Move up | Space |
| Move down | Q or Shift |
| Unlock cursor | Escape |
| Orbit exterior | Click + drag |
| Zoom exterior | Scroll wheel |
| Toggle sound | 🔊 button (bottom right) |

### Mobile
| Action | Control |
|---|---|
| Move | Left thumb joystick |
| Look | Drag right side of screen |
| Move up / down | Space / Q (if keyboard available) |
| Orbit exterior | Single finger drag |
| Zoom exterior | Pinch |
| Toggle sound | 🔊 button |

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| **Three.js r128** | 3D rendering engine |
| **GLTFLoader** | GLB model loading |
| **DRACOLoader** | Draco geometry decompression (interior model) |
| **Web Audio API** | Procedural music and sound effects |
| **Vanilla JS** | All game logic, controls, UI |
| **CSS3** | UI, animations, responsive layout |

No npm. No webpack. No React. Pure browser APIs.

---

## 📦 3D Models

| Model | Source | Role |
|---|---|---|
| Space Station 3 | Sketchfab — re1monsen | Exterior view with solar panel rotation animation |
| Space Station Scene WIP 7 | Sketchfab — 3DHaupt | Interior walkthrough with 100+ animated nodes |

### Compression applied
- **Exterior:** Original geometry + textures resized to 512px max, JPEGs for base color, PNGs preserved for normal/occlusion maps. 22MB → 9.4MB
- **Interior:** Draco mesh compression + texture optimisation. 6.4MB → 4.5MB
- Both embedded as base64 in the HTML

---

## 🏗️ Architecture

```
HTML File
├── CSS (responsive, mobile-first)
├── Loading Screen (progress bar)
├── Exterior Scene (Three.js)
│   ├── GLB model (base64 embedded)
│   ├── Star field (2500 procedural points)
│   ├── PBR lighting (directional + hemisphere)
│   └── Orbit camera with auto-rotate
├── Interior Scene (Three.js)
│   ├── GLB model (base64 + Draco)
│   ├── FPS camera (WASD + mouse look)
│   ├── Floating particles (600 points)
│   ├── Hotspot markers (4 interactive)
│   └── Point lighting (teal + purple)
├── Audio Engine (Web Audio API)
│   ├── Algorithmic reverb (impulse response)
│   ├── Exterior: Crystal bell arpeggiator
│   ├── Interior: Ascending melodic phrases
│   ├── Airlock SFX (noise sweep)
│   └── Master gain with crossfade
└── Mobile Controls
    ├── Virtual joystick (touch)
    └── Right-side look zone (touch)
```

---

## 🔧 Customisation

### Change movement speed
```js
// In the script, find:
SPEED = diag * 0.0008;
// Increase for faster, decrease for slower
```

### Change exterior orbit speed
```js
// In the render loop:
if(autoOrb) extYaw += dt * 0.07;
// Change 0.07 — higher = faster spin
```

### Add a hotspot
```js
// In the HOTSPOTS array:
{
  pos: new THREE.Vector3(x, y, z),
  name: 'Module Name',
  icon: '🔬',
  desc: 'Description text here.',
  color: '#ff6600'
}
```

### Mute by default
```js
// Change:
let isMuted = false;
// To:
let isMuted = true;
```

---

## 🌐 Browser Support

| Browser | Status |
|---|---|
| Chrome 90+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Safari 15+ | ✅ Full support |
| Mobile Chrome | ✅ Full support |
| Mobile Safari | ✅ Full support |

---

## 📄 License

Models used under their respective Sketchfab licenses. All code written for this project is MIT licensed.

---

## 👨‍💻 Built With

- Three.js for 3D rendering
- Web Audio API for procedural music
- Pure HTML/CSS/JS — no build step, no dependencies

> *"One file. Two worlds. Infinite space."*
