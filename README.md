# FaultTolerantQChem

Worked notebooks on **fault-tolerant resource estimation for quantum chemistry**,
using PennyLane's resource-estimation tooling. The focus is the bridge between
classical electronic-structure choices (basis set, active space) and the logical
qubit / Toffoli-gate cost of simulating molecular Hamiltonians via quantum phase
estimation (QPE) under double factorization.

## Contents

- **`01_single_molecule_estimate.ipynb`** — QPE resource estimate for H₂O under
  double factorization: 1-norm, Toffoli count, logical qubits. Includes a
  target-error sweep and an STO-3G vs 6-31G basis comparison.
- **`02_resource_scaling.ipynb`** — How resource cost scales across molecules of
  increasing size (H₂, LiH, H₂O, NH₃).
- **`03_active_space_scan.ipynb`** — How cost scales with active-space size for N₂,
  connecting the classical multireference accuracy/cost tradeoff to fault-tolerant
  circuit cost.

## Key results

Resource cost across molecules (STO-3G):

![Resource scaling](resource_scaling.png)

Resource cost vs active-space size (N₂):

![Active space scaling](active_space_scaling.png)

Representative numbers (H₂O / STO-3G, double factorization):
λ ≈ 53.6, ~1.0 × 10⁸ Toffoli gates, 290 logical qubits.

## Notes

These are resource *estimates* for fault-tolerant QPE — not circuit executions.
Active-space scans use a leading-block truncation of the MO integrals for a
scaling demonstration; physically motivated active-space selection would choose
orbitals deliberately.

## Setup
