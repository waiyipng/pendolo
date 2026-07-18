# Pendolo

**A music-learner's companion — metronome, tuner, and tone generator, all in one page.**

Pendolo bundles the three tools a practicing musician reaches for most into a single, dependency-free web app. Each tool wears its own playful visual theme, but they share one Web Audio engine under the hood.

## Features

### 🟩 Craftronome — Metronome
A precise, low-latency metronome built on the Web Audio API's look-ahead scheduler (not `setInterval`), so beats stay rock-steady.

- Tempo from **40–240 BPM** via slider, ± buttons, or presets
- Automatic Italian tempo markings (Largo, Adagio, Andante, Moderato, Allegro, Vivace, Presto, Prestissimo)
- Quick-pick tempo presets and prev/next marking jumps
- Time signatures: **2/4, 3/4, 4/4, 6/8**, plus a **NONE** mode for plain, unaccented clicks
- Accented downbeats with animated beat indicators

### 🟥 Dear Tuner — Chromatic Tuner
A microphone-based chromatic tuner with a stabilized pitch reading.

- Real-time pitch detection using **autocorrelation** with a clarity (periodicity) score
- Median smoothing over recent readings to steady the display
- Note name, octave, frequency (Hz), and cents-off-from-pitch
- Visual needle gauge with flat / in-tune / sharp feedback
- A440 reference tuning

### 🟦 Tone Lab — Tone Generator
A reference-tone generator with a live oscilloscope.

- Pick any note by name + accidental (♭ ♮ ♯) + octave, or **dial in a custom frequency** (20–5000 Hz)
- Four waveforms: **sine, triangle, sawtooth, square**
- Adjustable volume
- Live waveform display on a canvas oscilloscope

## Usage

Pendolo is a **single, self-contained HTML file** — no build step, no dependencies, no server required.

- **Open directly:** double-click [index.html](index.html) or open it in any modern browser.
- **Or serve locally** (recommended, so the microphone works reliably):

  ```bash
  python3 -m http.server 8000
  # then visit http://localhost:8000
  ```

The tuner needs microphone permission, which browsers only grant over `https://` or `http://localhost`. Metronome and Tone Lab work anywhere, including straight from the filesystem.

## Tech

- Vanilla HTML, CSS, and JavaScript — a single file, no frameworks or dependencies
- **Web Audio API** for scheduling, synthesis, and analysis
- **getUserMedia** for microphone input, with fallbacks for older Safari
- Google Fonts for the themed typography
- Responsive, mobile-friendly, with reduced-motion support

## License

See repository for license details.
