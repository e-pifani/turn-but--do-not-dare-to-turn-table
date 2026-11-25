# Counter Spin (turn but do not dare to turn table)

Put your phone on a turntable and the picture or video on its screen stays still.

The page rotates the visual counter-clockwise at the speed of the platter, so the platter's clockwise turn cancels it out.

## Use

1. Open `index.html` in a phone browser (or host it, see below).
2. Choose an image or video.
3. Pick **33⅓** or **45** RPM.
4. Press **Start**. The controls hide while it spins.
5. Tap the screen to stop. It returns to the first screen with the visual loaded.

While spinning you can still drag to move the visual and pinch (or use the size slider / mouse wheel) to resize it.

### Spin around

- **Screen centre**: rotates around the middle of the screen (marked by a small ring). Put the spindle under that point.
- **Visual centre**: rotates around the visual's own centre.

## Speeds

| RPM  | Degrees per second |
|------|--------------------|
| 33⅓  | 200                |
| 45   | 270                |

## Hosting

It is a single static file with no dependencies and no build step. Serve it from any static host.

To try it locally: `python -m http.server`, then open `http://<your-pc-ip>:8000` on the phone.

## Notes

- The screen is kept awake while spinning (Screen Wake Lock, where supported).
- Media stays on the device. Nothing is uploaded.
