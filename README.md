# photons

Interactive, browser-based photonics simulations for teaching and research.

**Live site:** https://talegre.github.io/photons/

| Simulation | Description |
|---|---|
| [Optical cavity: thermal shift (simple)](https://talegre.github.io/photons/cavity-simple/) | Streamlined 16:9 teaching version that scales to fit any window, so it can be embedded in a PowerPoint slide (Web Viewer 2.0 add-in). Cold vs. heated cavity spectrum on fixed axes, values labeled on the drawing, symmetric two-port option, keyboard shortcuts (C cycle, Space pause, R clear). |
| [Optical cavity: transmission & bistability](https://talegre.github.io/photons/cavity/) | One- and two-port Fabry–Pérot / ring resonators in temporal coupled-mode theory, with thermo-optic (red shift) or free-carrier dispersion (blue shift) nonlinearity, steady-state branches with stability, and time-domain laser sweeps showing hysteresis. |
| [Optomechanics in six steps (animated intro)](https://talegre.github.io/photons/optomechanics-intro/) | Animated teaching version: a mirror on a spring integrated in real time (full nonlinear equations, dimensionless units). Six guided steps: resonance tuning, transduction, delayed radiation-pressure force and the force–position work loop, cooling, self-oscillation, resolved sidebands. |
| [Cavity optomechanics: transduction & backaction](https://talegre.github.io/photons/optomechanics/) | Linearized optomechanics with direct detection on an ESA: transduction vs detuning (resolved/unresolved sideband), dependence on g₀, Ω_m, T and T_eff, thermal bistability during laser sweeps, PSD (dBm) → displacement calibration, optical spring/damping vs power, sideband cooling limit and OMIT/OMIA. Conventions of Aspelmeyer, Kippenberg & Marquardt, RMP 86, 1391 (2014). |
| [Loop taper on a waveguide: loss calibration](https://talegre.github.io/photons/taper-calibration/) | Loss budget of a fiber setup (laser, monitor splitter, polarization controller, circulator, loop taper touching a waveguide with an end reflector, 10/90 splitter to fast/slow detectors). Each component is entered as measured input/output powers or as a loss; the per-pass coupling η and contact scattering s are extracted from the transmission drop and the reflected power, with uncertainty propagation and a sensitivity plot vs the waveguide + reflector loss. |

Each simulation is a single self-contained HTML file, so it also works offline: just open the `index.html` of the folder. Most pages are plain JavaScript; the full optomechanics page has Plotly.js (MIT license) inlined, which is why it is ~4.5 MB.

## Model (cavity)

```
da/dt = [ i(ω_l − ω_c(|a|²)) − κ/2 ] a + √κ_e1 α_in,   α_in = √(P_in / ħω_l)
ω_c(|a|²) = ω_c⁽⁰⁾ + δω,   τ dδω/dt = ∓ g |a|^(2p) − δω
κ = κ_i + κ_e1 (+ κ_e2),   α_out,1 = α_in − √κ_e1 a,   α_out,2 = √κ_e2 a
```

Steady state: `|a|²[(Δ − δω(|a|²))² + κ²/4] = κ_e1 |α_in|²` (a cubic in |a|² for p = 1). A solution is stable iff `∂|α_in|²/∂|a|² > 0`.
