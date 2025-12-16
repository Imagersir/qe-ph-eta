# Patch for Quantum ESPRESSO 7.3: QE-PH-Eta

This repository provides a **patch** for **Quantum ESPRESSO (QE) version 7.3**
that implements a new feature for the circularly polarized phonon magnetic effect (primarily targeting the phonon Zeeman energy in magnetic materials) based on the DFPT method.

This code is intended for **research and reproducibility purposes**.
The emphasis of this repository is on **installation and usage**, rather than
software development details.

---

## Base software

- Quantum ESPRESSO version: **7.3**

⚠️ This patch is guaranteed to apply **only** to the QE 7.3 release.

---

## What this patch provides

- Enables:
  - [Feature / physical capability]


Implementation details are intentionally omitted.

---

## Quick start

### Installation

```bash
cd /path/to/qe-7.3
patch -p1 < /path/to/ph-eta.patch
./configure
make all
```

### Minimal Input (for ph.x)
```vim
&inputph
  prefix = 'Material'
  outdir = './'
  fildvscf = 'dvscf'
  fildyn = 'Material.dyn'
  ldisp = .true.
  el_ph_sigma = 0.001
  el_ph_nsigma = 10
  qplot = .true.
  q_in_band_form = .true.
  electron_phonon = 'interpolated'
 /
 1 ! nqs
 0.00000000 0.00000000 0.00000000 1 # Gamma
```
