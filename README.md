| Ordered (T = 1.0) | Critical (T ≈ 2.269) | Disordered (T = 3.5) |
|---|---|---|
| ![T=1.0](equil_T1.gif) | ![T=2.269](equil_critical.gif) | ![T=3.5](equil_T3_5.gif) |

# 2D Ising Model — Monte Carlo Simulation & Critical Phenomena

A computational physics project simulating the 2D Ising model using the **Metropolis–Hastings algorithm** to study the ferromagnetic phase transition. Reproduces the critical temperature **Tc ≈ 2.269** (in units of J/kB) and generates figures for the accompanying report.

## Quickstart (UC Berkeley Datahub)

1. Open [Datahub](https://datahub.berkeley.edu) and start a Python 3 server.
2. Clone this repository:
```bash
   git clone https://github.com/edenmhuang/Physic-77-88-Simulating-2D-Ising-Model.git
   cd Physic-77-88-Simulating-2D-Ising-Model
```
3. Open **`01_simulate_ising.ipynb`** and run all cells (Kernel → Restart & Run All).
4. Open **`02_load_and_explore.ipynb`** and run all cells to reproduce the analysis plots.

> **Tip:** Step 3 takes ~5–10 minutes. You can skip it — `ising_data.npz` is already included in the repo. Just go straight to step 4.

---

## Reproducing Figures

| Figure | Notebook | Output file |
|---|---|---|
| Phase transition \|M\| vs T | `01_simulate_ising.ipynb` | `phase_transition.png` |
| Burn-in convergence | `01_simulate_ising.ipynb` | `burnin_convergence.png` |
| Lattice snapshots | `01_simulate_ising.ipynb` | `lattice_snapshots.png` |
| Equilibration GIFs | `01_simulate_ising.ipynb` | `equil_T1.gif`, `equil_critical.gif`, `equil_T3_5.gif` |
| Analysis plots (Cv, χ, fits) | `02_load_and_explore.ipynb` | inline in notebook |

---

## Simulation Parameters

Key parameters are set at the top of `01_simulate_ising.ipynb`:

```python
N        = 50    # Lattice size (N × N)
BURNIN   = 250   # Burn-in sweeps discarded before measurement
N_MEAS   = 500   # Measurement sweeps per temperature
N_TRIALS = 3     # Independent trials averaged per temperature
B        = 0.0   # External magnetic field (zero-field)
```

---

## Data

`ising_data.npz` contains pre-computed arrays:

| Key | Description |
|---|---|
| `T_range` | Temperature values (40 points, denser near $T_c$) |
| `mean_M_arr` | Mean absolute magnetization \|M\| |
| `std_M_arr` | Std of \|M\| across trials |
| `mean_E_arr` | Mean energy per spin |
| `std_E_arr` | Std of energy across trials |
| `mean_Cv` | Heat capacity $C_v$ |
| `mean_chi` | Magnetic susceptibility $\chi$ |

---

## Environment

- **Python:** 3.9.6
- **Packages:** `numpy`, `matplotlib`, `scipy`

Runs out-of-the-box on UC Berkeley Datahub with no additional setup.
