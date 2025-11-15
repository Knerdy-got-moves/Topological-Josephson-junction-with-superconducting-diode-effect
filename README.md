# Topological Josephson Junction with Superconducting Diode Effect

A computational physics project reproducing results from the paper ["Superconducting diode effect in quantum spin Hall insulator based Josephson junctions"](https://doi.org/10.1103/PhysRevB.110.134511) published in Physical Review B.

## Overview

This project implements numerical calculations to study the **superconducting diode effect** in Josephson junctions based on quantum spin Hall insulators (QSHI). The diode effect manifests as a nonreciprocal critical current, where the maximum supercurrent depends on its direction—a key property for developing superconducting diodes and other quantum electronic devices.

### Key Physics Concepts

- **Quantum Spin Hall Insulator (QSHI)**: A topological insulator with helical edge states where spin and momentum are locked
- **Josephson Junction**: A weak link between two superconductors that enables supercurrent flow
- **Andreev Bound States (ABS)**: Discrete energy levels formed in the junction due to Andreev reflection
- **Superconducting Diode Effect**: Asymmetric critical current depending on current direction, quantified by the quality factor Q

## Features

The Jupyter notebook provides comprehensive calculations and visualizations for:

1. **Andreev Bound State Spectrum**
   - Energy dispersion as a function of superconducting phase difference
   - Analysis for different Doppler shift parameters (γ)

2. **Density of States**
   - Phase-dependent continuum density of states via the Friedel relation
   - Contribution from both subgap states and continuum

3. **Josephson Current**
   - Current-phase relationships including both ABS and continuum contributions
   - Temperature dependence analysis
   - Comparison with and without fermion parity constraints

4. **Quality Factor Analysis**
   - Quantification of the diode effect: Q = (|I⁺| - |I⁻|)/I₀
   - Temperature and magnetic field dependence
   - Effect of parity conservation

## Physics Model

### Hamiltonian

The system is described by a Bogoliubov-de Gennes (BdG) Hamiltonian for a S-QSHI-S junction:

```
Ĥ = (σ vF p̂x - μS)τz + vF pS/2 + V₀h(x)τz + Δ(x)[τx cos φ(x) - τy sin φ(x)]
```

Key parameters:
- `vF`: Fermi velocity
- `μS`: Chemical potential
- `pS`: Doppler shift momentum from orbital magnetic field
- `Δ`: Superconducting gap
- `φ`: Superconducting phase difference

### Key Results

The Josephson current splits into two contributions:

**1. Andreev Bound State Current:**
```
I_ABS = I₀ sin(φ/2) tanh[Δ̄(cos(φ/2) - σγ sgn(sin(φ/2)))]
```

**2. Continuum Current:**
Computed via numerical integration of the density of states

The **quality factor** Q quantifies the diode effect strength and depends on temperature and the dimensionless parameter γ = vF pS/(2Δ).

## Installation & Usage

### Prerequisites

```bash
pip install numpy scipy matplotlib tqdm jupyter
```

### Running the Notebook

#### Option 1: Google Colab (Recommended)
Click the badge below to open directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Knerdy-got-moves/Topological-Josephson-junction-with-superconducting-diode-effect/blob/main/Codes_and_links_to_theory_on_SDE_in_QSHI_based_JJ.ipynb)

#### Option 2: Local Jupyter
```bash
git clone https://github.com/Knerdy-got-moves/Topological-Josephson-junction-with-superconducting-diode-effect.git
cd Topological-Josephson-junction-with-superconducting-diode-effect
jupyter notebook Codes_and_links_to_theory_on_SDE_in_QSHI_based_JJ.ipynb
```

## Notebook Structure

1. **Hamiltonian Setup** - BdG formulation in Nambu spinor basis
2. **Andreev Bound States** - Energy spectrum calculations and visualization
3. **Density of States** - Continuum contribution via scattering matrix approach
4. **Josephson Current** - Combined ABS and continuum current calculations
5. **Quality Factor** - Diode effect analysis at various temperatures
6. **Parity Constraint Effects** - Advanced analysis including fermion parity conservation

## Theoretical Background

The notebook includes references to detailed theoretical notes covering:
- Full Hamiltonian derivation
- Boundary condition treatment
- Scattering matrix formalism
- Free energy calculations

Access the theoretical notes linked within the notebook for complete derivations.

## Current Status

**Completed:**
- ✅ Andreev bound state calculations
- ✅ Density of states computations
- ✅ Josephson current analysis (without parity constraint)
- ✅ Quality factor calculations and temperature dependence
- ✅ Initial parity constraint implementation

**In Progress:**
- ⚙️ Full parity constraint implementation refinement
- ⚙️ Enhanced numerical accuracy for quality factor at low temperatures

## Visualization Examples

The notebook generates several key plots:
- Energy band structure vs. phase for different γ values
- Density of states contour plots
- Josephson current as a function of phase and magnetic field
- Quality factor Q vs. γ for multiple temperatures
- Comparison of currents with/without parity constraints

## Citation

If you use this code, please cite the original paper:

```bibtex
@article{PhysRevB.110.134511,
  title = {Superconducting diode effect in quantum spin Hall insulator based Josephson junctions},
  journal = {Physical Review B},
  volume = {110},
  pages = {134511},
  year = {2024},
  doi = {10.1103/PhysRevB.110.134511}
}
```

## License

This project is provided for educational and research purposes. Please refer to the original paper for scientific content.

## Author

Repository maintained by [Knerdy-got-moves](https://github.com/Knerdy-got-moves)

## Acknowledgments

- Original paper authors for the theoretical framework
- Physics community for discussions on topological superconductivity
- Google Colab for computational resources

---

**Note:** Some numerical implementations show minor deviations from the original paper plots due to discretization choices and computational efficiency trade-offs. These are primarily visible in the quality factor calculations at low temperatures with sparse grid points.
