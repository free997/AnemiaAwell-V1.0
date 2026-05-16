[README.md](https://github.com/user-attachments/files/27854593/README.md)
# AnemiaAwell-V1.0# AnemiaAwell V1.0

**Non-Invasive Anemia Screening via Photoplethysmography (PPG) & AI**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Prototype](https://img.shields.io/badge/status-Prototype-orange.svg)](#)

---

## Demo Video

> 🎥 *Video placeholder — a demonstration video covering PPG-based anemia detection principles, AnemiaAwell V1.0 overview, and future directions will be added here.*

---

## 1. PPG-Based Anemia Detection Principle

Conventional hemoglobin testing relies on invasive blood sampling and laboratory infrastructure, creating significant barriers to large-scale anemia screening — especially in resource-limited regions.

AnemiaAwell is built on a core scientific hypothesis grounded in the **Beer-Lambert Law**: reduced hemoglobin concentration markedly alters the light absorption properties of human peripheral tissues. These alterations manifest as distinct variations in the **time-frequency features of photoplethysmography (PPG) signals**. By decoding this correlation mechanism through signal processing and AI algorithms, hemoglobin concentration can be estimated non-invasively from PPG waveforms.

### Key Insight

| Component | Role |
|---|---|
| **Photodetection** | Single-wavelength PPG sensor captures peripheral blood volume pulsations |
| **Signal Processing** | Multi-window weighted fitting filter removes baseline drift and motion artifacts |
| **Feature Extraction** | Nearest-neighbor correlation coefficient screening identifies biomarkers correlated with hemoglobin |
| **Regression Model** | Nonlinear modeling maps PPG features to hemoglobin concentration |

---

## 2. AnemiaAwell V1.0 Overview

### 2.1 Hardware Architecture

AnemiaAwell V1.0 is a prototype device consisting of two core modules:

| Module | Core Components | Approx. Cost |
|---|---|---|
| **Signal Acquisition** | AFE4404 analog front-end + SFH7050 photodetector + STM32 MCU | ~$60 |
| **Model Computing** | Raspberry Pi 4B | ~$90 |
| **Total Prototype Cost** | | **~$150** |

### 2.2 Software & Algorithms

- **PPG Signal Acquisition** — Single-wavelength photodetection unit with real-time signal capture
- **Noise Mitigation** — Multi-window weighted fitting filter algorithm to suppress baseline drift
- **Biomarker Screening** — Novel nearest-neighbor correlation coefficient method extracts core PPG features correlated with hemoglobin levels
- **Prediction Model** — Nonlinear regression model for hemoglobin concentration estimation

### 2.3 Clinical Validation

A small-scale clinical validation was completed using:

- **~200 participants** at Chongqing Ninth People's Hospital
- PPG signals paired with venous blood routine test data
- Additional calibration via open-access datasets

**Result: Hemoglobin prediction relative error < 8.6%**

### 2.4 Repository Structure

```
AnemiaAwell-V1.0/
├── data_csv/          # PPG signal datasets and clinical data
├── model/             # Trained hemoglobin prediction models
├── scipyh_filter/     # Signal processing and filtering algorithms
├── main_headless.py   # Headless inference pipeline
├── precdict.py        # Core prediction module
├── new_data_get.py    # Data acquisition and preprocessing
├── train.py           # Model training scripts
└── test.py            # Evaluation and testing
```

---

## 3. Future Development — AnemiaAwell V2.0

The next-generation AnemiaAwell V2.0 aims to deliver a **low-cost (< $70), non-invasive, intelligent anemia screening product** optimized for deployment in low- and middle-income countries (LMICs).

### 3.1 Hardware Upgrades

- **Three-wavelength PPG** (535nm, 660nm, 940nm) photodetector arrays for robust multi-channel capture
- **Ambient light suppression** and **automatic gain control** for stable signals across diverse skin tones
- **Edge AI chip** replacing Raspberry Pi — low-power, real-time inference
- **Ruggedized design**: LED pulse driving, power-off data protection, dustproof optical windows, shock-resistant enclosures
- **Target cost**: Signal module ~$40 + Edge AI module ~$30 = **< $70 total**

### 3.2 Algorithm Advancements

| Stage | Technique |
|---|---|
| **Biomarker Screening** | Gradient-driven feature selection across spatiotemporal, multi-wavelength fusion, and pulse dynamic features |
| **Regression** | Spatiotemporal fusion deep learning network capturing local waveforms, long-range dependencies, and cross-channel complementarity |
| **Model Lightweighting** | Pruning + knowledge distillation + low-bit quantization → **60–75% parameter reduction** |

### 3.3 Large-Scale Multicenter Validation

Targeting **5,000+ participants** across four continents:

- 🇨🇳 Chongqing Ninth People's Hospital — 2,000 participants
- 🇨🇳 Chongqing Maternal and Child Health Hospital — 1,200 participants
- 🇿🇦 Lentegeur Hospital, South Africa — 1,000 participants
- 🇧🇷 University of São Paulo, Brazil — 800 participants

### 3.4 Target Performance

- **Relative deviation ≤ ±6%**, CV < 2%
- **Result in < 30 seconds**, similar to a finger-clip pulse oximeter
- **< 5 minutes training** for community health workers
- Compliant with **YY/T 0653-2017** (China) and aligned with **CLSI H26** standards

---

## 4. Team

Led by **Prof. Yuan Zhang**, College of Electronic and Information Engineering, Southwest University.

- **3 professors, 2 associate professors, 3 lecturers, 33 postgraduate students**
- **80+ publications** on PPG-based non-invasive detection (anemia, glucose, blood pressure, blood oxygen)
- **10 authorized patents** as first inventor
- **7 national + 8 provincial research projects** led as PI

### International Collaborators

| Collaborator | Institution | Role |
|---|---|---|
| Prof. Xuesheng Ma | University of the Western Cape, South Africa | Clinical Validation |
| Prof. Alan Luiz Eckeli | University of São Paulo, Brazil | Clinical Validation |
| Prof. Zhiyi Huang | University of Otago, New Zealand | System Optimization |
| Prof. Zhiqiang Zhang | University of Leeds, UK | System Optimization |
| Dr. Benny Lo | Imperial College London, UK | System Optimization |

---

## 5. License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

*AnemiaAwell — Breaking the deadlock of anemia prevention and control through accessible, non-invasive screening technology.*
