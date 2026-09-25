# Tinnitus App

A single-page web app for finding the pitch of your tinnitus and playing it back
without interruption, with pulsing sound and a full-screen light room that
flashes in step with the tone.

**Live:** https://andreasbros.github.io/tinitus/

## What it does

- Plays a continuous pure tone or narrow-band hiss at any frequency from 1 Hz
  to 22 kHz on a logarithmic slider, with the audible 20 Hz – 20 kHz band marked.
- Fine-tunes with ±1, ±10 and ±100 Hz buttons or the arrow keys.
- Pans the sound to the left ear, right ear or both.
- Pulses the sound in five modes: off, on/off, left ↔ right, left only,
  right only, at any rate from 0.2 Hz to 40 Hz.
- Opens a full-screen light room (tap the orb) that fills each half of the
  screen with bright colour following the left and right channels.
- Remembers your settings and locked-in matches on the device.
- Installs as a standalone web app (manifest, icons, service worker) and keeps
  playing with the phone locked, with play, pause and ±10 Hz controls on the
  lock screen through the Media Session API.

## Install on iPhone

Open the live URL in Safari, tap **Share**, then **Add to Home Screen**. The
app opens full screen from its icon. Press play once inside the app; the tone
then continues when you lock the phone or switch apps, and the lock screen
shows Now Playing controls. A silent looping audio element keeps the iOS audio
session alive, which is what allows Web Audio to run in the background.

## Run locally

It is one static file with no build step. Open `index.html` in a browser, or
serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

React and the Radix UI primitives load as ES modules from jsdelivr, and the
fonts from Google Fonts, so an internet connection is needed the first time.

## Deploy

Pushing to `main` runs `.github/workflows/pages.yml`, which publishes the
repository root to GitHub Pages.

## Safety

Loud tones can worsen tinnitus, so start at a low volume. The light room
flashes bright light at up to 40 Hz. Do not use it if you have photosensitive
epilepsy or a history of seizures, and stop if you feel unwell.
