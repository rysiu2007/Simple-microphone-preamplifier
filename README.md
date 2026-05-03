# Dual-Channel Microphone Preamplifier (F4558)

This repository contains the design and documentation for a high-gain microphone preamplifier utilizing the **F4558 Dual Operational Amplifier**. The circuit is optimized for low-noise amplification of small-signal audio inputs.

## ⚡ Circuit Features
*   **Topology:** Inverting Transimpedance Amplifier (TIA) configuration.
*   **Constant Gain:** Fixed by a **470kΩ** precision feedback resistor.
*   **Stability:** Includes a **10pF** compensation capacitor ($C_6/C_7$) in parallel with the feedback loop to prevent high-frequency oscillation and roll off ultrasonic noise.
*   **Biasing:** Virtual ground established at **+6V** (half-supply) to allow for single-supply operation from a +12V source.
*   **Input Stage:** AC-coupled via **4.7µF** electrolytic capacitors with 10kΩ pull-ups for microphone biasing.

## 🖼 Schematic Overview
The design uses both halves of the F4558 (U1A and U1B) to provide dual-channel processing. 

![Microphone Preamplifier Schematic](schematic.png) 
*(Note: Upload your image to the repo and name it schematic.png for this to show up!)*

## 📂 Project Files
*   **[mic-amp-report.pdf](mic-amp-report.pdf)**: Full engineering report, including frequency response curves and BOM.
*   **index.html**: Project landing page.

## 🚀 Calculations
The gain for this specific inverting setup is defined by the input impedance of the microphone vs the feedback resistor ($R_f$):

$$V_{out} \approx -I_{in} \times R_f$$

The low-pass cutoff frequency ($f_c$) created by the feedback network is:
$$f_c = \frac{1}{2\pi \times 470k\Omega \times 10pF} \approx 33.8 \text{ kHz}$$
This ensures the full audible spectrum is captured while filtering out unwanted RF interference.
