# EEG-Circuit

This project reads EEG data from multiple analog channels via Arduino and visualizes both time-domain and frequency-domain signals using Processing.

### 🧠 What it does:
- Captures EEG signals via Arduino (6-channel max).
- Sends the data over Serial to the PC.
- Uses autoregressive modeling (instead of FFT) to display spectral features.
- Supports real-time visualization in Processing.

### 💻 Tools Used:
- Arduino Uno
- Processing (with Minim library)
- Matlab (used for offline EEG signal capture & filtering)
