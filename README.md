# Multivariate Multicycle Codes For Complete Single Shot Decoding

**Authors:**

Feroz Ahmed Mian, Owen Gwilliam, Stefan Krastanov

---

This repository provides a database of X-type and Z-type **parity check** matrices (`HX`, `HZ`) and **metacheck matrices** for the **Multivariate Multicycle (MM)** family of new quantum error-correcting codes. All matrices are stored in the standard **Matrix Market (`.mtx`) format**, ensuring compatibility with modern tools such as [Stim](https://github.com/quantumlib/Stim).

The dataset can be easily used for running **code distance** algorithms and calculating **confinement profiles** using the [dist‑m4ri](https://github.com/QEC-pages/dist-m4ri) program.

All code instances in this database were generated using [QuantumClifford.jl](https://github.com/QuantumSavory/QuantumClifford.jl). For a comprehensive overview of the Multivariate Multicycle code construction and its subfamilies, please refer to the [MM code documentation](https://qc.quantumsavory.org/dev/ECC_API/#QuantumCliffordOscarExt.MultivariateMulticycle).
