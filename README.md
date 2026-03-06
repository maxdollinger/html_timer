# Timer

A minimal, single-file countdown/countup timer with no external dependencies. Designed to be embedded as an `<iframe>` and configured entirely via URL parameters.

## Usage

```html
<iframe src="timer.html?duration=120&direction=down&autostart=1&countdown=3"></iframe>
```

## URL Parameters

| Parameter   | Default  | Description |
|-------------|----------|-------------|
| `duration`  | `60`     | Timer duration in seconds. |
| `direction` | `down`   | Count direction: `down` (countdown) or `up` (countup). |
| `autostart` | `0`      | `1` = start the timer automatically on page load. `0` = require manual start. |
| `countdown` | `0`      | Seconds of pre-timer countdown shown before the timer begins (e.g. `3` shows a 3-2-1 countdown). `0` = no countdown, start immediately. |
| `sound`     | `1`      | Enable (`1`) or disable (`0`) beep sounds. Only applies when the timer is started manually — autostart via URL param always runs silently because browsers block audio playback on page load without a prior user interaction. |

## Controls

- **Start / Pause / Resume** — Start the timer, pause it mid-run, or resume from a paused state.
- **Reset** — Stop the timer and return to the initial ready state.

## Phases

| Phase      | Description |
|------------|-------------|
| Ready      | Initial state, waiting for user input. |
| Starting in | Countdown to autostart (pink). |
| Running    | Timer is active (cyan). |
| Done       | Timer has reached its end, display pulses white. |
