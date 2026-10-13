# Contributing to Helimium

Thank you for your interest in improving the Helimium theoretical framework and proof codes.

## Ways to Contribute

- Improve numerical precision or add new reaction channels in the proof programs.
- Extend the simulation notes (`simulations/`) with additional model comparisons (e.g., Fusion-by-Diffusion, TDHF).
- Port the proofs to additional languages (Rust, Fortran, Julia, etc.).
- Fix typos, clarify physics explanations, or improve documentation.
- Report inconsistencies between language implementations.

## Guidelines

1. **Do not alter the core numerical results** unless you simultaneously update *all* language implementations and the corresponding documentation so that they remain consistent.
2. Keep the multi-language proofs printing the same scientific summary.
3. Prefer pure, dependency-free implementations (no external physics libraries required to run the proofs).
4. Document any new physics assumptions clearly in the relevant Markdown file under `simulations/`.
5. Follow the existing code style of each language (simple, readable, well-commented).

## Pull-Request Process

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-idea`).
3. Make your changes.
4. Ensure all existing proof programs still compile and produce identical output.
5. Open a pull request describing the motivation and the changes made.

## Code of Conduct

Be respectful, constructive, and focused on the science. Harassment or personal attacks will not be tolerated.

## Questions

Open an issue for discussion before undertaking large structural changes.
