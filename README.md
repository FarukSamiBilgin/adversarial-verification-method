# Adversarial verification of a computational-physics design study: catching a gauge artifact, a tautology, and a silent parameter error

**Status:** Manuscript in preparation (methodology note). Author: Faruk Sami Bilgin, Independent Researcher ([ORCID 0009-0001-9064-4410](https://orcid.org/0009-0001-9064-4410)).

## Question
Computational design studies chain many plausible stages (band structure, current-phase relation, driven dynamics, thermal budget) into a quantitative proposal. Such chains fail silently: a result can be dimensionally sound, convergent and internally consistent, and still wrong. How do you catch errors that the author's own checks share?

## Method
One principle: every load-bearing result is re-derived by an independent verifier built to use an *orthogonal* method (different representation, discretization, or an analytic bound), with an adversarial mandate to break the result rather than reproduce it. Supporting habits: versioned module contracts, every number in prose traced to a stored artifact, fixed seeds and recorded provenance.

## Key results: three errors removed from a magic-angle twisted-bilayer-graphene Josephson-junction design study
1. **Gauge artifact.** A claimed algebraic 1/R tail of a flat-band pair-correlation form factor (fit R^2 = 0.9994, stable under refinement) came from a single-zone Fourier transform of a band projector that is not periodic across the zone (||dP||/||P|| ~ 1.3). The gauge-invariant real-space density matrix decays exponentially (xi = 17.9 nm), as required for a gapped band; a true 1/R tail would also make the integrated quantum metric diverge, which it does not. Claim withdrawn.
2. **Tautology.** A "quantum-geometric twist-angle law" plotted a quantity proportional to (integrated quantum metric)/(bandwidth). The metric varied only 1.4x (and peaked away from the magic angle); the bandwidth varied by more than 10x with its minimum at the magic angle. Decomposition: 97.8% of the peak from 1/W, 2.2% from geometry, i.e. "the feature is largest where the band is flattest".
3. **Silent parameter fallback.** A figure showed a 7x peak contrast; recomputation from the converged artifact gave 1.7x. The plotting code failed to parse the converged bandwidth and silently fell back to a provisional value off by 6x. Figure retracted and regenerated.

None of the three was a coding bug in the ordinary sense; all three were convergent.

## Reusable checklist
1. Claims and evidence separable (artifact tracing). 2. Name the most fragile assumption and re-derive without it. 3. Use gauge-invariant objects for anything called an observable. 4. Attach a theorem or bound. 5. Decompose every striking feature into factors. 6. Regenerate figures from authoritative artifacts; missing inputs must raise, never default. 7. Adversarial mandate; report the best counter-argument even on failure.

A seeded-error benchmark (injected gauge artifacts, tautological ratios, silent fallbacks, sign flips) is proposed to score verification procedures by detection and false-positive rate.

## Limitations
N = 1 study, three catches: a demonstration, not a measured efficacy. Errors shared by both routes (e.g. a wrong physical assumption common to all models) are invisible to the method.

## Contents
- `paper/ABSTRACT.md` - extended abstract. The full note is not included because it cites external literature whose references have not yet been checked.

## Related work by the author
- Twisted hBN preprint: https://doi.org/10.5281/zenodo.24201814
- Twisted MoS2 preprint: https://www.alphaxiv.org/abs/2611.twisted-mos2-hole-spin-coherence
- Moiré microwave loss: https://doi.org/10.5281/zenodo.24204124
- josim-cpr-bridge: https://github.com/FarukSamiBilgin/josim-cpr-bridge

AI assistance: AI coding assistants were used for code development and for adversarial review. All load-bearing results were re-derived by independent methods and checked by automated tests; the author is responsible for every claim.

## Citation
See `CITATION.cff`. License: text CC BY 4.0 (`LICENSE-CONTENT`); code MIT (`LICENSE`).
