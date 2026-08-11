# Portfolio site — Paulo Caleb

Static site (HTML + CSS, no build step), ready for GitHub Pages.

## Structure
```
index.html
style.css
assets/            ← put your images here, using the exact filenames below
```

## Image checklist

Drop files into `assets/` with these exact names — the page will pick them
up automatically. Until a file exists, that slot shows an "unpopulated
footprint" placeholder with the expected filename.

**General CADs**
- `assets/cad-3d-printed-motor-01.jpg`
- `assets/cad-didactic-bench.jpg`

**Weather Station**
- `assets/pcb-weather-station-board.jpg`
- `assets/pcb-weather-station-schematic.jpg`
- `assets/pcb-weather-station-layout.jpg`

**eAlive**
- `assets/pcb-ealive-dongle-01.jpg`
- `assets/pcb-ealive-dongle-02.jpg`
- `assets/pcb-ealive-connector.jpg`
- `assets/pcb-ealive-schematic.jpg`
- `assets/pcb-ealive-panel.jpg`

**IoT Server Power Controller**
- `assets/pcb-server-ctrl-board.jpg`
- `assets/pcb-server-ctrl-3d.jpg`
- `assets/pcb-server-ctrl-layout.jpg`
- `assets/pcb-server-ctrl-ui.jpg`

**Aquarium Control Unit**
- `assets/other-aquarium-unit.jpg`
- `assets/other-fluid-mixer.jpg`
- `assets/other-aquarium-electronics.jpg`
- `assets/other-aquarium-schematic.jpg`

**FGR ECUs**
- `assets/other-fgr-ecu-01.jpg`

**Conveyor Belt Sorting System**
- `assets/other-conveyor-belt.jpg`
- `assets/other-conveyor-board.jpg`
- `assets/other-conveyor-gui.jpg`

Any image size works — they're all cropped to a fixed frame with
`object-fit: cover`, but aim for at least 800px wide for a crisp result.

## Deploy on GitHub Pages

```bash
git init
git add .
git commit -m "portfolio site"
git branch -M main
git remote add origin https://github.com/<seu-usuario>/<seu-usuario>.github.io.git
git push -u origin main
```

Then: **Settings → Pages → Build and deployment → branch `main`, folder `/root`**.
Site goes live at `https://<seu-usuario>.github.io`.

## Editing later
- Text/copy: edit directly in `index.html`.
- Colors/fonts/spacing: all in `style.css` under the `:root` token block at the top.
- New project card: copy an existing `<article class="card">…</article>` block and adjust.
