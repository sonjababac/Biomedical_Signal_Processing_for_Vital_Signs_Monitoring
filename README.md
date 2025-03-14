# Signal Processing for Remote Patient Monitoring

This repository contains two Python scripts (originally translated from MATLAB) demonstrating how to process real-world physiological data for **remote patient monitoring**. The focus is on:

1. **Measuring SpO₂ and Pulse Rate** from photoplethysmography (PPG) data.
2. **Measuring Respiration and Pulse Rate** from accelerometry data (seismocardiography + chest orientation).

Additionally, this repository includes:
- A `requirements.txt` file listing the Python dependencies.
- A `Datasets/` folder containing subfolders for each script’s data.
- Lecture slides from a session at Eindhoven University of Technology, offering an overview of clinical-grade remote patient monitoring and wellness-oriented health monitoring innovations.

---

## Repository Contents
. ├── Datasets │ 
├── Accelerometry │ 
│ └── [CSV files for measuring respiration and pulse from accelerometer] │
└── PPG │ └── [Excel or CSV files for measuring SpO₂ and pulse rate from PPG data]
├── Remote_Patient_Monitoring_Trends_in_2025_slides.pdf
├── requirements.txt 
├── Measuring_Respiration_and_Pulse_Rate.ipynb (Accelerometry-based lab)
├── Measuring_SpO2_and_Pulse_Rate.ipynb (PPG-based lab) 
└── README.md

1. **`Measuring_SpO2_and_Pulse_Rate.ipynb`**  
   Demonstrates how to:
   - Load and preprocess PPG signals (red & IR).
   - Apply filtering and ratio-of-ratios methods.
   - Detect peaks to calculate pulse rate.
   - Compute SpO₂ from calibrated sensor data.
   - Visualize the signals and compare results with reference measurements.

2. **`Measuring_Respiration_and_Pulse_Rate.ipynb`**  
   Demonstrates how to:
   - Load and resample accelerometry data (X, Y, Z).
   - Identify which axes primarily reflect respiration (Y) and pulse (Z).
   - Perform spectral analysis to guide filter design.
   - Apply bandpass filters for respiration and pulse rate ranges.
   - Detect peaks to calculate respiration rate and pulse rate.
   - (Optional) Use the envelope of the pulse signal for more robust PR estimation.
   - Visualize how PR and RR change over time and compare with manual measurements.

3. **`requirements.txt`**  
   A list of Python dependencies used in both notebooks. See instructions below on how to install them.

4. **`Datasets/`**  
   - **`Accelerometry/`**: Contains the accelerometer CSV files for the respiration/pulse notebook.  
   - **`PPG/`**: Contains the photoplethysmography files (e.g., `.xlsx` or `.csv`) for the SpO₂/pulse notebook.

5. **`Remote_Patient_Monitoring_Trends_in_2025_slides.pdf`**  
   Lecture slides discussing the current state of clinical-grade remote patient monitoring, as well as future trends in consumer and wellness-oriented health monitoring.

---

## Installation & Usage

1. **Clone this repository**:
   ```bash
   git clone https://github.com/<YourUsername>/Signal_Processing_For_Remote_Patient_Monitoring.git
   cd Signal_Processing_For_Remote_Patient_Monitoring
