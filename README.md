# Controller Visualizer

A single-file HTML visualizer that shows axes, triggers, bumpers, sticks and buttons for connected controllers using the browser Gamepad API.

Live demo: https://controller.parkerbrown.photos
*The controller dropdown takes a minute to populate on the live demo.

## Requirements
- Modern desktop browser with Gamepad API support (Chrome, Edge, Firefox recommended).
- For some browsers/controller combos the Gamepad API requires a secure context (HTTPS) or `localhost`.

## Quick start
1. Open the project folder and open `index.html` in your browser, or serve the folder and open the local URL.

Serve locally (example):

```bash
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

2. Connect a controller (USB or Bluetooth).
3. Select the controller from the dropdown at the top of the page.
4. Move sticks and press buttons to see the live visualization.

## Controls / Mapping (typical)
- Face buttons: A=0, B=1, X=2, Y=3
- Bumpers: LB=4, RB=5
- Triggers: LT=6, RT=7 (value buttons) or axes fallback
- Stick buttons: LS=10, RS=11
- D-Pad: Up=12, Down=13, Left=14, Right=15
- Axes: left stick = axes[0..1], right stick = axes[2..3] (model-dependent)

Note: Some controllers use different mappings; use developer tools (e.g. `chrome://gamepad-internals`) to inspect raw indices if things don't line up.

## Customization
- Open `index.html` and edit the top-level constants:
  - `SMOOTH` and `TRIG_SMOOTH` for stick/trigger smoothing responsiveness.
  - CSS variables at the top (e.g. `--trigger`, `--btn`) to change colors.

## Known limitations
- Nonstandard controllers may require remapping.
- Some browsers may not fire `gamepadconnected`/`gamepaddisconnected` reliably; the page polls for gamepads periodically.

If you want a screenshot or I can add a small local-server helper script, tell me which you'd prefer.