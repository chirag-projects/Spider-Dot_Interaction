# Spider-Dot Interaction
**ArachneCanvas** is a high-performance, interactive website template featuring a dynamic particle-web background and a Spider-Man themed UI. This project uses a custom JavaScript engine to create a "connect-the-dots" effect that responds to mouse movement in real-time.

---

## The Mathematics Used for Project

The core of the "spiderweb" effect in `spider.js` relies on **Euclidean Distance** to determine when to draw a line between a particle (dot) and the user's cursor.

### 1. Particle Generation
Particles are placed randomly across the canvas using a uniform distribution:
* **X-coordinate**: $x = \lfloor \text{random}() \cdot \text{width} \rfloor$
* **Y-coordinate**: $y = \lfloor \text{random}() \cdot \text{height} \rfloor$
* **Size**: Each dot is assigned a random size between $5$ and $8$ pixels.

### 2. Distance Calculation
For every frame where the mouse moves, the script calculates the distance $d$ between the cursor $(x_m, y_m)$ and each particle $(x_p, y_p)$ using the **Pythagorean Theorem**:

$$d = \sqrt{(x_m - x_p)^2 + (y_m - y_p)^2}$$

### 3. Conditional Rendering
The "web" is only spun if the distance falls within a specific radius (threshold):
* **Threshold**: $300$ pixels.
* **Logic**: If $d < 300$, a line is drawn from $(x_p, y_p)$ to $(x_m, y_m)$ using the particle's specific color.

---

## Preview
See the interactive animation in action below:

<p align="center">
  <video src="./dio.mp4" width="600" autoplay loop muted playsinline>
    Your browser does not support the video tag.
  </video>
</p>

## To Run locally

1.  **Clone the Repo**: Download the source files.
2.  **Run a Server**: Open the project using a local server (like VS Code "Live Server") to ensure the HTML and JS load correctly.
3.  **Interact**: Move your mouse over the main banner area to trigger the web-spinning effect.

---

## Styling Features
* **Inverted Graphics**: The logos are automatically inverted via CSS `filter: invert();` to create a sleek white-on-black aesthetic.
* **Pulse Animation**: The central spider logo features a smooth `zoom-in-zoom-out` keyframe animation that loops every $1$s.
* **Gradient Text**: The "Welcome Animation" header uses a linear gradient (45deg, #0c49f1, #ff0101) clipped to the text to represent Spider-Man's iconic colors.

---
*© This site is intended for animation project purposes.*
