# 2D Ising Model Simulation

Many physical systems have a critical point where they undergo 
a phase transition, like water turning to ice or iron losing 
its magnetism above a certain temperature. For this project we simulated the 2D Ising 
model using the Metropolis-Hastings algorithm to study exactly 
this kind of behavior and see if we could recover the critical 
exponents from our own simulated data.

The interesting thing about critical exponents is that completely 
unrelated physical systems can share the same ones, a concept 
called universality. So what we measured in this simple spin 
lattice model actually applies to a much broader class of systems 
in nature.

We were able to reproduce the critical temperature Tc ≈ 2.269 
and get pretty close to the theoretical critical exponents 
(β = 1/8 and δ = 15). Our β came out to 0.1286 ± 0.0030 which 
is really close. Our δ was off by more, likely because we were 
limited by lattice size and computational resources on a laptop.

The hardest part for me was getting up to speed on the physics 
side of things. Alex handled most of the statistical analysis 
for the critical exponents while I focused on building the 
simulation and setting up the repository. We wrote a full paper 
on the project which is included in the repo.

## What's in this repo

| File | Description |
|------|-------------|
| 01_simulate_ising.ipynb | Run the MCMC simulation, generate data and figures |
| 02_load_and_explore.ipynb | Load saved data and reproduce analysis plots |
| 03_critical_exponents.ipynb | Fit critical exponents β and δ |
| Physic88_Final_Project.ipynb | Full combined project notebook |
| ising_data.npz | Pre-computed simulation output (temperature sweep) |
| ising_delta_data.npz | Pre-computed simulation output (field sweep at Tc) |
| phase_transition.png | Magnetization vs temperature plot |
| burnin_convergence.png | Burn-in diagnostic |
| lattice_snapshots.png | Lattice snapshots at T = 1.0, Tc, 3.5 |

## How to run

Runs out of the box on UC Berkeley Datahub.

```bash
git clone https://github.com/edenmhuang/Physic-77-88-Simulating-2D-Ising-Model.git
```

Run the notebooks in order — or skip notebook 01 entirely 
since the pre-computed .npz files are already included.

## Results

- β = 0.1286 ± 0.0030 (theoretical: 0.125) ✅
- δ = 17.3998 ± 0.0687 (theoretical: 15) — off due to 
  finite lattice size limitations

## Tech Stack

Python, NumPy, Matplotlib, SciPy

## Team

Built by Eden Huang and Alex Halpin
Physics 77/88 Final Project · UC Berkeley · Spring 2026

We thank GSI Harper Sewalls and Professor Ma for their 
guidance on this project.
