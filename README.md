# 🖼️ Pixel Research Suite

A collection of interactive web tools for **pixel‑level image analysis**, **reconstruction**, and **steganography**.  
Built with vanilla HTML, CSS, and JavaScript – all processing happens client‑side. No data is sent to any server.

## 📦 What’s Inside

| Page | Purpose |
|------|---------|
| **🏠 Home** (`index.html`) | Landing page – upload an image, see its 28×28 pixelated grid, compare file sizes, and download the grid as a PNG. |
| **🧪 Option 1 – Hidden Detail** | Embed **variance** into the LSBs of a 28×28 grid. Reconstruct the grid as **pixelated** or **smooth** (bicubic + sharpening). |
| **🔐 Option 2 – Steganography** | Hide a **secret message** in the LSBs of a 28×28 grid. Embed and extract messages using a simple LSB technique. |
| **📦 Option 3 – Export / Reconstruct** | Export the 28×28 grid **averages** and **all original block pixels** as JSON. Load the JSON to reconstruct the grid in **pixelated** or **scrambled** mode. |

---

## 🚀 Features

### ✅ Home
- Upload any image (file or clipboard paste).
- Crop to square automatically.
- Generate a 28×28 pixelated grid.
- View original file size and grid file size (in B / KB / MB).
- Download the grid as a PNG (scalable via a user‑defined factor).
- Hover over any grid cell to see block info (sum, average, pixel count, and a mini preview).

### ✅ Option 1 – Hidden Detail
- Pixelate an image into a 28×28 grid.
- Store **variance** (standard deviation) in the LSBs of the grid – hidden in the pixel values.
- Reconstruct in two modes:
  - **Pixelated** – nearest‑neighbour upscaling.
  - **Smooth** – bicubic interpolation + unsharp mask for crisp, clear output.
- Adjust sharpness (0–100) for smooth mode.
- Upload a previously downloaded pixelated PNG and divide it back to 28×28 (fixed 15× divisor).
- Download the reconstructed image at any scale (user‑defined).
- Hover over any grid cell to see **block info** (sum, average, variance, pixel count, and a mini preview).
- Click any grid cell to see the **full pixel list** for that block.

### ✅ Option 2 – Steganography
- Embed a secret message into the LSBs of the 28×28 grid.
- Extract the message from a 28×28 PNG (auto‑descales 15× images).
- ASCII‑only text up to **293 characters** (using a 2‑byte length header).
- Multi‑line text input with a live character counter.
- Download the modified grid as a PNG (15× scaled).

### ✅ Option 3 – Export / Reconstruct
- **Export JSON** containing:
  - `grid` – 28×28 average RGBA values.
  - `blocks` – the **full RGBA pixel list** for every block (preserves all original image data).
- **Load JSON** to reconstruct the grid and view the **scrambled** block data (each block’s pixels are arranged as a mini‑grid).
- Switch between **Pixelated** (average upscale) and **Scrambled** (raw block pixels) reconstruction.
