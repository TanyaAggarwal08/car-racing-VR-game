# 🏎️ SYNTHWAVE RACER VR

> A retro 80s-style WebVR car racing game built with [A-Frame](https://aframe.io). Race down neon highways under glowing sunsets — steered entirely by your gaze and head movements.

![Retro Synthwave Racing](https://img.shields.io/badge/style-SYNTHWAVE-ff00aa?style=for-the-badge)
![Built With A-Frame](https://img.shields.io/badge/A--Frame-1.4.0-00ffff?style=for-the-badge)
![VR Ready](https://img.shields.io/badge/VR-CARDBOARD%20READY-ffff00?style=for-the-badge)

---

## 🎮 Play the Game

Open `index.html` in any modern browser. **No server required.**

```
index.html   →   setup.html   →   game.html
```

---

## ✅ Feature Checklist

| Feature | Status |
|---|---|
| Flash screen with credentials | ✅ |
| Setup options (level, music, controls) | ✅ |
| At least 2 levels | ✅ Level 1: City Sunset · Level 2: Neon Night |
| Background music (mutable) | ✅ Synthwave beat via Web Audio API |
| Sound effects | ✅ Crash, overtake, level-up, engine |
| Always-visible scoreboard | ✅ HUD with score, time, level, lives, speed |
| Gaze-based head control | ✅ Camera yaw for steering |
| Head-tilt control | ✅ DeviceOrientation gamma axis |
| Stereoscopic mobile VR | ✅ A-Frame cardboard mode |
| Own objects with textures | ✅ All textures procedurally generated |
| Collision detection | ✅ AABB per-frame check |
| No blood / no violence | ✅ |
| Manual | ✅ `manual.html` + this `README.md` |

---

## 🚀 Installation & Running

### Browser (Recommended)
1. Download / clone this repository
2. Open `index.html` in Chrome, Firefox, Edge, or Safari
3. No build step, no server, no dependencies to install

### Local Server (Optional — for iOS VR support)
```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .
```
Then visit `http://localhost:8080` in your browser.

---

## 🕹️ Controls

| Action | Desktop | Mobile VR |
|---|---|---|
| Steer Left | Look left / `←` / `A` | Tilt phone left |
| Steer Right | Look right / `→` / `D` | Tilt phone right |
| Pause | `P` or `ESC` | — |
| Toggle Music | `M` | — |
| Enter VR | Click goggles icon | Tap goggles icon |

> **Head-look steering:** Turn your head (or mouse-drag) more than 14° left or right to steer. Arrows in the HUD confirm your direction.

---

## 🌅 Levels

### Level 1 — City Sunset
- Palm tree-lined highway under a glowing sunset
- 4 traffic opponents at moderate speed
- 90-second timer
- Asphalt road texture with lane dashes

### Level 2 — Neon Night
- Glowing purple grid highway under a starfield
- 7 traffic opponents at high speed
- Neon fence barriers & holographic signs
- Score carries over from Level 1

---

## 🏆 Scoring

| Event | Points |
|---|---|
| Time alive × speed | +variable |
| Overtake a traffic car | +80 |
| Collision | −200 & −1 life |
| Lives | 3 total |

---

## 📱 Mobile VR (Google Cardboard)

1. Open the game in **Chrome on Android**
2. Start the game normally
3. Tap the **VR goggles icon** (bottom-right of screen)
4. Insert phone into a **Google Cardboard** headset
5. **Tilt your head left/right** to steer

> **iOS Note:** Safari requires HTTPS for DeviceOrientation events. Use a local server (see above) or GitHub Pages.

---

## 🔧 Technical Details

| Technology | Details |
|---|---|
| VR Engine | A-Frame 1.4.0 |
| VR Mode | WebXR / Google Cardboard |
| Textures | Procedural Canvas 2D API |
| Audio | Web Audio API (oscillator synthesis) |
| Collision | AABB (Axis-Aligned Bounding Box) |
| Road scrolling | Entity z-translation with circular wrapping |

### File Structure

```
.
├── index.html        # Flash screen / splash
├── setup.html        # Game setup options
├── game.html         # Main A-Frame VR game
├── manual.html       # In-game manual page
└── README.md         # This file
```

---

## 🎵 Audio

All audio is synthesized in real-time using the **Web Audio API** — no external files:

- **Engine hum** — sawtooth oscillator with LFO tremolo, frequency tracks speed
- **Crash sound** — filtered white noise burst
- **Overtake whoosh** — sine wave with rising frequency sweep
- **Level-up jingle** — ascending square wave chord progression
- **Synthwave background music** — procedural drum machine (kick, snare, hihat) + bass + synth pads at 120 BPM

> Music can be toggled in Setup or with `M` key during gameplay.



*No blood. No violence. Just pure neon speed.* 🌅
