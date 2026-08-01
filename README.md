# Quadrature Down Converter

An analog **Quadrature Down Converter** designed and simulated in **LTSpice** for translating high-frequency RF signals into low-frequency baseband signals. The project implements a complete analog signal chain using a **Bubba Oscillator**, **MOSFET-based Mixer**, and **Cascaded Low-Pass Filters** to generate **In-phase (I)** and **Quadrature (Q)** outputs.

> 📄 A detailed explanation of the design, mathematical derivations, and simulation results can be found in the accompanying project report.

---

## 📌 Overview

Quadrature Down Converters are widely used in RF receivers and communication systems to translate high-frequency signals to lower frequencies, enabling easier signal processing and demodulation.

This project demonstrates the complete down-conversion process in LTSpice and validates the design using transient and FFT analysis.

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

The output frequency is given by

```text
fout = |fin − fLO|
```

---

## 🧩 Components

### 🔹 Bubba Oscillator
- Generates quadrature sine and cosine signals
- Oscillation frequency: **100.2 kHz**
- Phase difference: **≈90°**

### 🔹 MOSFET Mixer
- NMOS operating in the **triode region**
- Produces both **sum** and **difference** frequency components through analog multiplication

### 🔹 Cascaded RC Low-Pass Filter
- Cutoff frequency: **≈2 kHz**
- Removes high-frequency mixing products while preserving the desired baseband signal

---

## 📐 Design Specifications

| Parameter | Value |
|-----------|-------|
| Simulation Software | LTSpice XVII |
| Local Oscillator Frequency | 100.2 kHz |
| Input Frequency Range | 95–105 kHz |
| Example Input Frequency | 102 kHz |
| Output Frequency | ≈2 kHz |
| Low-Pass Filter Cutoff | ≈2 kHz |

---

## 📊 Simulation Results

- Successfully down-converted RF signals to baseband.
- Generated stable **In-phase (I)** and **Quadrature (Q)** outputs.
- Achieved approximately **92° phase difference** between the final I/Q signals.
- FFT analysis verified suppression of unwanted frequency components and extraction of the desired baseband signal.

---

## 🛠️ Tools Used

- LTSpice XVII
- Transient Analysis
- FFT Analysis

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `QuadDownConverter.asc` | LTSpice schematic of the complete quadrature down converter |
| `Quadrature Down Converter.pdf` | Project report containing circuit design, derivations, and simulation results |
| `TSMC_180nm.txt` | CMOS transistor model used for MOSFET simulation |
| `UA741.301` | UA741 operational amplifier model |
| `README.md` | Project documentation |

---

## 📚 Applications

- RF Receivers
- Software Defined Radio (SDR)
- QAM & PSK Demodulation
- Wireless Communication Systems
- Intermediate Frequency (IF) Signal Processing

---

## 👨‍💻 Authors

- **Anish Toshniwal**
- **Vedant Zope**
- **Kavya Pandey**
