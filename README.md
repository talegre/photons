# photons

Interactive, browser-based photonics simulations for teaching and research.

**Live site:** https://talegre.github.io/photons/

| Simulation | Description |
|---|---|
| [Optical cavity: transmission & bistability](https://talegre.github.io/photons/cavity/) | One- and two-port Fabry–Pérot / ring resonators in temporal coupled-mode theory, with thermo-optic (red shift) or free-carrier dispersion (blue shift) nonlinearity, steady-state branches with stability, and time-domain laser sweeps showing hysteresis. |
| [Cavity optomechanics: transduction & backaction](https://talegre.github.io/photons/optomechanics/) | Linearized optomechanics with direct detection on an ESA: transduction vs detuning (resolved/unresolved sideband), dependence on g₀, Ω_m, T and T_eff, thermal bistability during laser sweeps, PSD (dBm) → displacement calibration, optical spring/damping vs power, sideband cooling limit and OMIT/OMIA. Conventions of Aspelmeyer, Kippenberg & Marquardt, RMP 86, 1391 (2014). |

Each simulation is a single self-contained HTML file, so it also works offline: just open the `index.html` of the folder. The cavity page is plain JavaScript; the optomechanics page has Plotly.js (MIT license) inlined, which is why it is ~4.5 MB.

## Model (cavity)

```
da/dt = [ i(ω_l − ω_c(|a|²)) − κ/2 ] a + √κ_e1 α_in,   α_in = √(P_in / ħω_l)
ω_c(|a|²) = ω_c⁽⁰⁾ + δω,   τ dδω/dt = ∓ g |a|^(2p) − δω
κ = κ_i + κ_e1 (+ κ_e2),   α_out,1 = α_in − √κ_e1 a,   α_out,2 = √κ_e2 a
```

Steady state: `|a|²[(Δ − δω(|a|²))² + κ²/4] = κ_e1 |α_in|²` (a cubic in |a|² for p = 1). A solution is stable iff `∂|α_in|²/∂|a|² > 0`.
