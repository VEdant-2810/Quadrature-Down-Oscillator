# Quadrature Down Converter

An analog **Quadrature Down Converter** designed and simulated in **LTSpice** for translating high-frequency RF signals to low-frequency baseband signals. The project demonstrates the complete signal chain using a **Bubba Oscillator**, **MOSFET-based Mixer**, and **Cascaded Low-Pass Filters** to generate **In-phase (I)** and **Quadrature (Q)** outputs.

> 📄 For detailed circuit analysis, derivations, and simulation results, refer to the **Project Report** included in this repository.

---

## 📌 Overview

Quadrature Down Converters are widely used in RF receivers and communication systems to shift high-frequency signals to lower frequencies for easier processing.

This project implements the complete down-conversion process using analog circuit blocks and validates the design through transient and FFT simulations in LTSpice.

---

## ⚙️ System Architecture

```text
            RF Input
               │
               ▼
      Bubba Oscillator
     (Sin & Cos Outputs)
               │
        ┌──────┴──────┐
        ▼             ▼
      Mixer         Mixer
        │             │
        ▼             ▼
   Low Pass Filter  Low Pass Filter
        │             │
        ▼             ▼
      I Output      Q Output
```

The output frequency follows:

```text
f_out = |f_in − f_LO|
```

---

## 🧩 Components

### 🔹 Bubba Oscillator
- Generates sine and cosine local oscillator signals
- Frequency: **100.2 kHz**
- Approximately **90° phase difference**

### 🔹 MOSFET Mixer
- NMOS operating in the **triode region**
- Produces both **sum** and **difference** frequency components through analog multiplication

### 🔹 Cascaded Low-Pass Filter
- Two-stage RC filter
- Cutoff frequency: **≈2 kHz**
- Removes unwanted high-frequency mixing products while preserving the baseband signal

---

## 📐 Design Specifications

| Parameter | Value |
|-----------|-------|
| Simulation Tool | LTSpice XVII |
| Oscillator Frequency | 100.2 kHz |
| Input Frequency | 95–105 kHz |
| Example Input | 102 kHz |
| Output Frequency | ≈2 kHz |
| LPF Cutoff | ≈2 kHz |

---

## 📊 Results

- Successfully down-converted RF signals to baseband.
- Generated stable **In-phase (I)** and **Quadrature (Q)** outputs.
- Achieved approximately **92° phase difference** between the final I/Q signals.
- FFT analysis confirmed suppression of unwanted frequency components and successful extraction of the desired baseband signal.

---

## 🛠️ Tools Used

- LTSpice XVII
- Analog CMOS Circuit Design
- Transient Analysis
- FFT Analysis

---

## 📚 Applications

- RF Receivers
- Software Defined Radio (SDR)
- QAM & PSK Demodulation
- Wireless Communication Systems

---

## 📁 Repository Contents

```
├── Oscillator
├── Mixer
├── LowPassFilter
├── CompleteCircuit
├── SimulationPlots
├── ProjectReport.pdf
└── README.md
```

---

## 👨‍💻 Authors

- **Anish Toshniwal**
- **Vedant Zope**
- **Kavya Pandey**
