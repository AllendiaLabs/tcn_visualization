# Temporal Convolutional Network (TCN) Visualizer

An interactive, self-contained visualization tool for exploring the receptive field of the Temporal Convolutional Network (TCN) architecture.  
The app is written in vanilla HTML5/JavaScript, requires **no build step or external dependencies**, and is fully documented using JSDoc-style comments compatible with **Doxygen**.

---

## ✨ Features

* Real-time rendering of the TCN computation graph on an HTML5 `<canvas>` element.
* Adjustable **kernel size k**, **dilation growth factor d**, **number of blocks L**, and **delay samples** via sleek slider controls.
* Automatic calculation and display of the **receptive field** for the last output sample.
* Responsive layout that looks great on desktop or mobile.
* Deterministic, dependency-free code that runs in any modern browser.

---

## 🚀 Quick Start

1. **Clone or download** this repository.
2. Open `index.html` directly in a modern web browser *or* serve the directory locally and navigate to `http://localhost:8000`:

   ```bash
   # From the project root
   python3 -m http.server 8000
   ```

   A local server is recommended if your browser blocks local `file://` script execution.
3. Tweak the sliders and watch the visualization update in real time!

> **Tip** – Press <kbd>Ctrl/Cmd</kbd> + <kbd>R</kbd> to reset your browser's PRNG if you want to see a different random sampling for fractional dilations.

---

## 🎛️ Control Reference

| Control | Symbol | Range | Description |
|---------|--------|-------|-------------|
| **Kernel Size** | *k* | 2 – 9 | Number of taps in each 1-D convolution filter. |
| **Dilation Growth** | *d* | 1.0 – 4.0 (0.1 step) | Base of the exponential that determines dilation per block (*d*<sup>layer</sup>). Fractional values are handled stochastically. |
| **Blocks** | *L* | 1 – 10 | Number of causal convolutional blocks stacked vertically. |
| **Delay Samples** | *–* | 1 – 512 | Spacing between successive taps in **the last layer only**. Kept in sync with *d* and *L*. |

The **receptive field** shown below the sliders reports how many input samples influence the last output sample at *t = 0*.

---

## 🛠️ Development Guide

### Project Structure

```text
.
├── index.html   # Single-page application (HTML + CSS + JS)
└── README.md    # You are here
```

### Code Style & Documentation

* JavaScript is entirely embedded inside `index.html` for portability.
* All functions are documented with **JSDoc** tags that are readily parsed by **Doxygen**:

  ```bash
  doxygen -g            # Generate a default Doxyfile (first time only)
  # Edit Doxyfile: set FILE_PATTERNS = *.html and EXTRACT_ALL = YES
  doxygen               # Emit HTML documentation to ./html/
  ```

### Contributing

Feel free to open issues or pull requests for

* enhanced visual styling,
* performance optimizations,
* bug fixes, or
* additional explanatory material.

All contributions should follow the existing JSDoc style so that generated docs remain comprehensive.

---

## 🌐 Deployment

Because the project is a static site, it can be hosted easily on **GitHub Pages**, **Netlify**, or any static file server.

1. Push the repository to GitHub.
2. Enable *GitHub Pages* in the repository settings (branch: `main`, folder: `/`).
3. Your live demo will be available at `https://<username>.github.io/tcn_visualization`.

---

*Happy experimenting 👩‍🔬 👨‍🔬!*