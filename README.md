# photons

Interactive, browser-based photonics simulations for teaching and research.

**Live site:** https://talegre.github.io/photons/

| Simulation | Description |
|---|---|
| [Optical cavity: transmission & bistability](https://talegre.github.io/photons/cavity/) | One- and two-port Fabry–Pérot / ring resonators in temporal coupled-mode theory, with thermo-optic (red shift) or free-carrier dispersion (blue shift) nonlinearity, steady-state branches with stability, and time-domain laser sweeps showing hysteresis. |

Each simulation is a single self-contained HTML file (plain JavaScript, no dependencies), so it also works offline: just open the `index.html` of the folder.

## Model (cavity)

```
da/dt = [ i(ω_l − ω_c(|a|²)) − κ/2 ] a + √κ_e1 α_in,   α_in = √(P_in / ħω_l)
ω_c(|a|²) = ω_c⁽⁰⁾ + δω,   τ dδω/dt = ∓ g |a|^(2p) − δω
κ = κ_i + κ_e1 (+ κ_e2),   α_out,1 = α_in − √κ_e1 a,   α_out,2 = √κ_e2 a
```

Steady state: `|a|²[(Δ − δω(|a|²))² + κ²/4] = κ_e1 |α_in|²` (a cubic in |a|² for p = 1). A solution is stable iff `∂|α_in|²/∂|a|² > 0`.
