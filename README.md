# SignalSketch

**Sketch your floor plan, drop in access points, and see Wi-Fi, 4G and 5G coverage as a heatmap.**

SignalSketch is a single-page coverage planner that runs entirely in your browser.
There is nothing to install, no account, and no server: your floor plans never leave your computer.

## ▶ Run it

| Option | What to do |
|---|---|
| **Online (no download)** | Open **https://beleonattila.github.io/SignalSketch/** |
| **Offline / portable** | Download [**SignalSketch.zip**](https://github.com/beleonattila/SignalSketch/releases/latest/download/SignalSketch.zip), unzip it anywhere (Desktop, Documents, a USB stick), and double-click `SignalSketch.html`. |

Both work on a locked-down company laptop: no admin rights, no installer, no runtime.
Any current browser does the job (Edge, Chrome, Firefox).
The offline copy works without internet too, including PDF import, as long as the `lib` folder stays next to `SignalSketch.html`.

## Quick start

1. **Open plan…** and pick a PNG, JPG or PDF of your floor plan. Use **Rotate** and **Crop plan** if needed.
   No plan at hand? Try **Demo** or **Industrial demo**.
2. **Set scale (C):** click two points of a known distance (for example a scale bar) and enter the length in metres.
3. **Draw wall (W):** trace the walls and pick a material for each (gypsum, brick, concrete, steel panel…).
   **Equipment zone (Z)** marks machinery, racks or tanks that absorb signal.
4. **Place marker (M):** drop Wi-Fi 2.4 GHz, Wi-Fi 5 GHz, 4G LTE or 5G NR transmitters. Drag them and the heatmap updates live.
   To model your real hardware, open **My devices…** and define a device with its own frequency, Tx power, antenna gain and cable loss; it then appears in the marker selector.
5. Read the **Area at or above target level** figure, or let **Suggest AP placement** propose a layout.
6. **Save project** to keep your work as a `.json` file, and **Export PNG** for reports.

Keys: `V` select · `W` wall · `Z` zone · `M` marker · `C` calibrate · `P` measurement ·
`Space`+drag or middle-drag pans · wheel zooms · `Del` deletes · `Esc` ends · `Ctrl+Z` / `Ctrl+Y` undo / redo · `Shift` locks the wall angle · `B` or the ◀ button hides the sidebar.

## Features

- **Floor plans:** PNG, JPG and PDF import, rotate, crop and two-point scale calibration.
- **Walls:** hand-drawn, with editable per-material losses. Each wall crossing is counted once, and doors and gaps are respected. Optional wall auto-detection for clean drawings.
- **Four layers:** Wi-Fi 2.4 GHz, Wi-Fi 5 GHz, 4G LTE and 5G NR, each with its own frequency and transmit power.
- **Custom devices:** save named profiles (technology, frequency, Tx power, antenna gain, cable loss → EIRP) and place them from the marker selector. Editing a device updates every marker placed from it. Devices are remembered in your browser, stored in project files, and can be exported and imported as JSON to share with colleagues.
- **Two propagation models:**
  - log-distance with explicit walls and equipment zones;
  - ITU-R P.1238 industrial (site-general), with LOS/NLOS, uncertainty and validity-range warnings.
- **Coverage figures:** heatmap (smooth or 5 dB bands), hover readout and the percentage of area above your target level, over the whole plan or only inside the walls.
- **AP placement suggestion:** a greedy search that adds, nudges and prunes access points until the target area is reached.
- **Measurements:** add real readings as pins, compare them with the prediction, and calibrate the model offset.

## Limits

SignalSketch is a planning sketch, not a site survey.
It is 2D and single-floor, and it does not model antenna heights, antenna patterns, reflections, client uplink power, capacity or interference.
Wall losses and equipment losses are generic starting values.
Calibrate with a few real measurements before you trust an AP count.

## Privacy

Everything runs locally in your browser tab. Plans and projects are read from and saved to your own disk; nothing is uploaded.

## License

[MIT](LICENSE). PDF import uses [PDF.js](https://mozilla.github.io/pdf.js/) by Mozilla (Apache 2.0), included in `lib/pdfjs`.
