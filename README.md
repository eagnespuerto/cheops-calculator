# CHEOPS Transit Calculator

A single-page calculator that derives planet and system parameters from a single transit light curve — the kind delivered by ESA's [CHEOPS](https://www.esa.int/Science_Exploration/Space_Science/Cheops) (CHaracterising ExOPlanet Satellite) mission.

**Live site:** https://eagnespuerto.github.io/cheops-calculator/

## What it computes

Given a transit's **depth** and **total duration**, the calculator returns the planet-to-star radius ratio. Optional inputs unlock additional derived parameters:

| Input                                | Unlocks                                            |
|--------------------------------------|----------------------------------------------------|
| Depth δ, duration T₁₄                | Radius ratio *k = √δ*                              |
| \+ Stellar radius R⋆                 | Planet radius Rₚ (in R⊕ and R♃)                    |
| \+ Flat duration T₂₃                 | Impact parameter *b*                               |
| \+ Orbital period P                  | Scaled distance a/R⋆, inclination *i*, stellar density ρ⋆ |

## Formulas

- **Radius ratio:** k = √δ
- **Impact parameter:** b² = [(1−k)² − (T₂₃/T₁₄)²(1+k)²] / [1 − (T₂₃/T₁₄)²]
- **Scaled distance:** a/R⋆ = √((1+k)² − b²) / sin(π T₁₄ / P)   *(assumes sin i ≈ 1)*
- **Inclination:** cos i = b / (a/R⋆)
- **Stellar density:** ρ⋆ = (3π / G P²) · (a/R⋆)³

## Run locally

No build step. Open `index.html` in any modern browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000.

## License

MIT.
