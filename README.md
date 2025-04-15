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

## ⚡ Circuit Overview

This project utilizes a custom-built **EEG acquisition circuit**, designed using analog components to filter, amplify, and process brainwave signals. The circuit consists of an instrumentation amplifier for signal conditioning and operational amplifiers for further signal processing. 

Key components used in the circuit:
- **AD620AN**: An instrumentation amplifier used to amplify small differential EEG signals.
- **TL084CN**: A quad op-amp used for further amplification and filtering of the EEG signals to ensure accurate readings and minimize noise.
  
### 🧑‍🔬 How the Circuit Works:
- **EEG Signal Detection**: Electrodes are placed on the scalp based on the **10–20 system**. These electrodes detect the electrical activity of the brain and send the raw signal to the EEG circuit.
- **Signal Amplification**: The AD620AN instrumentation amplifier boosts the small EEG signals. The op-amps (TL084CN) are used for additional filtering and amplification to ensure the signal quality is suitable for analysis.
- **Filtering**: Active filters are used to remove noise from the signal, such as power-line interference and artifacts from eye movements.
- **Transmission to Arduino**: After amplification and filtering, the analog signals are sent to the Arduino, which reads them through its analog inputs. The processed data is then transmitted via Serial to the PC for visualization.


## 🧑‍⚕️ Electrode Placement: The 10–20 System

The **10–20 system** is a widely used method for placing EEG electrodes on the scalp. The positions are based on the distance between key anatomical landmarks, ensuring a standardized setup across different individuals and experiments. 

### Electrode Locations:
- **Fp1, Fp2**: Frontal positions (left and right)
- **C3, C4**: Central positions (left and right)
- **P3, P4**: Parietal positions (left and right)
- **O1, O2**: Occipital positions (left and right)

These electrodes measure electrical activity at various brain regions. The signals from these electrodes are processed and visualized to analyze brain activity patterns.


## 🔬 Signal Processing

- **Autoregressive (AR) Modeling**: Instead of the traditional Fast Fourier Transform (FFT), this project uses autoregressive modeling to estimate the spectral features of the EEG signal. This approach helps in providing more accurate frequency-domain representations for the visualization of brain activity.
  
- **Time-Domain & Frequency-Domain Visualization**: The captured EEG signals are displayed in both the time-domain (raw signals) and frequency-domain (power spectral density) to analyze brainwave patterns such as alpha, beta, and theta waves.
