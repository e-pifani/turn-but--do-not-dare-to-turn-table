# Counter Spin (turn but do not dare to turn table)

Put your phone on a turntable and the picture or video on its screen stays still.

The page rotates the visual counter-clockwise at the speed of the platter, so the platter's clockwise turn cancels it out.

## Try it

You can test it live at https://idelabz.com/turn-but--do-not-dare-to-turn-table/ (open it on your phone).

## Use

1. Open `index.html` in a phone browser (or host it, see below).
2. Choose an image or video.
3. Pick **Auto** (default: follows the real platter speed with the gyroscope), **33⅓** or **45** RPM.
4. Press **Start**. The controls hide while it spins.
5. Tap the screen to stop. It returns to the first screen with the visual loaded.

While spinning you can still drag to move the visual and pinch (or use the size slider / mouse wheel) to resize it.

### Spin around

- **Screen centre**: rotates around the middle of the screen (marked by a small ring). Put the spindle under that point.
- **Visual centre**: rotates around the visual's own centre.

## Auto mode

Auto reads the phone's gyroscope and counter-rotates the visual by the platter's real, measured rotation, so it stays still even if the turntable runs a little fast, slow or uneven. A small RPM readout shows the measured speed.

- Lay the phone screen-up on the platter.
- Needs a gyroscope and HTTPS. On iPhone, Safari asks for motion-sensor permission when you press Start.

## Auto-locate spindle

If the phone is not centred on the spindle, the picture appears to circle around it. With **Spindle: Auto-locate (sensor)** the accelerometer measures the centripetal acceleration (ω²·r, pointing at the spindle) and the app moves its rotation point onto the spindle, so you see the same object all the time.

1. Lay the phone screen-up on the platter, platter **stopped**, and press **Start** (the app learns the resting sensor reading).
2. Switch the turntable on. After about 2 s the readout shows the estimated distance to the spindle and the picture settles.

Notes: it is an estimate (sensor placement, tilt and the px-per-cm assumption add error), works best with the platter level, and needs HTTPS plus a motion sensor. It works with 33, 45 or Auto speed.

### Sensor log

While the sensors run (Auto speed or Auto-locate) the app records a row every 100 ms: platter speed, raw gyro and accelerometer values, the resting reading, the spindle fit and the current pivot. After you stop, the controls show **Copy log** and **Download CSV**; the log is kept until the next Start.

## More controls

The collapsed **More controls** section holds the advanced options: Spin around, Auto-locate spindle, the sensor log and the help text.

Start stays disabled until a visual is loaded, and the visual is fitted to the screen width or height without changing its aspect ratio.

**Spin around** defaults to *Visual centre*. Switching on *Auto-locate* changes it to *Screen centre* (the point it rotates around is then the spindle position the sensors found).

## Speeds

| RPM  | Degrees per second |
|------|--------------------|
| 33⅓  | 200                |
| 45   | 270                |

## Hosting

It is a single static file with no dependencies and no build step. Serve it from any static host.

To try it locally: `python -m http.server`, then open `http://<your-pc-ip>:8000` on the phone.

## Notes

- **Tested only on Android** (Chrome). It has not been tested in any iOS browser. The iOS code paths (motion-sensor permission prompt, reversed accelerometer sign, gyro axis mapping) are written from the specs and may need fixes.
- The screen is kept awake while spinning (Screen Wake Lock, where supported).
- Media stays on the device. Nothing is uploaded.

## License

Licensed under the GNU General Public License v3.0 (GPL-3.0). You are free to use, study, modify and share it; if you distribute a modified version, you must release it under the same license. See [LICENSE](LICENSE).
