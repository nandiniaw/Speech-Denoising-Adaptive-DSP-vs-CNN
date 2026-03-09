
## Overview
This project investigates two approaches to speech denoising:
- **Classical DSP** — NLMS Adaptive Filter and Wiener Filter
- **Deep Learning** — Conv2D CNN trained on log-magnitude spectrograms

Both approaches are evaluated under multiple noise conditions and SNR levels.

## Methods

### 1. NLMS Adaptive Filter
- 64-tap filter with normalized LMS update rule
- Tested on AR(1) colored noise
- SNR range: -5 dB to +15 dB

### 2. Wiener Filter
- Implemented in the STFT domain (n_fft=512, hop=256)
- Tested on AWGN and Babble noise
- SNR range: -5 dB to +15 dB

### 3. Conv2D CNN
- Input: log-magnitude spectrograms (n_fft=256, hop=128) at 8kHz
- Architecture: 4-layer Conv2D network
- Trained on TIMIT dataset mixed with real noise files
- Tested across SNR levels: -5, 0, 5, 10, 15 dB

## Results

| Method | Noise Type | SNR Range Tested |
|--------|------------|------------------|
| NLMS Filter | AR(1) Colored | 5 dB input |
| Wiener Filter | AWGN | -5 to +15 dB |
| Wiener Filter | Babble | -5 to +10 dB |
| Conv2D CNN | Real noise | -5 to +15 dB |

See full results with output plots and spectrograms in [Speech_Denoising_DSP_vs_LSTM.ipynb](Speech_Denoising_DSP_vs_LSTM.ipynb)

Performance evaluated using:
- SNR improvement (dB)
- FFT magnitude comparison
- Spectrogram visual analysis

## Tech Stack
- Python 3
- NumPy
- Librosa
- TensorFlow / Keras
- Matplotlib

## Author
**Nandini Walia**
B.Tech EEE, Vellore Institute of Technology
[linkedin.com/in/nandiniwalia](https://linkedin.com/in/nandiniwalia)
