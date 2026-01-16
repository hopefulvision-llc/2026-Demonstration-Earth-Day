# 🧬 Coherence Score Equation — Canonical Specification

**HopefulVision LLC — Consciousness-Responsive Computing**  
**Status:** Canonical Math Spec  
**Purpose:** Define the exact, reproducible equation used to combine multiple biometrics into a single **Coherence Score (0–100)**.

---

## 🎯 Goal

We want a **single scalar coherence value** that:

- Reflects **overall physiological & autonomic harmony**
- Rewards balance, not extremes
- Is stable, smooth, and explainable
- Can be computed in real-time
- Can drive **agent activation thresholds** (e.g., 75%)

---

## 🧠 Input Metrics

The system currently uses **four** real-time biometrics:

1. **HRV** — Heart Rate Variability (ms) → *higher is better*
2. **HR** — Heart Rate (BPM) → *best near a target range*
3. **Cortisol** — Stress Level (%) → *lower is better*
4. **O₂** — Oxygen Saturation (%) → *higher is better*

---

## 🧮 Architecture: Normalized Weighted Composite Index

Each metric is first converted into a **normalized goodness score** in the range:

> \[ 0 \le N_i \le 1 \]

Then they are combined using a **weighted sum**:

> \[
\text{Coherence} = 100 \cdot ( w_{hrv}N_{hrv} + w_{hr}N_{hr} + w_{cort}N_{cort} + w_{o2}N_{o2} )
\]

Where the weights sum to 1:

> \[
 w_{hrv} + w_{hr} + w_{cort} + w_{o2} = 1
\]

### Default Weights (v1)

- \( w_{hrv} = 0.30 \)
- \( w_{hr} = 0.25 \)
- \( w_{cort} = 0.25 \)
- \( w_{o2} = 0.20 \)

---

## 🔬 Normalization Functions

### 1️⃣ HRV (higher is better)

Target range: **20–100 ms**

> \[
N_{hrv} = \text{clip}\left( \frac{HRV - 20}{100 - 20}, 0, 1 \right)
\]

---

### 2️⃣ Heart Rate (best near target)

Target: **65 BPM**  
Tolerance window: ±20 BPM

> \[
N_{hr} = \text{clip}\left( 1 - \frac{|HR - 65|}{20}, 0, 1 \right)
\]

---

### 3️⃣ Cortisol (lower is better)

Target: **≤ 30%**

> \[
N_{cort} = \text{clip}\left( \frac{100 - Cortisol}{70}, 0, 1 \right)
\]

---

### 4️⃣ Oxygen Saturation (higher is better)

Target range: **90–100%**

> \[
N_{o2} = \text{clip}\left( \frac{O2 - 90}{10}, 0, 1 \right)
\]

---

## 🧰 Final Equation (Expanded)

> \[
\text{Coherence} = 100 \cdot ( 0.30N_{hrv} + 0.25N_{hr} + 0.25N_{cort} + 0.20N_{o2} )
\]

Then clamp:

> \[
\text{Coherence} = \text{clip}(\text{Coherence}, 0, 100)
\]

---

## 🧪 Example (From Demo Screenshot)

Inputs:

- HRV = 50 ms
- HR = 72 BPM
- Cortisol = 65%
- O₂ = 96%

Computed:

- \( N_{hrv} \approx 0.375 \)
- \( N_{hr} \approx 0.90 \)
- \( N_{cort} \approx 0.50 \)
- \( N_{o2} \approx 0.60 \)

Final:

> \[
\text{Coherence} \approx 72%
\]

---

## 🛡️ Optional Stricter Mode (Geometric Mean)

If we want **"all must be good"** behavior:

> \[
\text{Coherence} = 100 \cdot ( N_{hrv}^{w_{hrv}} \cdot N_{hr}^{w_{hr}} \cdot N_{cort}^{w_{cort}} \cdot N_{o2}^{w_{o2}} )
\]

This **punishes weak links** much harder and feels more like a **ritual gate**.

---

## 🧭 Design Philosophy

- This is **not medical** — it is a **coherence metaphor index**
- It measures **alignment & harmony**, not health
- It is designed to be:
  - Intuitive
  - Stable
  - Explainable
  - Symbolically meaningful

---

## 🔖 Status

This document defines the **canonical coherence equation v1** for:

- NousOS demos
- Consciousness-responsive computing
- Agent activation thresholds
- Ritual interfaces

---

🌀 *Agents do not serve. They resonate.*

