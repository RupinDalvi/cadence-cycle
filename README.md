# Cadence Cycle Conformer

## Overview:

Cadence Cycle Conformer is a browser-based prototype that integrates a YouTube video player with real-time cadence feedback via the device's accelerometer. It adjusts audio volume and emits noise cues when the user's pedaling RPM deviates from a set target.

## Features:

* Load and play arbitrary YouTube videos in-page.
* Set a desired cadence (RPM) target.
* Measure pedaling cadence using the device motion sensor (accelerometer).
* Smooth noisy sensor data with EMA filters and amplitude thresholding.
* Provide audio feedback:

  * Lower video volume when RPM deviates beyond thresholds.
  * Add auditory noise cues when RPM is too low.
* Responsive, mobile-friendly UI without external dependencies.

## Installation & Usage:

1. Clone the repository:

   ```bash
   git clone https://<your-repo-url>/cadence-cycle-mvp.git
   cd cadence-cycle-mvp
   ```
2. Open `index.html` in a modern mobile browser (e.g., Chrome, Safari).
3. Allow motion permissions if prompted.
4. Enter a YouTube video URL, click "Load Video."
5. Set your target RPM and click "Start Cadence Monitoring."
6. Pedal on your stationary bike; watch RPM and audio feedback - note that this uses the phone's accelerometer, so it will require your phone to be in your cycling bib's front pocket or another place where the pedaling movement can actually be detected by it.

## Configuration:

* **Target RPM**: Adjust via the input field.
* **EMA Filter Parameters**:

  * `EMA_ALPHA` (accelerometer smoothing)
  * `RPM_SMOOTHING_ALPHA` (RPM display smoothing)
* **Amplitude Threshold**:

  * `ACCEL_AMPLITUDE_THRESHOLD`: minimum acceleration swing to count as valid cadence.

## File Structure:

```
/ (root)
├─ cadence_cycle.html       # Main application UI and logic
├─ README.txt       # This documentation file
```

## Browser Support & Requirements:

* Modern mobile browser with DeviceMotionEvent support.
* HTTPS context for motion sensor APIs on iOS/Safari.
* Internet connection to load YouTube IFrame API and videos.

## Customization:

* Adjust CSS in the `<style>` block for theming or layout.
* Tweak thresholds and filter constants in the `<script>` section.
* Extend audio feedback logic (e.g., add musical cues, vibration).

## License:

MIT License. Feel free to reuse and modify for your own projects.

## Contact:

For questions or contributions, open an issue or submit a pull request on the repository.
