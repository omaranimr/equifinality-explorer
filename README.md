# Equifinality explorer: one hydrograph, many catchments

An interactive teaching tool that shows what **equifinality** means in hydrological modelling, and how a tracer such as **δ¹⁸O** can constrain it during history matching.

**Live tool:** https://omaranimr.github.io/equifinality-explorer/

This is not a modelling tool. It is a visual sandbox for lectures, presentations and self-study.

## What it shows

- **Equifinality.** Thousands of parameter sets reproduce the observed hydrograph almost equally well, while their internal behaviour (how much water travels overland, through the shallow subsurface, or through groundwater) differs strongly.
- **Tracer constraint.** Adding stream δ¹⁸O to the objective function rejects most of these "right answers for the wrong reasons" and narrows the plausible range of source contributions.
- **Celerity versus velocity.** Each store has a passive mixing volume that affects δ¹⁸O but not streamflow, showing why the hydrograph alone cannot reveal water age or mixing.

## How to use it

| Control | Effect |
|---|---|
| Overland-share slider | Browse accepted realizations, from little to mostly overland flow |
| Streamflow only / Streamflow + δ¹⁸O | Switch the objective function (animates the isotope weight *w*) |
| Accept if *J* ≥ | Acceptance (behavioral) threshold |
| Time series / Catchment | Switch between hydrograph plots and the 3D catchment schematic |
| This day / Whole 150 days | Arrow scaling in the catchment view |
| Explainer, Definitions | Beginner guide to δ¹⁸O, the catchment schematic, and key terms |
| Reveal truth | Show the true parameter set of the synthetic experiment |
| Click a dot | Load any individual realization |

Keyboard: ← → move, Space play sweep, I isotopes, C catchment view, B explainer, D definitions, T truth, E envelope.

## Model and assumptions

- Synthetic experiment over 150 days with daily time steps.
- Three parallel linear reservoirs (overland, shallow subsurface, groundwater), each with outflow Q = S/k.
- Each store is fully mixed over its dynamic storage plus a passive mixing volume. The overland mixing volume is fixed at 0.5 mm.
- Eight uncertain parameters, 30,000 Monte Carlo samples from uniform priors (log-uniform for time constants and mixing volumes).
- "Observed" streamflow is the true model plus 12% multiplicative noise; stream δ¹⁸O is sampled every 2 days with ±0.15‰ noise.
- Rain δ¹⁸O is stylized: a seasonal drift from −15‰ to −7‰ plus four strongly depleted storms.
- Objective: J = (1 − w)·NSE_Q + w·NSE_δ. Realizations with J above the threshold are accepted.
- Losses (evapotranspiration) are a fixed fraction (1 − c) of rainfall, a simplification of this conceptual model.

All computation runs in the browser. No data are collected or sent anywhere.

## Background reading

- Beven, K., & Binley, A. (1992). The future of distributed models: model calibration and uncertainty prediction. *Hydrological Processes*, 6(3), 279–298.
- Beven, K. (2006). A manifesto for the equifinality thesis. *Journal of Hydrology*, 320(1–2), 18–36.
- McDonnell, J. J., & Beven, K. (2014). Debates—The future of hydrological sciences: A (common) path forward? A call to action aimed at understanding velocities, celerities and residence time distributions of the headwater hydrograph. *Water Resources Research*, 50, 5342–5350.

## Embedding

To embed the tool in a course page (Moodle, Canvas, a website):

```html
<iframe src="https://omaranimr.github.io/equifinality-explorer/"
        width="100%" height="900" style="border:0" loading="lazy"
        title="Equifinality explorer"></iframe>
```

## Author and citation

Omar Nimr, University of Oulu.

If you use this tool in teaching or publications, please cite this repository.

## License

See the LICENSE file.
