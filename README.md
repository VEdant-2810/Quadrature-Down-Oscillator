
# Quadrature Down Converter

## 📌 Overview
This project implements a **Quadrature Down Converter** using LTSpice to perform frequency translation of high-frequency signals to baseband. Such systems are widely used in **RF communication**, **modulation/demodulation**, and **signal processing**.

The design consists of three main stages:
- Oscillator
- Mixer
- Low-Pass Filter

---

## ⚙️ System Architecture

The complete system performs:
\[
f_{out} = f_{in} - f_{osc}
\]

It generates **in-phase (I)** and **quadrature (Q)** components by mixing the input signal with cosine and sine local oscillator signals.

---

## 🧩 Components

### 🔹 1. Oscillator (Bubba Oscillator)
- Generates sine and cosine waves
- Frequency: ~100 kHz  
- Phase difference: ~90°  
- Built using op-amp based RC phase-shift network

---

### 🔹 2. Mixer
- Implemented using a **MOSFET operating in triode region**
- Performs signal multiplication:
\[
V_{out} \propto V_{in} \cdot V_{osc}
\]
- Produces sum and difference frequencies:
\[
f_{out} = f_{in} \pm f_{osc}
\]

---

### 🔹 3. Low-Pass Filter (LPF)
- RC filter with cutoff ≈ 2 kHz  
- Removes high-frequency components  
- Extracts the baseband signal:
\[
f_{out} = f_{in} - f_{osc}
\]

---

## 📊 Simulation Results

- Input frequency: ~102 kHz  
- Oscillator frequency: ~100 kHz  
- Output frequency: ~2 kHz  

### Key Observations:
- Successful frequency down-conversion  
- I and Q signals exhibit ~90° phase difference  
- FFT confirms dominant component at baseband frequency  
- Higher frequency components are effectively attenuated  

---

## 🛠️ Tools Used
- **LTSpice** (circuit design and simulation)

---

## 📁 Files
- LTSpice schematic / netlist
- Simulation plots (transient + FFT)
- Project report

---

## 📚 Applications
- RF receivers  
- Software Defined Radio (SDR)  
- Communication systems (QAM, PSK)  
- Signal demodulation  

---

## 🧠 Key Learnings
- Design of oscillator, mixer, and filter circuits  
- Frequency translation using signal multiplication  
- Quadrature signal generation (I/Q demodulation)  
- Circuit simulation and validation using FFT  

---

## 👨‍💻 Authors
- Anish Toshniwal  
- Vedant Zope  
- Kavya Pandey

