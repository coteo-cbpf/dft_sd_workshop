# 🧲 Spin Dynamics Workshop (Python + Jupyter)

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/coteo-cbpf/dft_sd_workshop/main?labpath=notebook-sd%2Fspin_dynamics_workshop_tutorial.ipynb)

Welcome! This repository contains a **hands-on, step-by-step workshop** where students build an **atomistic spin-dynamics** code from scratch in **Python** and run it in a **Jupyter Notebook** with **interactive visualization**.

The notebook is written to be *didactic*: each routine is implemented, explained, and immediately tested with small checks and plots.

---

## ✨ What’s inside

### Core physics (in code)
We work with classical unit spins $\mathbf{S}_i$ (normalized: $|\mathbf{S}_i|=1$) and implement:

- **Exchange** $$J_{ij}$$
- **DMI** $$\mathbf{D}_{ij}$$
- **Zeeman field** $$\mathbf{B}$$ (external field)

A typical Hamiltonian used in the workshop is:

$$
E = -\sum_{i<j} J_{ij}\,\mathbf{S}_i\cdot\mathbf{S}_j
    -\sum_{i<j} \mathbf{D}_{ij}\cdot(\mathbf{S}_i\times\mathbf{S}_j)
    -\sum_i \mathbf{B}\cdot \mathbf{S}_i
$$

Then we compute the effective field
$\mathbf{H}_i^{\mathrm{eff}} = -\partial E/\partial \mathbf{S}_i$
and integrate the **Landau–Lifshitz–Gilbert (LLG)** equation using a stable **predictor–corrector (Heun) integrator**.

---

## 📘 Notebook (main content)

**Main notebook:**
- `spin_dynamics_workshop_python_routine_by_routine_*.ipynb`

It contains routine-by-routine implementations and three examples:

### ✅ Example 01 — Nanochain
A minimal system to introduce:
- reading/generated inputs
- effective field computation
- LLG update loop
- interactive 3D visualization of spins

### ✅ Example 02 — Square lattice skyrmion (20×20, PBC) + Zeeman field
A more advanced example focusing on:
- 2D lattice + **periodic boundary conditions (PBC)**
- interfacial DMI and field stabilization
- seeded skyrmion initialization vs random initialization
- side-by-side **top views** (field vs no-field)

### ✅ Example 03 — Kagomé lattice (PBC) and non-collinear order
A non-collinear example designed to highlight:
- frustration / geometry effects
- angle diagnostics between spins
- visualization of non-collinear textures

---

## 🚀 Quick start

### 1) Install dependencies
We recommend Python **3.10+**.

#### Option A — pip (simple)
```bash
pip install numpy pandas matplotlib tqdm ipympl
```

#### Option B — conda (clean environment)
```bash
conda create -n spin-dyn python=3.11 -y
conda activate spin-dyn
pip install numpy pandas matplotlib tqdm ipympl
```

### 2) Enable interactive plots (classic Jupyter Notebook)
Usually one-time:
```bash
jupyter nbextension enable --py --sys-prefix ipympl
```

### 3) Run the notebook
```bash
jupyter notebook
```

Open the main notebook and run **top-to-bottom**.

### 🔗 Launch individual notebooks on Binder

You can open any notebook in this repository directly on Binder using the links below (launched from `aibergman/dft_sd_workshop`, branch `uppasd_notebooks`).

#### DFT
- [notebook-dft/dft_notebook.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-dft%2Fdft_notebook.ipynb)

#### LLG + Python
- [notebook-sd/spin_dynamics_workshop_tutorial.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-sd%2Fspin_dynamics_workshop_tutorial.ipynb)

#### UppASD
- [notebook-uppasd/Skyrmion_Interactive.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FSkyrmion_Interactive.ipynb)
- [notebook-uppasd/UppASD_bccFe_thermo.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FUppASD_bccFe_thermo.ipynb)
- [notebook-uppasd/UppASD_bccFe.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FUppASD_bccFe.ipynb)
- [notebook-uppasd/J1J2J3_exchange.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FJ1J2J3_exchange.ipynb)
- [notebook-uppasd/CBPFTutorial.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FCBPFTutorial.ipynb)
- [notebook-uppasd/Skyrmion_Lattice.ipynb](https://mybinder.org/v2/gh/aibergman/dft_sd_workshop/uppasd_notebooks?urlpath=%2Flab%2Ftree%2Fnotebook-uppasd%2FSkyrmion_Lattice.ipynb)

---

### ☁️ Open selected notebooks on Google Colab

You can open the same selected notebooks directly in Google Colab (runs on Colab VMs). These links use the `aibergman/dft_sd_workshop` repository and the `uppasd_notebooks` branch.

#### DFT
- [notebook-dft/dft_notebook.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-dft/dft_notebook.ipynb)

#### LLG + Python
- [notebook-sd/spin_dynamics_workshop_tutorial.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-sd/spin_dynamics_workshop_tutorial.ipynb)

#### UppASD
- [notebook-uppasd/Skyrmion_Interactive.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/Skyrmion_Interactive.ipynb)
- [notebook-uppasd/UppASD_bccFe_thermo.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/UppASD_bccFe_thermo.ipynb)
- [notebook-uppasd/UppASD_bccFe.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/UppASD_bccFe.ipynb)
- [notebook-uppasd/J1J2J3_exchange.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/J1J2J3_exchange.ipynb)
- [notebook-uppasd/CBPFTutorial.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/CBPFTutorial.ipynb)
- [notebook-uppasd/Skyrmion_Lattice.ipynb](https://colab.research.google.com/github/aibergman/dft_sd_workshop/blob/uppasd_notebooks/notebook-uppasd/Skyrmion_Lattice.ipynb)

## 📬 Contact
For questions or suggestions, feel free to reach out: **ramon.cardias@cbpf.br**
