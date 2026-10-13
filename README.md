# Helimium

**Element 119 — Helimium (Hl)**

Theoretical synthesis framework and multi-language executable proofs for the cold/hot fusion reaction:

```text
249Bk (Z=97) + 50Ti (Z=22)  →  299Hl*  →  295Hl + 4n
```

This repository contains:

- Physics notes and simulation write-ups (`simulations/`)
- Multi-language proof codes that reproduce the same numerical results (`src/helimium_proof/`)

The calculations are based on the **Dinuclear System Model (DNS)** coupled to **Fluctuation-Dissipation (Langevin) dynamics**.

## Key Proven Results

| Quantity                              | Value              |
|---------------------------------------|--------------------|
| Static Coulomb barrier (c.m.)         | 236.0 MeV          |
| Dynamical barrier (after deformation) | 228.0 MeV          |
| Optimal centre-of-mass energy         | 242.5 MeV          |
| **Optimal laboratory beam energy**    | **291.2 MeV**      |
| Compound-nucleus excitation \(E^*\)   | 38.4 MeV           |
| Neutrons evaporated                   | **exactly 4**      |
| Residual isotope                      | \(^{295}\mathrm{Hl}\) (N=176) |
| \(^{249}\mathrm{Bk}\) half-life       | 330 days           |
| Predicted ER cross-section range      | 35–55 fb           |

## Repository Structure

```text
Helimium/
├── README.md                 ← you are here
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── simulations/
│   ├── helimium_v0.1.md
│   └── helium_v0.2.md
└── src/
    └── helimium_proof/
        ├── helimium.py       # Python 3
        ├── helimium.cpp      # C++
        ├── Helimium.java     # Java
        ├── helimium.c        # C
        ├── helimium.asm      # x86-64 NASM Assembly
        ├── README.md         # language-specific build notes
        └── (compiled binaries / class files)
```

## Quick Start – Run the Proofs

```bash
# Python
python3 src/helimium_proof/helimium.py

# C++
g++ -O2 -o helimium_cpp src/helimium_proof/helimium.cpp -lm
./helimium_cpp

# Java
javac src/helimium_proof/Helimium.java
java -cp src/helimium_proof Helimium

# C
gcc -O2 -o helimium_c src/helimium_proof/helimium.c -lm
./helimium_c

# Assembly (requires NASM)
nasm -f elf64 src/helimium_proof/helimium.asm -o helimium.o
ld helimium.o -o helimium_asm
./helimium_asm
```

All implementations print the **identical** scientific summary, demonstrating language-independent consistency of the DNS + Langevin results.

## Physics Background

The framework replaces simplified textbook approximations (plain WKB + Fermi-gas level density) with:

1. **Dinuclear System Model** – driving potential in the mass-asymmetry and deformation coordinates.
2. **Langevin fluctuation-dissipation equations** – stochastic trajectories that determine the competition between complete fusion and quasi-fission.
3. Microscopic sequential neutron evaporation with temperature-dependent fission barriers.

Optimal beam energy maximises the product \(P_\mathrm{CN} \times W_\mathrm{sur}\).

## License

See [LICENSE](LICENSE).

## Disclaimer

Helimium is a theoretical construct. No atoms of element 119 have been experimentally confirmed as of the creation of this repository. The codes and notes are provided for educational and research-discussion purposes.
