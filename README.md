# guitar-tuner

This project is a real-time guitar tuner built in Python using the Hyperbolic Product Spectrum (HPS) approach. The tuner captures audio through the microphone and processes it to identify the closest musical note.

## Features

- Captures audio using the `sounddevice` library.
- Applies a Hann window to reduce spectral leakage.
- Uses Fast Fourier Transform (FFT) to convert audio signals to frequency-domain data.
- Implements the HPS algorithm to determine the fundamental frequency.
- Suppresses background noise and mains hum.
- Displays the tuned note only after stable readings.

## Requirements

- Python 3.x
- numpy
- scipy
- sounddevice

## How It Works

1. **Audio Input:** The program starts an input stream and continuously reads audio samples.
2. **Windowing and FFT:** Samples are windowed with a Hann window to mitigate edge effects and then transformed using FFT.
3. **Noise Suppression:** Frequencies below 62 Hz and weak components in each octave band are filtered out.
4. **HPS Calculation:** The HPS algorithm combines multiple downsampled spectra to emphasize the fundamental frequency.
5. **Note Identification:** The resultant frequency is compared to standard tuning to find the closest musical note and its frequency is displayed.

## Running the Tuner

Ensure that your microphone is set up correctly, then run the script:

```bash
python HPS_Tuner.py