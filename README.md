# ecolienz
Computational validation of nanozyme-enhanced metabolic rescue for chronic wound healing — using COBRApy FBA/FVA on the E. coli core model to simulate hypoxia, model catalytic nanozyme intervention, and demonstrate restoration of ATP production and redox balance.
# AKE NanoHeal — Nanozyme Metabolic Rescue Simulator


---

## 🧬 Overview

Chronic wounds fail to heal not because of missing growth signals, but due to **metabolic collapse** — elevated ROS, hypoxia, impaired ATP production, and redox imbalance. This project proposes a **nanozyme-based therapeutic strategy** and computationally validates it using genome-scale metabolic modeling.

We use **COBRApy** (Constraint-Based Reconstruction and Analysis in Python) to simulate:
1. Normal E. coli metabolic flux as a cellular proxy
2. Hypoxic wound conditions (restricted O₂ uptake)
3. Nanozyme intervention (relaxed ATP synthase, NADH dehydrogenase, and transhydrogenase constraints)

**Key Results:**
- Hypoxia drops biomass flux to `~0.21`
- Nanozyme simulation restores it to `~0.83`
- FVA shows significantly expanded flux ranges for `ATPS4r` (~42) and `NADH16` (~36)

---

## 🧪 Scientific Background

| Component | Role |
|----------|------|
| `EX_o2_e` | Oxygen exchange — simulates hypoxia by restricting uptake |
| `ATPS4r` | ATP Synthase — models enhanced energy production via nanozymes |
| `NADH16` | NADH Dehydrogenase — restores electron transport, NAD⁺/NADH cycling |
| `NADTRHD` | Transhydrogenase — maintains redox homeostasis |

The nanozyme is modeled as a **Mn-doped akermanite (Ca–Mg–Si) bioceramic** with catalase-like activity, converting H₂O₂ → O₂ + H₂O and restoring intracellular redox balance.

---

## 🛠️ Tools Used

- `cobra` / `cobrapy` — FBA and FVA on E. coli core model
- `matplotlib` — Visualization of biomass and flux variability
- `numpy` — Numerical array operations
- `scipy` — Scientific computation support
- `conda` (Miniconda) — Environment management
- IPython / Windows Terminal — Interactive development

---

## ⚙️ Installation

```bash
conda create -n nanoheal python=3.10
conda activate nanoheal
pip install cobra matplotlib numpy scipy
```

---

## 🚀 Usage

```bash
python nanozyme_fba.py
```

This will:
- Load the E. coli core COBRA model
- Run FBA under normal, hypoxic, and nanozyme conditions
- Run FVA and compare flux variability
- Generate two plots: **Biomass Comparison** and **FVA Flux Flexibility Comparison**

---

## 📊 Outputs

| Plot | Description |
|------|-------------|
| `FBA: Biomass Comparison` | Bar chart — Hypoxia vs Normal vs Nanozyme biomass flux |
| `FVA: Flux Flexibility Comparison` | Error bar chart — flux ranges for key reactions |

---

## 📚 References

- Wang X et al. *Nanozymes: next wave of artificial enzymes.* Chemical Society Reviews, 2019.
- Sen CK. *Wound healing essentials: let there be oxygen.* Wound Repair and Regeneration, 2009.
- Liu, Y., Lim, J., & Teoh, S.-H. (2013). *Development of clinically relevant scaffolds for vascularised bone tissue engineering.* Biotechnology Advances, 31(5), 688–705.
- Kothandam S, Swamiappan S. *Synthesis, characterization, and in vitro bioactivity, mechanical strength of silver doped akermanite bioceramic.* Inorganic Chemistry Communications. 2023;148:110347
