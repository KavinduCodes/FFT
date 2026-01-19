Here is a **clean, professional `README.md`** you can directly add to your GitHub repository.
It is written for **academic + technical clarity** and matches **exactly what you implemented**.

---

# Sampling and Reconstruction Using RP2040

## Overview

This project demonstrates **sampling and reconstruction of analog signals** using the **RP2040 microcontroller (Raspberry Pi Pico)**. The built-in ADC is configured for high-speed, constant-rate sampling, and the acquired data is transferred to a computer for **time-domain reconstruction** and **frequency-domain (FFT) analysis** using Python and Jupyter Notebook.

Signals in the range **10 Hz to 1 kHz** are sampled, reconstructed, and analyzed to evaluate reconstruction quality in accordance with the **Nyquist–Shannon sampling theorem**.

---

## Features

* High-speed **12-bit ADC sampling** using RP2040
* Constant sampling rate (**10 kHz**)
* Safe signal generator interfacing with **protection circuit**
* Time-domain signal reconstruction in Python
* Frequency-domain analysis using **Fourier Transform (FFT)**
* Visualization using **Matplotlib**

---

## Hardware Requirements

* Raspberry Pi Pico (RP2040)
* Signal Generator
* Protection circuit components:

  * 1 kΩ resistor
  * 2 × 1N5817 Schottky diodes
  * 100 nF capacitor
* Breadboard and jumper wires
* USB cable

---

## Circuit Description

The signal generator output is connected to the RP2040 ADC input (GPIO 26) through a protection circuit consisting of a 1 kΩ series resistor, two Schottky clamp diodes to 3.3 V and ground, and a 100 nF capacitor for noise filtering. This ensures the ADC input voltage remains within the safe 0–3.3 V range.

---

## Software Requirements

* Arduino IDE (with RP2040 board support)
* Python 3.x
* Jupyter Notebook
* Required Python libraries:

  ```bash
  pip install pyserial numpy matplotlib scipy
  ```

---

## Repository Structure

```
├── Arduino_Code/
│   └── fft.ino
├── Python_Code/
│   ├── ADC.ipynb
│   └── Fourier.ipynb
├── Plots/
│   ├── time_domain_10Hz.png
│   ├── time_domain_1kHz.png
│   ├── fft_10Hz.png
│   └── fft_1kHz.png
├── Circuit/
│   └── protection_circuit_diagram.png
└── README.md
```

---

## How to Run

### 1. Arduino (RP2040)

1. Open the Arduino sketch in `Arduino_Code/`
2. Select **Raspberry Pi Pico** board and correct COM port
3. Upload the code
4. Set the signal generator frequency (10 Hz – 1 kHz)
5. Press **RESET** to capture samples

---

### 2. Python / Jupyter Notebook

1. Close Arduino Serial Monitor
2. Open the Jupyter Notebook files in `Python_Code/`
3. Update the COM port if required
4. Run the notebook cells to:

   * Convert ADC values to voltage
   * Plot voltage vs sample number
   * Perform FFT and plot frequency spectrum

---

## Results Summary

* Low-frequency signals (10 Hz) show smooth time-domain reconstruction and clean FFT spectra.
* Higher-frequency signals (1 kHz) exhibit reduced samples-per-cycle and minor spectral spreading.
* FFT analysis confirms correct frequency detection and validates Nyquist sampling criteria.

---

## Applications

* Digital Signal Processing (DSP) education
* Embedded systems signal acquisition
* Sampling theorem demonstration
* ADC performance analysis

---

## References

* RP2040 Datasheet
* Nyquist–Shannon Sampling Theorem
* NumPy, SciPy, Matplotlib Documentation

---

## Author

**Kavindu**
