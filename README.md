# Too Soon to Save: Structural Uncertainty Inverts the Value of Precautionary Conservation Action

**Muhammad Umer Gurchani¹\*, José M. Montoya², Sacha Bourgeois-Gironde³⁴**

¹ Institut Jean Nicod (ENS, EHESS, CNRS), École Normale Supérieure, Paris  
² CNRS, Station d'Écologie Théorique et Expérimentale, Moulis  
³ Université Paris 2 Panthéon-Assas, Paris  
⁴ University of Haifa, Faculty of Law, Haifa  
\* Corresponding author: muhammad.gurchani@ens.psl.eu

*Submitted to Nature*

---

## Overview

Conservation policy commonly assumes that acting early is inherently safer than waiting. This repository accompanies a study showing that this intuition can fail when ecological structure is uncertain and protection decisions are difficult to reverse.

We develop a formal framework combining a **Partially Observable Markov Decision Process (POMDP)** with **Inverse Reinforcement Learning (IRL)** from a hindsight teacher to compare:

- **Precautionary strategy** — protect early under uncertainty
- **Adaptive strategy** — learn trophic structure before committing protection

The adaptive strategy yields higher protected-area phylogenetic diversity and functional diversity than the precautionary baseline in synthetic ecosystems, with the advantage largest when structural uncertainty is high and structural importance is decoupled from abundance. Validation uses empirical food-web data from real ecosystems.

---

## Repository Contents

| File | Description |
|------|-------------|
| [`SimulationCodeUploadedVersion.ipynb`](SimulationCodeUploadedVersion.ipynb) | Synthetic ecosystem simulation: POMDP–IRL framework, full policy comparison (adaptive vs. precautionary vs. Marxan vs. oracle), regime analysis, and all simulation figures |
| [`Empirical_Validation_UploadedVersion.ipynb`](Empirical_Validation_UploadedVersion.ipynb) | Empirical validation using real food-web datasets: Spearman/Kendall correlations, cross-ecosystem generalisability, and empirical figures |

Both notebooks are self-contained and reproduce all results and figures reported in the paper.

---

## Requirements

**Python 3.9 or higher** is required.

Install all dependencies with:

```bash
pip install -r requirements.txt
```

### Core dependencies

| Package | Version | Used in |
|---------|---------|---------|
| `numpy` | ≥ 1.24 | Both notebooks |
| `scipy` | ≥ 1.10 | Both notebooks |
| `matplotlib` | ≥ 3.7 | Both notebooks |
| `pandas` | ≥ 2.0 | Both notebooks |
| `networkx` | ≥ 3.1 | Both notebooks |
| `geopandas` | ≥ 0.13 | Empirical notebook only |
| `jupyter` | ≥ 1.0 | Running notebooks |

---

## Running the Code

### 1. Clone the repository

```bash
git clone https://github.com/umergurchani/adaptive-conservation-pomdp.git
cd adaptive-conservation-pomdp
```

### 2. Install dependencies

We recommend using a virtual environment:

```bash
python -m venv venv
source venv/bin/activate        # macOS/Linux
# venv\Scripts\activate         # Windows
pip install -r requirements.txt
```

### 3. Launch Jupyter

```bash
jupyter notebook
```

### 4. Run the notebooks

Open either notebook and run all cells from top to bottom. All figures are generated inline.

**Execution times (standard laptop):**

| Notebook | Approx. runtime |
|----------|----------------|
| `SimulationCodeUploadedVersion.ipynb` | 10–30 minutes (Monte Carlo replicates) |
| `Empirical_Validation_UploadedVersion.ipynb` | 2–5 minutes |

> **Quick test:** In `SimulationCodeUploadedVersion.ipynb`, reduce `N_REPS` in the master `Config` cell (Section 0.1) to a smaller value (e.g., 20) for a fast sanity check.

---

## Data

The empirical validation notebook uses publicly available food-web data loaded directly within the notebook. No separate data download is required.

---

## Reproducibility

All stochastic components use fixed random seeds (set in the `Config` dataclass of each notebook). Running the notebooks end-to-end reproduces the exact numerical results and figures reported in the paper.

---

## Citation

If you use this code, please cite:

```bibtex
@article{gurchani2025toosoon,
  title     = {Too Soon to Save: structural uncertainty inverts the value of precautionary conservation action},
  author    = {Gurchani, Muhammad Umer and Montoya, Jos{\'e} M. and Bourgeois-Gironde, Sacha},
  journal   = {Nature},
  year      = {2025},
  note      = {Under review}
}
```

---

## License

This code is released under the MIT License. See [LICENSE](LICENSE) for full terms.

---

## Contact

For questions about the code or analysis, contact **Muhammad Umer Gurchani** at muhammad.gurchani@ens.psl.eu.
