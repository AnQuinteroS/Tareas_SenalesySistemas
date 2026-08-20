# Signals and Systems: Fourier Transform Assignments

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AnQuinteroS/Tareas_SenalesySistemas/blob/main/Ejercicios_Serie_FTT_y_Taller_2.ipynb)

## Overview
This repository contains coursework for the **Signals and Systems** course of the Electronic Engineering program at Universidad Nacional de Colombia, Manizales. The notebook applies the **Discrete Fourier Transform (DFT)** and the **Fast Fourier Transform (FFT)** to real audio, power electronics and communications problems, using Python in Google Colab.

The notebook itself is written in Spanish.

## Contents

### 1. DFT vs. FFT Performance
A direct summation DFT, with complexity $O(N^2)$, is timed against NumPy's FFT, with complexity $O(N \log N)$, for signal lengths from 4 to 4096 samples. The resulting plot shows how quickly the direct method becomes impractical as the signal grows.

### 2. Spectral Filtering of a Song
A song is downloaded from YouTube with `yt-dlp`, converted to WAV with `ffmpeg`, and a 5-second stereo segment is processed in the frequency domain:
- The spectrum of each channel is computed with `np.fft.rfft`.
- Low-pass, high-pass, band-pass and band-stop filters are applied by setting the unwanted frequency bins to zero.
- The signal is rebuilt with `np.fft.irfft`, played back in the notebook and saved as a WAV file.

### 3. Music Genre Detector (Work in Progress)
The goal is to classify a 5-second clip into one of three genres by computing the Euclidean distance between its magnitude spectrum and a database of reference clips. The notebook currently downloads and converts the dataset for two genres (Jazz and Bachata); the classification step is not implemented yet.

### 4. Total Harmonic Distortion and Power Factor
A theoretical section explaining how Total Harmonic Distortion (THD) is obtained from the FFT, and how the distortion power factor is derived from it:

$$THD = \frac{\sqrt{V_2^2 + V_3^2 + \dots + V_n^2}}{V_1}, \qquad PF_{dist} = \frac{1}{\sqrt{1 + THD^2}}$$

### 5. AM Modulation
Examples of amplitude modulation with a rectangular pulse message and a cosine message, plotted in the time domain and in the frequency domain using `rfft`.

## Tech Stack
- Python 3, NumPy, Matplotlib
- SoundFile and IPython Audio for audio input and playback
- yt-dlp and FFmpeg for downloading and converting audio
- Google Colab

## How to Run
The easiest way is to click the **Open in Colab** badge above and run the cells in order. The audio sections need an internet connection to download the songs.

To run it locally:

```bash
pip install numpy matplotlib soundfile yt-dlp jupyter
jupyter notebook Ejercicios_Serie_FTT_y_Taller_2.ipynb
```

FFmpeg must also be installed and available in the system `PATH`.

## Author
**Andrés Quintero** · [GitHub](https://github.com/AnQuinteroS) · [LinkedIn](https://linkedin.com/in/andres-quintero-salazar)
