# Signal Processing for Remote Patient Monitoring

This repository contains two Python scripts demonstrating how to process real-world physiological data for **remote patient monitoring**. The focus is on:

1. **Measuring SpO₂ and Pulse Rate** from photoplethysmography (PPG) data.
2. **Measuring Respiration and Pulse Rate** from accelerometry data (seismocardiography - the recording of body vibrations induced by the heart and breathing).

Additionally, this repository includes:
- A `requirements.txt` file listing the Python dependencies.
- A `Datasets/` folder containing subfolders for each script’s data.
- Lecture slides from a session at Eindhoven University of Technology, offering an overview of clinical-grade remote patient monitoring and wellness-oriented health monitoring innovations.

---

## Repository Contents
```text
.
├── Datasets
│   ├── Accelerometry
│   │   └── [CSV files for measuring respiration and pulse from accelerometer]
│   └── PPG
│       └── [Excel or CSV files for measuring SpO₂ and pulse rate from PPG data]
├── Remote_Patient_Monitoring_Trends_in_2025_slides.pdf
├── requirements.txt
├── Measuring_Respiration_and_Pulse_Rate.ipynb  (Accelerometry-based lab)
├── Measuring_SpO2_and_Pulse_Rate.ipynb         (PPG-based lab)
└── README.md
```

## Overview of the Files

1. **`Measuring_SpO2_and_Pulse_Rate.ipynb`**

   This notebook demonstrates how to:
   - **Import and Inspect PPG Data:** Load red and infrared (IR) signals from a finger clip sensor.
   - **Preprocess Signals:** Apply a Butterworth bandpass filter to isolate the heart rate frequency range (0.8–2 Hz) and use a low-pass filter to separate DC and AC components.
   - **Visualize Signal Quality:** Plot raw versus filtered signals to verify noise reduction and preservation of the pulsatile AC component.
   - **Peak Detection:** Detect peaks in the filtered IR signal to determine the time intervals between heartbeats.
   - **Calculate Pulse Rate:** Convert inter-beat intervals into instantaneous pulse rate (bpm) and apply an 8-beat moving average for smoothing.
   - **Compute SpO₂:** Use the ratio-of-ratios method with calibration constants to compute SpO₂ per beat.
   - **Compare Results:** Visualize and compare the computed SpO₂ and pulse rate with reference measurements.

2. **`Measuring_Respiration_and_Pulse_Rate.ipynb`**

   This notebook demonstrates how to:
   - **Load and Resample Accelerometry Data:** Import CSV files containing acceleration data along the X, Y, and Z axes and interpolate the data to a uniform sampling rate (125 Hz).
   - **Understand Sensor Axes:** Identify that the Y-axis primarily captures respiration (chest expansion/contraction) while the Z-axis captures pulse-related mechanical vibrations.
   - **Spectral Analysis:** Compute periodograms to determine dominant frequency ranges (e.g., 0.1–0.5 Hz for respiration and 5–20 Hz for pulse rate) to guide filter design.
   - **Filter Design:** Create 3rd‑order Butterworth bandpass filters for both respiration and pulse signals.
   - **Apply Filtering:** Use both causal (lfilter) and zero-phase (filtfilt) filtering methods and compare the results.
   - **Peak Detection:** Detect peaks in the filtered signals to calculate respiration rate (RR) and pulse rate (PR).
   - **Envelope Analysis:** Compute the envelope of the filtered pulse signal using the Hilbert transform to enhance peak detection.
   - **Rate Calculation and Averaging:** Calculate instantaneous rates and average them over a 1‑minute period, then compare these with manually recorded values.
   - **Explore Signal Interactions:** Use dual‑axis plotting to visually analyze the interaction between respiration and pulse rate (Respiratory Sinus Arrhythmia).


3. **`requirements.txt`**  
   A list of Python dependencies used in both notebooks. See instructions below on how to install them.

4. **`Datasets/`**  
   - **`Accelerometry/`**: Contains the accelerometer CSV files for the respiration/pulse notebook.  
   - **`PPG/`**: Contains the photoplethysmography files (e.g., `.xlsx` or `.csv`) for the SpO₂/pulse notebook.

5. **`Remote_Patient_Monitoring_Trends_in_2025_slides.pdf`**  
   Lecture slides discussing the current state of clinical-grade remote patient monitoring, as well as future trends in consumer and wellness-oriented health monitoring.

---

## Installation & Usage

**Clone this repository**:
   ```bash
   git clone https://github.com/<YourUsername>/Signal_Processing_For_Remote_Patient_Monitoring.git
   cd Signal_Processing_For_Remote_Patient_Monitoring


## Disclaimer
These scripts are for educational and research purposes only and are not intended for clinical or diagnostic use. Consult appropriate medical professionals for any healthcare-related decisions.

## License
This project is licensed under the MIT License. Feel free to modify or use these materials in accordance with the license terms.

# Happy Vital Signs Monitoring!


