# Compositional-Data-Analysis-to-Basis-Data
Tatsuki Itagaki's Code of Beliefs and Estimation of Basis Data
# 🚀 ULTIMATE COMPOSITIONAL DECONVOLUTION ENGINE
### Methodology: Ohta (2011) CV-Asymmetry + VLR-Purity + Dynamic Poisson Floor
**Engine:** Pure Base R (Zero External Dependencies)  
**Author:** Tatsuki Itagaki

---

## 📌 Overview
This engine provides a high-fidelity analytical framework to overcome the **"Compositional Closure"** problem. It reconstructs absolute scaling factors (Relative Total Mass) from relative abundance data without the need for physical spike-ins.

### ⚖️ The Scientific Beliefs
> "Physical standards (Spike-ins) are often just new sources of noise. The true reference does not come from outside; it exists within the data—the component that has endured the entire process of sampling, extraction, and sequencing, yet remained statistically motionless. This is the **Natural Internal Standard**."

---

## 🛠 Key Mathematical Pillars

1.  **Ohta (2011) CV-Asymmetry (Win Count):** 
    A non-parametric statistical approach that identifies the best denominator (Anchor) by comparing forward and inverse Coefficient of Variation (CV) ratios. It minimizes error propagation during deconvolution.
2.  **Dynamic Poisson Floor (Invariance Ratio - IR):** 
    Dynamically estimates the physical noise limit based on your actual data density. An **IR near 1.0** mathematically proves that a taxon has reached the theoretical limit of stability (Sampling Noise only).
3.  **Geometric Purity Index (PI):** 
    Utilizes the Aitchison **Variation Matrix (VLR)** to find the geometric center of the compositional simplex, ensuring the anchor selection is independent of total sum fluctuations.
4.  **95% Bootstrap Confidence Intervals:** 
    1,000 iterations quantify the uncertainty of the deconvolution, visualizing the robustness of the mass reconstruction for every single sample.

---

## 📊 Evaluation Metrics

*   **IR (Invariance Ratio):** *Physical Stability.* The lower the IR, the closer the taxon is to the "Unmovable Point" of the physical world.
*   **PI (Purity Index):** *Geometric Stability.* Identifies the most "pure" reference point that reflects the bulk scaling of the system.
*   **Win Count:** *Statistical Stability.* The "Winner" that minimizes the variance of all other components when used as a denominator.

---

## 🚀 Usage

1.  **Data Input:** Prepare your `Dataset` in R (Rows = Samples, Cols = Taxa/Metabolites) as a proportion matrix (Sum per row = 1).
2.  **Strict Filtering:** The engine applies a user-defined threshold (default: 0.00001) to ensure no zero-substitution bias interferes with the log-variance.
3.  **Analysis:** Run the script to generate three independent stability plots.
4.  **Selection:** The taxon with the **lowest IR, highest PI/Win, and shortest error bars** is your absolute anchor for deconvolution.

---

## 📈 Output Interpretation
*   **Scaling Factor:** The Y-axis of the generated plots represents the multiplier required to restore each sample's relative absolute mass.
*   **Signal Classification:** Automatically categorizes taxa into **PHYSICAL NOISE** (Ideal Anchors), **PRACTICAL PROXIES**, or **BIOLOGICAL SIGNALS**.
