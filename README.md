# 911 Turbo — Walk Around It

> **A cinematic WebGL experience built around the iconic Porsche 911 silhouette.**

A minimal, immersive 3D showcase that lets you **scroll around a classic 911 Turbo**, explore different angles, and repaint the car in real time.

Built as a single-page web experience with a focus on **visual storytelling, smooth motion, responsive design, and minimal UI**.

---

## ✦ Experience

The page turns scrolling into a camera journey around the car.

Instead of traditional navigation, the experience unfolds through a sequence of visual moments:

* **911** — an opening hero composition
* **Roof to tail** — a side/rear perspective
* **Rear engine** — a closer look at the classic layout
* **Round headlights** — the iconic front silhouette
* **Pick your paint** — interactive color customization

The interface stays intentionally quiet so the 3D model remains the focus.

---

## ✨ Features

* 🏎️ **Interactive 3D Porsche 911 Turbo**
* 🎥 **Scroll-driven cinematic camera movement**
* 🔄 **Animated wheel rotation while scrolling**
* 🎨 **Real-time paint customization**
* 💡 **Studio-style environment lighting**
* 🌑 **Dynamic background that follows the selected paint**
* 📱 **Responsive desktop and mobile layout**
* ♿ **`prefers-reduced-motion` support**
* ⚡ **WebGL hardware acceleration**
* 🧊 **Meshopt-compressed glTF rendering**
* 🖥️ **Automatic viewport and camera adjustment**
* 🎯 **Minimal glassmorphism color-control dock**

---

## 🛠️ Built With

| Technology          | Purpose                            |
| ------------------- | ---------------------------------- |
| **HTML5**           | Page structure                     |
| **CSS3**            | Layout, typography & responsive UI |
| **JavaScript**      | Interaction & animation            |
| **Three.js**        | 3D rendering                       |
| **WebGL**           | Hardware-accelerated graphics      |
| **GLTFLoader**      | 3D model loading                   |
| **Meshopt Decoder** | Geometry decompression             |
| **Google Fonts**    | Bricolage Grotesque typography     |

The implementation uses Three.js `r128`, GLTFLoader, and the Meshopt decoder.

---

## 🎨 Paint Collection

The experience includes seven selectable colors:

| Color         | Hex       |
| ------------- | --------- |
| Guards Red    | `#c8102e` |
| Miami Blue    | `#3fb4dc` |
| Racing Yellow | `#f2c200` |
| Python Green  | `#2f6b46` |
| Agate Grey    | `#6d7074` |
| Jet Black     | `#111114` |
| Chalk         | `#d8d4cb` |

Selecting a color smoothly transitions the vehicle's paint and the surrounding environment.

---

## 🎬 How It Works

### Scroll → Camera

The page maps the document scroll position to a normalized animation progress value.

That progress moves the camera through predefined positions around the vehicle, creating the feeling of physically walking around it.

```text
Scroll
  ↓
Document Progress
  ↓
Camera Path Interpolation
  ↓
Look-at Target Interpolation
  ↓
3D Scene
```

The camera path contains multiple viewpoints around the vehicle and uses smooth interpolation between them.

### Scroll → Wheels

Scrolling also produces a small rotational effect on the wheels, giving the model additional physical movement rather than simply moving the camera.

### Paint → Environment

The selected paint color is interpolated smoothly and used to influence the surrounding background, creating a subtle visual relationship between the car and its environment.

---

## 🖥️ Responsive Design

The experience adapts its camera configuration based on viewport size.

On smaller screens:

* Camera FOV changes
* Desktop camera offset is removed
* Paint controls become more compact
* The vertical scroll hint disappears
* The color names are hidden to preserve space

The layout also accounts for mobile safe-area insets.

---

## ♿ Accessibility & Motion

The project checks the user's system preference for reduced motion:

```js
matchMedia("(prefers-reduced-motion: reduce)")
```

When reduced motion is enabled, camera interpolation becomes immediate rather than gradually animated.

A WebGL fallback message is also provided when the browser cannot initialize the renderer.

---

## 🚀 Run Locally

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Because the project loads WebGL assets and external dependencies, running it through a local HTTP server is recommended.

### Python

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

### VS Code

Alternatively, open the project with **Live Server** and launch `index.html`.

---

## 📁 Project Structure

```text
.
├── index.html
└── README.md
```

The current implementation keeps the experience intentionally lightweight by placing the HTML, CSS, JavaScript, and embedded glTF scene inside the page.

---

## 🧩 3D Model

The Porsche 911 model included in this experience is:

**FREE 1975 Porsche 911 (930) Turbo**

Created by **Lionsharp Studios**.

The embedded asset identifies the model as licensed under **CC BY 4.0** and provides the original Sketchfab source attribution.

### Attribution

> 3D model: **Lionsharp Studios**
> Model: **FREE 1975 Porsche 911 (930) Turbo**
> License: **CC BY 4.0**

Please retain the appropriate attribution when redistributing the 3D asset.

---

## 🎯 Design Direction

The visual language intentionally combines:

**Minimalism × Automotive Design × Editorial Typography × Interactive 3D**

The UI stays mostly invisible while the vehicle becomes the primary visual element.

The typography uses **Bricolage Grotesque**, while the interface uses a dark studio aesthetic with translucent controls and subtle blur effects.

---

## 💭 Why I Built This

I wanted to experiment with a different way of presenting a 3D object on the web.

Rather than placing a model inside a conventional product viewer with buttons and menus, the goal was to make the **scroll itself become the interaction**.

Every scroll position becomes part of the presentation.

> **Don't just look at the car.
> Walk around it.**

---

## 🔮 Possible Improvements

Ideas for future iterations:

* [ ] Mouse / touch drag camera control
* [ ] More vehicle paint options
* [ ] Interior exploration
* [ ] Engine-detail mode
* [ ] Cinematic transition presets
* [ ] Sound design
* [ ] Fullscreen presentation mode
* [ ] WebGPU rendering
* [ ] Performance presets for low-end devices

---

## 📜 Credits

**Concept & Web Experience**
Your Name

**3D Model**
Lionsharp Studios

**3D Technology**
Three.js

---

<p align="center">
  Built with curiosity, WebGL & a love for beautiful machines.
</p>
