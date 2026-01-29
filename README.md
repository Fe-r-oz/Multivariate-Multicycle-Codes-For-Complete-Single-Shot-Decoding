# Multivariate Multicycle Codes For Complete Single Shot Decoding

**Authors:**

Feroz Ahmed Mian, Owen Gwilliam, Stefan Krastanov

---

This repository provides a database of X-type and Z-type **parity check** matrices (`HX`, `HZ`) and **metacheck matrices** for the **Multivariate Multicycle (MM)** family of new quantum error-correcting codes. All matrices are stored in the standard **Matrix Market (`.mtx`) format**, ensuring direct usage with modern tools such as [Stim](https://github.com/quantumlib/Stim).

The dataset can be directly used for running **code distance** algorithms and calculating **confinement profiles** using the [dist‑m4ri](https://github.com/QEC-pages/dist-m4ri) program.

All code instances in this database were generated explicitly using [QuantumClifford.jl](https://github.com/QuantumSavory/QuantumClifford.jl). For a comprehensive overview of the Multivariate Multicycle code construction and its subfamilies, please refer to the [MM code documentation](https://qc.quantumsavory.org/dev/ECC_API/#QuantumCliffordOscarExt.MultivariateMulticycle).

## Confinement Profile Computation using [dist‑m4ri](https://github.com/QEC-pages/dist-m4ri) 

A convenient method to compute confinement is using Google Colab. Here is a simple guide:

### Install Dependencies and Clone [dist‑m4ri](https://github.com/QEC-pages/dist-m4ri) Program

```bash
!apt-get update
!apt-get install -y libm4ri-dev build-essential git
!git clone https://github.com/QEC-pages/dist-m4ri.git
%cd dist-m4ri/src
!make dist_m4ri
```

### Verify Installation

```bash
!ls -l dist_m4ri
!./dist_m4ri --help
```

### Find Installation Path of [dist‑m4ri](https://github.com/QEC-pages/dist-m4ri) Program

```bash
%%bash
find /content -name dist_m4ri 2>/dev/null
```

## Running Confinement Computation

Once installed, navigate to your QEC code directory and run the computation:

```bash
%%bash
cd "/content/drive/MyDrive/QEC_CODE"
DIST="/content/dist-m4ri/src/dist_m4ri" # Example path
HZ="MM_96_12_4_HZ.mtx"
echo "Using dist-4mri:"
ls -l "$DIST"
$DIST method=2 finH="$HZ" wmax=6
```

### Output

```bash
Using dist-4mri:
-rwxr-xr-x 1 root root 229688 Jan 29 05:56 /content/dist-m4ri/src/dist-m4ri/src/dist_m4ri
# read H <- file 'MM_96_12_4_HZ.mtx'
# recursively searching for w=1 codewords wmax=6 beg=0 end=95
# recursively searching for w=2 codewords wmax=6 beg=0 end=94
# recursively searching for w=3 codewords wmax=6 beg=0 end=93
# recursively searching for w=4 codewords wmax=6 beg=0 end=92
# w=1 min non-zero syndrome weight 8
# w=2 min non-zero syndrome weight 8
# w=3 min non-zero syndrome weight 8
# w=4 min non-zero syndrome weight 8
### Cluster (actual min-weight codeword found): d=4
```

### And

```bash
%%bash
cd "/content/drive/MyDrive/mm_codes"
DIST="/content/dist-m4ri/src/dist-m4ri/src/dist_m4ri"
HZ="MM_96_12_4_HZ.mtx"
echo "Using binary:"
ls -l "$DIST"
$DIST method=2 finH="$HZ" wmax=6 debug=0
```

### Output

```bash
Using binary:
-rwxr-xr-x 1 root root 229688 Jan 29 05:56 /content/dist-m4ri/src/dist-m4ri/src/dist_m4ri
# confinement: 8,8,8,8,
4 # code distance 
```

## Citation

In any publication or work that utilizes this database, please cite the following.

```latex
@misc{mian2026multivariatemulticyclecodescomplete,
      title={Multivariate Multicycle Codes for Complete Single-Shot Decoding}, 
      author={Feroz Ahmed Mian and Owen Gwilliam and Stefan Krastanov},
      year={2026},
      eprint={2601.18879},
      archivePrefix={arXiv},
      primaryClass={quant-ph},
      url={https://arxiv.org/abs/2601.18879}, 
}
```
