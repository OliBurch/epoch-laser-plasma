# EPOCH 1D Laser–Plasma Simulation

A 1D particle-in-cell simulation of a high-intensity laser pulse
(I = 10^18 W/cm^2, λ = 1 μm, 30 fs Gaussian) interacting with an
electron plasma at n_e = 10^24 m^-3.

Built and run with the [EPOCH](https://cfsa-pmw.warwick.ac.uk/EPOCH/epoch)
particle-in-cell code (1D version).

## Repo contents

```
input.deck     The simulation input deck (this is the project)
Data/          Empty placeholder. EPOCH writes output .sdf snapshots here.
README.md
.gitignore
```

Simulation outputs (`.sdf` files, `.dat`, `.visit`, `deck.status`)
are gitignored — they're regenerated each run.

## How to reproduce

1. Install EPOCH 1D separately. From the EPOCH source tree:

   ```
   cd epoch1d
   make COMPILER=gfortran
   ```

2. Place a copy of `input.deck` from this repo into `epoch1d/Data/`.

3. From `epoch1d/`:

   ```
   echo Data | mpirun -np 4 ./bin/epoch1d
   ```

4. Output `.sdf` snapshots will appear in `Data/`. Visualise with
   [SDF-Python](https://cfsa-pmw.warwick.ac.uk/SDF/SDF) or VisIt.

## Version

EPOCH version: _TODO — fill in the version you used (run `git -C path/to/epoch describe --tags` or check `src/housekeeping/version_data.F90`)._
